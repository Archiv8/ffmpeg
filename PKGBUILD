#!/bin/bash

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.

# [Note]: Intel only option: libmfx
# [Note]: The nvidia Cg toolkit is no longer actively maintained and therefore not enabled in build. Latest update April 2012.  See https://developer.nvidia.com/cg-toolkit.  Suggested alternative,
# [Note]: nvFX, is unmaintained and therefore not enabled in build. See https://github.com/tlorach/nvFX
# [Note]: AMD only options: OpenMAX(partial)
# [Note]: Nvidia only options: NVENC / NVDEC / CUVID
# [Note]: Android only option: MediaCodec / V4L2 M2M, JNI
# [Note]: Apple only option: VideoToolbox
# [Note]: Windows only options: AMF / Direct3D 11 / Direct3D 9 (DXVA2) / Media Foundation
# [Note]: Raspberry Pi only option: MMAL
# [Note]: libshaderc and libglslang are mutually exclusive, if in doubt, disable libglslang
# [ToDo]: Add files: User documentation
# [ToDo]: Add files: Tooling
# [ToDo]: Split required packages between makedepends, depends and optdepends variables
# [ToDo]: Configure component options
# [ToDo]: Ensure licenses are up to date
# [ToDo]: Create split package to allow, for example, amd, intel, nvidia  only installs
# [ToDo]: Split depends between "depends", "makedepends" and "optdepends" fields
# [Query]: Option "enable-avresample" does not appear to be a valid configuration option and throws error on configure. See ./configure --help
# [Query]: Option "enable-libsvthevc" does not appear to be a valid configuration option and throws error on configure. See ./configure --help
# [Query]: Option "enable-libsvtvp9" does not appear to be a valid configuration option and throws error on configure. See ./configure --help
# [Query]: What provides libopencv. Currently disabled
# [Query]: What provides libopenvino. Currently disabled
# [Query]: What provides libtensorflow. Currently disabled
# [Query]: Is libtls needed. Currently disabled
# [Query]: Is mbedtls needed. Currently disabled
# [FixMe]: ERROR: cuvid requested, but not all dependencies are satisfied: ffnvcodec
# [FixMe]: Cannot find library listed in "provides": libavresample.so
# [FixMe]: Namcap warnings and errors

# Maintainer: Ross Clark <https://github.com/Archiv8/ffmpeg/discussions>
# Contributor: Ross Clark <https://github.com/Archiv8/ffmpeg/discussions>

_svt_hevc_ver="b62f72e752243cee4104cfb41dc7ee409d3ac3e9"
_svt_vp9_ver="d9ef3cc13159143b9afc776c04f67cdfa6284046"

pkgname=ffmpeg
pkgver=5.1
pkgrel=1
pkgdesc="A complete solution to record, convert and stream audio and video (all possible features for AMD)"
arch=("x86_64")
url="https://www.ffmpeg.org/"
license=("custom: nonfree and unredistributable" "LGPL2.1" "GPL2" "GPL3" "LGPL3")
depends=(
  # Arch Linux official repositories
  "amf-headers"
  "aom"
  "aribb24"
  "alsa-lib"
  "avisynthplus"
  "bzip2"
  "celt"
  "chromaprint"
  "clang"
  "codec2"
  "cuda"
  "dav1d"
  "ffnvcodec-headers"
  "fontconfig"
  "freetype2"
  "fribidi"
  "frei0r-plugins"
  "glslang"
  "gmp"
  "gsm"
  "gnutls"
  "jack"
  "intel-media-sdk"
  "kvazaar"
  "ladspa"
  "lame"
  "lcms2"
  "libass"
  "libavc1394"
  "libbluray"
  "libbs2b"
  "libcaca"
  "libcdio-paranoia"
  "libdc1394"
  "libdrm"
  "libfdk-aac"
  "libgcrypt"
  "libgl"
  "libgme"
  "libiec61883"
  "libilbc"
  "libjxl"
  "libmfx"
  "libmodplug"
  "libmysofa"
  "libomxil-bellagio"
  "libopenmpt"
  "libplacebo"
  "libpulse"
  "librabbitmq-c"
  "libraw1394"
  "librsvg"
  "libsoxr"
  "libssh"
  "libtheora"
  "libva"
  "libvdpau"
  "libvorbis"
  "libvpx"
  "libwebp"
  "libxext"
  "libx11"
  "libxcb"
  "libxml2"
  "libxv"
  "lv2"
  "lilv"
  "nasm"
  "nvidia-utils"
  "openal"
  "opencl-headers"
  "opencv"
  "ocl-icd"
  "opencore-amr"
  "openjpeg2"
  "opus"
  "rav1e"
  "rtmpdump"
  "rubberband"
  "sdl2"
  "smbclient"
  "snappy"
  "sndio"
  "speex"
  "spirv-tools"
  "srt"
  "svt-hevc"
  "svt-av1"
  "svt-vp9"
  "tesseract"
  "twolame"
  "v4l-utils"
  "vapoursynth"
  "vid.stab"
  "vmaf"
  "vulkan-headers"
  "vulkan-icd-loader"
  "x264"
  "x265"
  "xvidcore"
  "xz"
  "zeromq"
  "zimg"
  "zlib"
  "zvbi"
  # "openvino"

  # Archiv8 / AUR
  "davs2"
  # [Fixed]:  2022/05/03 FFMpeg requires shared libraries that are not included within the official, Arch Linux, flite packages. See https://github.com/Archiv8/flite to get flite-full.
  "flite-all"
  "lensfun"
  "libklvanc"
  "openh264"
  "librist"
  "shine"
  "uavs3d"
  "vo-amrwbenc"
  "xavs"
  "xavs2"
)
makedepends=(
  # Arch Linux official repositories
  "git"

  # "amf-headers"
  # "clang"
  # "ffnvcodec-headers"
  # "nasm"
  # "opencl-headers"
  # "vulkan-headers"

  # Archiv8 / AUR
  "decklink-sdk"
)
provides=(
  "ffmpeg"
  "libavcodec.so"
  "libavdevice.so"
  "libavfilter.so"
  "libavformat.so"
  "libavutil.so"
  "libpostproc.so"
  "libavresample.so"
  "libswscale.so"
  "libswresample.so"
)
# options=(
#   "debug"
# )
source=(
  "https://ffmpeg.org/releases/ffmpeg-${pkgver}.tar.xz"{,.asc}
  "010-ffmpeg-add-svt-hevc-g${_svt_hevc_ver:0:7}.patch"::"https://raw.githubusercontent.com/OpenVisualCloud/SVT-HEVC/${_svt_hevc_ver}/ffmpeg_plugin/master-0001-lavc-svt_hevc-add-libsvt-hevc-encoder-wrapper.patch"
  "020-ffmpeg-add-svt-hevc-docs-g${_svt_hevc_ver:0:7}.patch"::"https://raw.githubusercontent.com/OpenVisualCloud/SVT-HEVC/${_svt_hevc_ver}/ffmpeg_plugin/0002-doc-Add-libsvt_hevc-encoder-docs.patch"
  "030-ffmpeg-add-svt-vp9-g${_svt_vp9_ver:0:7}.patch"::"https://raw.githubusercontent.com/OpenVisualCloud/SVT-VP9/${_svt_vp9_ver}/ffmpeg_plugin/master-0001-Add-ability-for-ffmpeg-to-run-svt-vp9.patch"
  "040-ffmpeg-add-av_stream_get_first_dts-for-chromium.patch"
  # "050-ffmpeg-vmaf-2.x.patch"
  "060-ffmpeg-fix-segfault-with-avisynthplus.patch"
  # "070-ffmpeg-libsvtav1-0.9.0-part1.patch"::"https://git.ffmpeg.org/gitweb/ffmpeg.git/patch/c33b4048859a191acf9b6aa22acaea248a4eb18f"
  # "080-ffmpeg-libsvtav1-0.9.0-part2.patch"::"https://git.ffmpeg.org/gitweb/ffmpeg.git/patch/1dddb930aaf0cadaa19f86e81225c9c352745262"
)
sha512sums=(
  '9ba24f7488d1c7f8a3e3fbc3920e329724e75631d769400998f7a0858c58213f2eee2880fdd7caa9a701150217448a834b5008840327478314e4508c5e0e3b19'
  'SKIP'
  '81d94885a8442527ffe8dc76bd68ac93983790c8e6a984016481f3b38c4e0bcfb3d7f53b1a511ac85c347f196c33a10a14f1115ffd5708a12cafa89bb1176e28'
  '86ba78179084d02adafa599a25b8c9880a788db3007c49a16f1bcc81c022fd3d63cbe68bfea185934205d00d004c5b1b7d749679318d5b7cf0bd2c9a1892e167'
  '34cf3210192bc963ea9f2ec207a3c7680483d18922712757426f822bbdae62e6bfa92512d27b9314ca671a66632f7a58138a29144ac590d262e5235bde33e8ea'
  'b144d4a68b2cdd4ba8d0fcff34fb93abd17daf016799376ca47a5882251aca4a166202f2680dddad10ec011da93d4257810c5ec57712faf592f89bd6ed512fbe'
  'd3d59ff6285b4a9c7d905ec46136928fa7207c47b5a21011a864a7323a421aa25667c8ecf15877f4070df3736039cd4b9834245cd5b32632a0705deb6f4338ab'
)
# validpgpkeys=(
#     "FCF986EA15E6E293A5644F10B4322F04D67658D8"
# )

prepare() {

  cd "$pkgname-$pkgver"

  # [Fixes]: avcodec/nvenc on older gpus. See https://github.com/FFmpeg/FFmpeg/commit/988f2e9eb063db7c1a678729f58aab6eba59a55b
  # git cherry-pick -n 988f2e9eb063db7c1a678729f58aab6eba59a55b

  # [Fixes]:
  rm -f "ffmpeg-${pkgver}/libavcodec/"libsvt_{hevc,vp9}.c

  # [Fixes]: AVCodecs are not modified any longer in ffmpeg for "lavc/svt_hevc" add "libsvt hevc" encoder wrapper
  echo Patch 1 of 8
  patch -d "${srcdir}/ffmpeg-${pkgver}" -Np1 -i "${srcdir}/010-ffmpeg-add-svt-hevc-g${_svt_hevc_ver:0:7}.patch"

  # [Fixes]: Add docs for libsvt_hevc encoder in encoders.texi and general.texi
  # [FixMe]: Patch fails with, "patch: **** malformed patch at line 177:  @section libtheora"
  # echo Patch 2 of 8
  # patch -d "${srcdir}/ffmpeg-${pkgver}" -Np1 -i "${srcdir}/020-ffmpeg-add-svt-hevc-docs-g${_svt_hevc_ver:0:7}.patch"

  # [Fixes]: Add ability for ffmpeg to run svt vp9
  echo Patch 3 of 8
  patch -d "${srcdir}/ffmpeg-${pkgver}" -Np1 -i "${srcdir}/030-ffmpeg-add-svt-vp9-g${_svt_vp9_ver:0:7}.patch"

  # [Fixes]: chromium build failure on Chromium 94+,add "av_stream_get_first_dts". See, https://crbug.com/1251779
  echo Patch 4 of 8
  patch -d "${srcdir}/ffmpeg-${pkgver}" -Np1 -i "${srcdir}/040-ffmpeg-add-av_stream_get_first_dts-for-chromium.patch"

  # [Fixes]: vmaf 2.x support. See https://aur.archlinux.org/cgit/aur.git/tree/050-ffmpeg-vmaf-2.x.patch?h=ffmpeg-full
  # echo Patch 5 of 8
  # patch -d "${srcdir}/ffmpeg-${pkgver}" -Np1 -i "${srcdir}/050-ffmpeg-vmaf-2.x.patch"

  # [Fixes]: Fix segmentation fault when using avisynth plus
  echo Patch 6 of 8
  patch -d "${srcdir}/ffmpeg-${pkgver}" -Np1 -i "${srcdir}/060-ffmpeg-fix-segfault-with-avisynthplus.patch"

  # [Fixes]: Add a svtav1-params option to pass a list of key=value parameters
  # echo Patch 7 of 8
  # patch -d "${srcdir}/ffmpeg-${pkgver}" -Np1 -i "${srcdir}/070-ffmpeg-libsvtav1-0.9.0-part1.patch"

  # [Fixes]: For "avcodec/libsvtav1" update some options and defaults
  # echo Patch 8 of 8
  # patch -d "${srcdir}/ffmpeg-${pkgver}" -Np1 -i "${srcdir}/080-ffmpeg-libsvtav1-0.9.0-part2.patch"
}

build() {

  cd "${srcdir}/$pkgname-$pkgver"

  printf "%s\n" "-> Running ffmpeg configure script..."

  ./configure \
    --prefix="/usr" \
    --enable-logging \
    --disable-rpath \
    --enable-gpl \
    --enable-version3 \
    --enable-nonfree \
    --disable-static \
    --enable-shared \
    --disable-small \
    --enable-runtime-cpudetect \
    --enable-gray \
    --enable-swscale-alpha \
    --enable-autodetect \
    --enable-avdevice \
    --enable-avcodec \
    --enable-avformat \
    --enable-swresample \
    --enable-swscale \
    --enable-postproc \
    --enable-avfilter \
    --enable-pthreads \
    --disable-w32threads \
    --disable-os2threads \
    --enable-network \
    --enable-dct \
    --enable-dwt \
    --enable-error-resilience \
    --enable-lsp \
    --enable-mdct \
    --enable-rdft \
    --enable-fft \
    --enable-faan \
    --enable-pixelutils \
    --enable-alsa \
    --disable-appkit \
    --disable-avfoundation \
    --enable-avisynth \
    --enable-bzlib \
    --disable-coreimage \
    --enable-chromaprint \
    --enable-frei0r \
    --enable-gcrypt \
    --enable-gmp \
    --enable-gnutls \
    --enable-iconv \
    --disable-jni \
    --enable-ladspa \
    --enable-libaom \
    --enable-libaribb24 \
    --enable-libass \
    --enable-libbluray \
    --enable-libbs2b \
    --enable-libcaca \
    --enable-libcelt \
    --enable-libcdio \
    --enable-libcodec2 \
    --enable-libdav1d \
    --enable-libdavs2 \
    --enable-libdc1394 \
    --enable-libfdk-aac \
    --enable-libflite \
    --enable-fontconfig \
    --enable-libfreetype \
    --enable-libfribidi \
    --disable-libglslang \
    --enable-libgme \
    --enable-libgsm \
    --enable-libiec61883 \
    --enable-libilbc \
    --enable-libjack \
    --enable-libklvanc \
    --enable-libkvazaar \
    --enable-liblensfun \
    --enable-libmodplug \
    --enable-libmp3lame \
    --enable-libopencore-amrnb \
    --enable-libopencore-amrwb \
    --disable-libopencv \
    --enable-libopenh264 \
    --enable-libopenjpeg \
    --enable-libopenmpt \
    --disable-libopenvino \
    --enable-libopus \
    --enable-libplacebo \
    --enable-libpulse \
    --enable-librabbitmq \
    --enable-librav1e \
    --enable-librist \
    --enable-librsvg \
    --enable-librubberband \
    --enable-librtmp \
    --disable-libshaderc \
    --enable-libshine \
    --enable-libsmbclient \
    --enable-libsnappy \
    --enable-libsoxr \
    --enable-libspeex \
    --enable-libsrt \
    --enable-libssh \
    --enable-libsvtav1 \
    --disable-libtensorflow \
    --enable-libtesseract \
    --enable-libtheora \
    --disable-libtls \
    --enable-libtwolame \
    --enable-libuavs3d \
    --enable-libv4l2 \
    --enable-libvidstab \
    --enable-libvmaf \
    --enable-libvo-amrwbenc \
    --enable-libvorbis \
    --enable-libvpx \
    --enable-libwebp \
    --enable-libx264 \
    --enable-libx265 \
    --enable-libxavs \
    --enable-libxavs2 \
    --enable-libxcb \
    --enable-libxcb-shm \
    --enable-libxcb-xfixes \
    --enable-libxcb-shape \
    --enable-libxvid \
    --enable-libxml2 \
    --enable-libzimg \
    --enable-libzmq \
    --enable-libzvbi \
    --enable-lv2 \
    --enable-lzma \
    --enable-decklink \
    --disable-mbedtls \
    --disable-mediacodec \
    --disable-mediafoundation \
    --disable-metal \
    --enable-libmysofa \
    --enable-openal \
    --enable-opencl \
    --enable-opengl \
    --disable-openssl \
    --disable-pocketsphinx \
    --enable-sndio \
    --enable-sdl2 \
    --disable-schannel \
    --disable-securetransport \
    --enable-vapoursynth \
    --enable-vulkan \
    --enable-xlib \
    --enable-zlib \
    --enable-amf \
    --disable-audiotoolbox \
    --enable-cuda-nvcc \
    --enable-cuda-llvm \
    --enable-cuvid \
    --disable-d3d11va \
    --disable-dxva2 \
    --enable-ffnvcodec \
    --enable-libdrm \
    --enable-libmfx \
    --disable-libnpp \
    --disable-mmal \
    --enable-nvdec \
    --enable-nvenc \
    --enable-omx \
    --disable-omx-rpi \
    --disable-rkmpp \
    --enable-v4l2-m2m \
    --enable-vaapi \
    --enable-vdpau \
    --disable-videotoolbox \
    --enable-lto \
    --disable-debug \
    --disable-stripping

  make

  make tools/qt-faststart

  make doc/ff{mpeg,play}.1
}

package() {
  make -C "$pkgname-$pkgver" DESTDIR="$pkgdir" install

  install -D -m755 "$pkgname-$pkgver/tools/qt-faststart" -t "${pkgdir}/usr/bin"

  install -D -m644 "$pkgname-$pkgver/LICENSE.md" -t "${pkgdir}/usr/share/licenses/${pkgname}"

  install -D -m644 "$pkgname-$pkgver/COPYING.LGPLv2.1" -t "${pkgdir}/usr/share/licenses/${pkgname}"

  install -D -m644 "$pkgname-$pkgver/COPYING.GPLv2" -t "${pkgdir}/usr/share/licenses/${pkgname}"

  install -D -m644 "$pkgname-$pkgver/COPYING.GPLv3" -t "${pkgdir}/usr/share/licenses/${pkgname}"

  install -D -m644 "$pkgname-$pkgver/COPYING.LGPLv3" -t "${pkgdir}/usr/share/licenses/${pkgname}"
}
