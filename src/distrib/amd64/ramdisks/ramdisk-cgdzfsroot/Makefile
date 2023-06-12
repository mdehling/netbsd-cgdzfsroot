#	$NetBSD$

IMAGE=			ramdisk-cgdzfsroot.fs
IMAGESIZE=		5000k
IMAGEDEPENDS=
MAKEDEVTARGETS=		all
CRUNCHENV=		INIT_CHROOT=1
SMALLPROG_INET6=	1

# Build as re-entrant because zpool requires libhack built this way.
CPPFLAGS+=		-D_REENTRANT

LISTS+=			${.CURDIR}/list
LISTS+=			${DISTRIBDIR}/common/list.cgdzfsroot

.include "${.CURDIR}/../common/Makefile.ramdisk"
.include "${DISTRIBDIR}/common/Makefile.makedev"

MTREECONF+=		${DISTRIBDIR}/common/mtree.cgdzfsroot

.if ${USE_INET6} != "no"
LISTS+=			${DISTRIBDIR}/common/list.inet6
.endif
