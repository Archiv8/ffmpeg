#!/bin/bash

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
#
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
# [Query]: Option --enable-avresample does not appear to be a valid configuration option and throws error on configure. See ./configure --help
# [Query]: Option --enable-libsvthevc does not appear to be a valid configuration option and throws error on configure. See ./configure --help
# [Query]: Option --enable-libsvtvp9 does not appear to be a valid configuration option and throws error on configure. See ./configure --help
# [Query]: What provides libopencv. Currently disabled
# [Query]: What provides libopenvino. Currently disabled
# [Query]: What provides libtensorflow. Currently disabled
# [Query]: Is libtls needed. Currently disabled
# [Query]: Is mbedtls needed. Currently disabled
# [FixMe]: ERROR: cuvid requested, but not all dependencies are satisfied: ffnvcodec
# [FixMe]: Cannot find library listed in 'provides': libavresample.so
# [FixMe]: Namcap warnings and errors

# Maintainer: Ross Clark <archiv8@artisteducator.com>
# Contributor: Ross Clark <archiv8@artisteducator.com>

pkgname=ffmpeg
pkgver=5.0.1
pkgrel=1
pkgdesc="Complete solution to record, convert and stream audio and video (all possible features for AMD)"
arch=("x86_64")
url="https://www.ffmpeg.org/"
license=("custom: nonfree and unredistributable")
depends=(
    # Archiv8 / AUR:
    "alsa-lib"
    "avisynthplus"
    "bzip2"
    "frei0r-plugins"
    "libgcrypt"
    "gmp"
    "gnutls"
    "ladspa"
    "libass"
    "aom"
    "aribb24"
    "libbluray"
    "libbs2b"
    "libcaca"
    "libmfx"
    "celt"
    "libcdio-paranoia"
    "chromaprint"
    "codec2"
    "dav1d"
    "libdc1394"
    "libavc1394"
    "libfdk-aac"
    "flite1-patched"
    "fontconfig"
    "freetype2"
    "fribidi"
    "glslang"
    "spirv-tools"
    "libgme"
    "gsm"
    "libiec61883"
    "libilbc"
    "jack"
    "kvazaar"
    "libmodplug"
    "lame"
    "opencore-amr"
    "openjpeg2"
    "opus"
    "libpulse"
    "librabbitmq-c"
    "rav1e"
    "librsvg"
    "rubberband"
    "rtmpdump"
    "smbclient"
    "snappy"
    "libsoxr"
    "speex"
    "srt"
    "libssh"
    "svt-hevc"
    "svt-av1"
    "svt-vp9"
    "tesseract"
    "libtheora"
    "twolame"
    "v4l-utils"
    "vid.stab"
    "vmaf"
    "libvorbis"
    "libvpx"
    "libwebp"
    "x264"
    "x265"
    "libxcb"
    "xvidcore"
    "libxml2"
    "zimg"
    "zeromq"
    "zvbi"
    "lv2"
    "lilv"
    "xz"
    "libmysofa"
    "openal"
    "ocl-icd"
    "libgl"
    "sndio"
    "sdl2"
    "vapoursynth"
    "vulkan-icd-loader"
    "libxv"
    "libx11"
    "libxext"
    "zlib"
    "libomxil-bellagio"
    "libdrm"
    "libva"
    "libvdpau"
    "cuda"
    "opencv"
    "openvino"

    # Archiv8 / AUR:
    "davs2"
    "libklvanc-git"
    "openh264"
    "libopenmpt-svn"
    "librist"
    "shine"
    "uavs3d-git"
    "vo-amrwbenc"
    "xavs"
    "xavs2"
    "pocketsphinx"
    "lensfun-git"
)
makedepends=(
    # Official Repositories:
    "amf-headers"
    "clang"
    "ffnvcodec-headers"
    "nasm"
    "opencl-headers"
    "vulkan-headers"
    # Archiv8 / AUR:
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
    "ffmpeg"
    "ffmpeg-full"
)
conflicts=(
    "ffmpeg-amd-full"
)
_svt_hevc_ver="33ca9aa8a2a2d28022d3fc03704e99ce01828376"
_svt_vp9_ver="abd5c59c06d686eae57ef4e6f899c601f791d055"
source=(
    "https://ffmpeg.org/releases/ffmpeg-${pkgver}.tar.xz"{,.asc}
    "010-ffmpeg-fix-vmaf-model-path.patch"
    "020-ffmpeg-add-svt-hevc-g${_svt_hevc_ver:0:7}.patch"::"https://raw.githubusercontent.com/OpenVisualCloud/SVT-HEVC/${_svt_hevc_ver}/ffmpeg_plugin/0001-lavc-svt_hevc-add-libsvt-hevc-encoder-wrapper.patch"
    "030-ffmpeg-add-svt-hevc-docs-g${_svt_hevc_ver:0:7}.patch"::"https://raw.githubusercontent.com/OpenVisualCloud/SVT-HEVC/${_svt_hevc_ver}/ffmpeg_plugin/0002-doc-Add-libsvt_hevc-encoder-docs.patch"
    "040-ffmpeg-add-svt-vp9-g${_svt_vp9_ver:0:7}.patch"::"https://raw.githubusercontent.com/OpenVisualCloud/SVT-VP9/${_svt_vp9_ver}/ffmpeg_plugin/master-0001-Add-ability-for-ffmpeg-to-run-svt-vp9.patch"
    #   "LICENSE"
)
sha256sums=(
    'ef2efae259ce80a240de48ec85ecb062cecca26e4352ffb3fda562c21a93007b'
    'SKIP'
    '52778c70d9fe6e3a10941b99b96ac7749cec325dc1b9ee11ab75332b5ff68e50'
    '740dc9838aa47daa9f9b107178e53e384344f4c6f90865bd7e3af189257da544'
    '1499e419dda72b1604dc5e3959668f3843292ff56bfba78734e31510ba576de0'
    'b7d722dfce20b73e9d5c73d55ffe041bbdc92a3c4a5c5d766b6b3040671b4052'
)
# validpgpkeys=(
#     'FCF986EA15E6E293A5644F10B4322F04D67658D8'
# )

# prepare() {
#    rm -f "ffmpeg-${pkgver}/libavcodec/"libsvt_{hevc,vp9}.c
#    sed -i 's/general.texi/general_contents.texi/g' "030-ffmpeg-add-svt-hevc-docs-g${_svt_hevc_ver:0:7}.patch"
#    patch -d "ffmpeg-${pkgver}" -Np1 -i "${srcdir}/010-ffmpeg-fix-vmaf-model-path.patch"
#    patch -d "ffmpeg-${pkgver}" -Np1 -i "${srcdir}/020-ffmpeg-add-svt-hevc-g${_svt_hevc_ver:0:7}.patch"
#    patch -d "ffmpeg-${pkgver}" -Np1 -i "${srcdir}/030-ffmpeg-add-svt-hevc-docs-g${_svt_hevc_ver:0:7}.patch"
#    patch -d "ffmpeg-${pkgver}" -Np1 -i "${srcdir}/040-ffmpeg-add-svt-vp9-g${_svt_vp9_ver:0:7}.patch"
# }

build() {

    cd "ffmpeg-${pkgver}"

    printf '%s\n' '-> Running ffmpeg configure script...'

    ./configure \
        --prefix='/usr' \
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
        --disable-autodetect \
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
        --enable-libopenvino \
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
        --enable-pocketsphinx \
        --enable-sndio \
        --enable-sdl2 \
        --disable-schannel \
        --disable-securetransport \
        --enable-vapoursynth \
        --enable-vulkan \
        --enable-xlib \
        --enable-zlib \
        \
        --enable-lto \
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
        --disable-libmfx \
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
        --disable-debug \
        --disable-stripping

    make

    make tools/qt-faststart

    make doc/ff{mpeg,play}.1
}

package() {
    # make -C "ffmpeg-${pkgver}" DESTDIR="$pkgdir" install

    #  install -D -m755 "ffmpeg-${pkgver}/tools/qt-faststart" -t "${pkgdir}/usr/bin"

    #   install -D -m644 LICENSE -t "${pkgdir}/usr/share/licenses/${pkgname}"

    make DESTDIR="${pkgdir}" -C ffmpeg install install-man

    install -Dm 755 ffmpeg/tools/qt-faststart "${pkgdir}"/usr/bin/

}
