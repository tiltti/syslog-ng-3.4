SUBDIRS = @IVYKIS_SUBDIRS@
DIST_SUBDIRS = ivykis
moduledir = @moduledir@


YFLAGS=@YFLAGS@

export top_srcdir

lib_LTLIBRARIES = libsyslog-ng.la
libsyslog_ng_la_LIBADD = @CORE_DEPS_LIBS@
libsyslog_ng_la_LDFLAGS = -no-undefined -release @VERSION@

module_LTLIBRARIES = libsyslog-ng-crypto.la
libsyslog_ng_crypto_la_CFLAGS = @UUID_CFLAGS@
libsyslog_ng_crypto_la_LIBADD = @CORE_DEPS_LIBS@ @OPENSSL_LIBS@ @UUID_LIBS@ libsyslog-ng.la
libsyslog_ng_crypto_la_LDFLAGS = -no-undefined -avoid-version

# this is intentionally formatted so conflicts are less likely to arise. one name in every line.
pkginclude_HEADERS = 		\
	afinter.h		\
	alarms.h		\
	apphook.h		\
	atomic.h		\
	block-ref-parser.h	\
	cfg.h                   \
	cfg-grammar.h           \
	cfg-lexer.h		\
	cfg-parser.h		\
	cfg-tree.h		\
	children.h		\
	compat.h		\
	control.h		\
	crypto.h		\
	dnscache.h		\
	driver.h		\
	file-perms.h		\
	filter-expr-parser.h	\
	filter.h		\
	gprocess.h		\
	gsockaddr.h		\
	gsocket.h		\
	logmatcher.h		\
	logmpx.h		\
	logmsg.h		\
	logparser.h		\
	logpipe.h		\
	logproto.h		\
	logqueue-fifo.h		\
	logqueue.h		\
	logreader.h		\
	logrewrite.h		\
	logsource.h		\
	logstamp.h		\
	logtransport.h		\
	logwriter.h		\
	mainloop.h		\
	memtrace.h		\
	messages.h		\
	misc.h			\
	msg-format.h		\
	nvtable.h		\
	parser-expr-parser.h	\
	persist-state.h		\
	plugin.h		\
	pragma-parser.h		\
	rewrite-expr-parser.h	\
	scratch-buffers.h	\
	serialize.h		\
	stats.h			\
	str-format.h		\
	syslog-names.h		\
	syslog-ng.h		\
	tags.h			\
	templates.h		\
	timeutils.h		\
	tls-support.h		\
	tlscontext.h  		\
	tlstransport.h		\
	utils.h			\
	uuid.h			\
	value-pairs.h		\
	vptransform.h		\
	versioning.h

# this is intentionally formatted so conflicts are less likely to arise. one name in every line.
libsyslog_ng_crypto_la_SOURCES = \
	crypto.c		\
	tlscontext.c		\
	tlstransport.c		\
	uuid.c

# this is intentionally formatted so conflicts are less likely to arise. one name in every line.
libsyslog_ng_la_SOURCES = \
	afinter.c		\
	alarms.c		\
	apphook.c		\
	block-ref-parser.c	\
	cfg.c			\
	cfg-lexer.c		\
	cfg-parser.c		\
	cfg-tree.c		\
	children.c		\
	compat.c		\
	control.c		\
	dnscache.c		\
	driver.c		\
	file-perms.c		\
	filter.c		\
	filter-expr-parser.c	\
	globals.c		\
	gprocess.c		\
	gsockaddr.c		\
	gsocket.c		\
	logmatcher.c		\
	logmpx.c		\
	logmsg.c		\
	logparser.c		\
	logpipe.c		\
	logproto.c		\
	logqueue.c		\
	logqueue-fifo.c		\
	logreader.c		\
	logrewrite.c		\
	logsource.c		\
	logstamp.c		\
	logtransport.c		\
	logwriter.c		\
	mainloop.c		\
	memtrace.c		\
	messages.c		\
	misc.c			\
	msg-format.c		\
	nvtable.c		\
	parser-expr-parser.c	\
	persist-state.c		\
	plugin.c		\
	pragma-parser.c		\
	rewrite-expr-parser.c	\
	scratch-buffers.c	\
	serialize.c		\
	stats.c			\
	str-format.c		\
	syslog-names.c		\
	tags.c			\
	templates.c		\
	timeutils.c		\
	utils.c			\
	value-pairs.c		\
	vptransform.c		\
				\
	cfg-lex.l		\
	cfg-grammar.y		\
	filter-expr-grammar.y	\
	block-ref-grammar.y	\
	pragma-grammar.y	\
	parser-expr-grammar.y	\
	rewrite-expr-grammar.y

# each line with closely related files (e.g. the ones generated from the same source)
BUILT_SOURCES = cfg-lex.c cfg-lex.h						\
	cfg-grammar.c cfg-grammar.h						\
	filter-expr-grammar.y filter-expr-grammar.c filter-expr-grammar.h	\
	block-ref-grammar.y block-ref-grammar.c block-ref-grammar.h		\
	pragma-grammar.y pragma-grammar.h pragma-grammar.c			\
	parser-expr-grammar.y parser-expr-grammar.c parser-expr-grammar.h	\
	rewrite-expr-grammar.y rewrite-expr-grammar.c rewrite-expr-grammar.h

EXTRA_DIST = $(BUILT_SOURCES) \
	filter-expr-grammar.ym		\
	block-ref-grammar.ym		\
	pragma-grammar.ym		\
	parser-expr-grammar.ym		\
	rewrite-expr-grammar.ym		\
	merge-grammar.pl

CLEAN_FILES = $(BUILT_SOURCES)

# divert install/uninstall targets to avoid recursing into $(SUBDIRS)

install:
	$(MAKE) $(AM_MAKEFLAGS) all
	$(MAKE) $(AM_MAKEFLAGS) install-am

uninstall:
	$(MAKE) $(AM_MAKEFLAGS) uninstall-am

include $(top_srcdir)/build/lex-rules.am
