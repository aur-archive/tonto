# Maintainer : Martin Wimpress <code@flexion.org>

pkgname=tonto
pkgver=1.48
pkgrel=3
pkgdesc="An essential sidekick for the Pronto Family of programmable remotes."
arch=('i686' 'x86_64')
url="http://mrallen.com/tonto/"
license=('custom')
depends=('bash' 'java-runtime' 'zenity')
makedepends=('unzip')
options=('!strip')
source=("${pkgname}.sh"
        "${pkgname}.desktop"
        "http://mrallen.com/${pkgname}/image/${pkgname}.gif"
        "http://mrallen.com/${pkgname}/dload/${pkgname}.jar"
        "http://mrallen.com/${pkgname}/dload/libs.jar")
md5sums=('63bbd2eb2a729e6580db9503763ff205'
         '92ba8571899d60b63bfaeb7e5fb535d4'
         '151a69649e0e624ff34edd37bc72831d'
         'c985b33ffcf7373e64cd80edeb26a94d'
         'c74ef433c84cc9ac7f99528dbba91dfa')

package() {
    cd "${srcdir}"
    install -D -m 755 ${pkgname}.sh "${pkgdir}/opt/${pkgname}/${pkgname}.sh"
    install -D -m 644 ${pkgname}.gif "${pkgdir}/opt/${pkgname}/${pkgname}.gif"
    install -D -m 644 ${pkgname}.desktop "${pkgdir}/usr/share/applications/${pkgname}.desktop"
    install -D -m 644 ${pkgname}.jar "${pkgdir}/opt/${pkgname}/${pkgname}.jar"
    if [ "${CARCH}" == "i686" ]; then
        mkdir -p "${pkgdir}/opt/${pkgname}"/lib
        unzip -o -qq libs.jar -d "${pkgdir}/opt/${pkgname}"/lib
        rm -rf "${pkgdir}/opt/${pkgname}"/lib/{*.dll,META-INF,osx}
    fi
}
