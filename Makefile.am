ACLOCAL_AMFLAGS = -I m4

opdir		 = $(datadir)/vyatta-op/templates

bin_sudo_usersdir = $(bindir)/sudo-users
share_perl5dir	 = $(datarootdir)/perl5/Vyatta/VPN
share_perl5_vpnprofdir   = $(datarootdir)/perl5/Vyatta/vpnprof

share_perl5_DATA = lib/OPMode.pm
share_perl5_vpnprof_DATA = lib/vpnprof/OPMode.pm

bin_sudo_users_SCRIPTS = scripts/gen_local_rsa_key.pl
bin_sudo_users_SCRIPTS += scripts/vyatta-show-vpn.pl
bin_sudo_users_SCRIPTS += scripts/vyatta-vpn-op.pl
bin_sudo_users_SCRIPTS += scripts/vyatta-dmvpn-op.pl
bin_sudo_users_SCRIPTS += scripts/vyatta-op-vpn.pl
bin_sudo_users_SCRIPTS += scripts/vyatta-op-vpnprof.pl
bin_sudo_users_SCRIPTS += scripts/vyatta-show-ipsec-status.pl

cpiop = find  . ! -regex '\(.*~\|.*\.bak\|.*\.swp\|.*\#.*\#\)' -print0 | \
	cpio -0pd

install-exec-hook:
	mkdir -p $(DESTDIR)${sysconfdir} $(DESTDIR)${sbindir} $(DESTDIR)$(opdir)
	cp scripts/vyatta-gen-x509-keypair $(DESTDIR)${sbindir}/
	cp scripts/key-pair.template $(DESTDIR)${sysconfdir}
	cd templates; $(cpiop) $(DESTDIR)$(opdir)


