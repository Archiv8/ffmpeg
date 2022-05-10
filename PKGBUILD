#!/bin/bash

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154

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
# [Query]: Option --enable-avresample does not appear to be a valid configuration option and throws error on configure. See ./configure --help
# [Query]: Option --enable-libsvthevc does not appear to be a valid configuration option and throws error on configure. See ./configure --help
# [Query]: Option --enable-libsvtvp9 does not appear to be a valid configuration option and throws error on configure. See ./configure --help
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

_relname=ffmpeg

pkgname=${_relname}
pkgver=5.0
pkgrel=16
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
  "lensfun"
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
  "libmfx"
  "libmodplug"
  "libmysofa"
  "libomxil-bellagio"
  "libopenmpt"
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
  "libklvanc"
  "openh264"
  "librist"
  "shine"
  "uavs3d"
  "vo-amrwbenc"
  "xavs"
  "xavs2"
  "lensfun"
)
makedepends=(
  # Arch Linux official repositories
  "git"

  # "amf-headers"
  # "clang"
  #  "ffnvcodec-headers"
  #   "nasm"
  # "opencl-headers"
  #  "vulkan-headers"

  # Archiv8 / AUR
  "decklink-sdk"
)
provides=(
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
_tag=390d6853d0ef408007feb39c0040682c81c02751
# options=(
#   "debug"
# )
source=(
  "$_relname-$pkgver::git+https://git.ffmpeg.org/ffmpeg.git#tag=${_tag}"
  "ffmpeg-vmaf2.x.patch"
  "add-av_stream_get_first_dts-for-chromium.patch"
)
sha512sums=(
  'SKIP'
  'f775e35465f6487b50e1e5f36c70946ee03db448bc2970c5b4b697565fa380c4a61d8a7bed0cbb89a54b1118a2f097cf4a27290d632575c524876beeff448f5a'
  'bb23ce619dc98f341ded7e269dd703074d6fb5aa28bd71ba1f62bc4c02e471bf57d99aa47d57993596ffe7aa65fbb410410082705dd203839bb0992975f1fede'
)
# validpgpkeys=(
#     "FCF986EA15E6E293A5644F10B4322F04D67658D8"
# )

prepare() {
  cd "$_relname-$pkgver"
  #[Fixes]: avcodec/nvenc on older gpus. See https://github.com/FFmpeg/FFmpeg/commit/988f2e9eb063db7c1a678729f58aab6eba59a55b
  git cherry-pick -n 988f2e9eb063db7c1a678729f58aab6eba59a55b
  patch -Np1 -i ../ffmpeg-vmaf2.x.patch                           # vmaf 2.x support. See https://aur.archlinux.org/cgit/aur.git/tree/050-ffmpeg-vmaf-2.x.patch?h=ffmpeg-full
  patch -Np1 -i ../add-av_stream_get_first_dts-for-chromium.patch # Fix chromium build failure on Chromium 94+. See, https://crbug.com/1251779
}

pkgver() {
  cd "$_relname-$pkgver"
  git describe --tags | sed 's/^n//'
}

build() {

  cd "$_relname-$pkgver"

  printf "%s\n" "-> Running ffmpeg configure script..."

  ./configure \
    --prefix="/usr" \
    --enable-logging \
    --disable-rpath \
    \
    --enable-gpl \
    --enable-version3 \
    --enable-nonfree \
    \
    --disable-static \
    --enable-shared \
    --disable-small \
    --enable-runtime-cpudetect \
    --enable-gray \
    --enable-swscale-alpha \
    \
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
    --enable-lzo \
    --enable-mdct \
    --enable-rdft \
    --enable-fft \
    --enable-faan \
    --enable-pixelutils \
    \
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
    \
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
    \
    --enable-lto \
    \
    --disable-debug \
    --disable-stripping

  make

  make tools/qt-faststart

  make doc/ff{mpeg,play}.1
}

package() {
  make -C "$_relname-$pkgver" DESTDIR="$pkgdir" install

  install -D -m755 "$_relname-$pkgver/tools/qt-faststart" -t "${pkgdir}/usr/bin"

  install -D -m644 "$_relname-$pkgver/LICENSE.md" -t "${pkgdir}/usr/share/licenses/${pkgname}"

  install -D -m644 "$_relname-$pkgver/COPYING.LGPLv2.1" -t "${pkgdir}/usr/share/licenses/${pkgname}"

  install -D -m644 "$_relname-$pkgver/COPYING.GPLv2" -t "${pkgdir}/usr/share/licenses/${pkgname}"

  install -D -m644 "$_relname-$pkgver/COPYING.GPLv3" -t "${pkgdir}/usr/share/licenses/${pkgname}"

  install -D -m644 "$_relname-$pkgver/COPYING.LGPLv3" -t "${pkgdir}/usr/share/licenses/${pkgname}"
}
