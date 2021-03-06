# Makefile for virt-what
# Copyright (C) 2008-2011 Red Hat Inc.
#
# This program is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; either version 2 of the License, or
# (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software
# Foundation, Inc., 675 Mass Ave, Cambridge, MA 02139, USA.

CLEANFILES = virt-what

AM_CPPFLAGS = -Wall

sbin_SCRIPTS = virt-what
libexec_PROGRAMS = virt-what-cpuid-helper
if HOST_CPU_IA64
libexec_PROGRAMS += virt-what-ia64-xen-rdtsc-test
endif

if HAVE_POD2MAN

CLEANFILES += virt-what.1 virt-what.txt
man_MANS = virt-what.1

virt-what.1: virt-what.pod
	pod2man -c "Virtualization Support" --release "$(PACKAGE)-$(VERSION)" \
	  $? > $@
virt-what.txt: virt-what.pod
	pod2text $? > $@

endif

TESTS = \
	tests/test-aws-baremetal-x86.sh \
	tests/test-aws-kvm-x86.sh \
	tests/test-aws-xen-x86.sh \
	tests/test-baremetal.sh \
	tests/test-bhyve.sh \
	tests/test-docker.sh \
	tests/test-esx4.1.sh \
	tests/test-hyperv.sh \
	tests/test-kvm.sh \
	tests/test-kvm-explicit-cpu.sh \
	tests/test-linux-vserver.sh \
	tests/test-ldoms.sh \
	tests/test-lkvm.sh \
	tests/test-lkvm-arm.sh \
	tests/test-lxc.sh \
	tests/test-lx86.sh \
	tests/test-parallels-desktop.sh \
	tests/test-ppc64-baremetal.sh \
	tests/test-ppc64-kvm.sh \
	tests/test-ppc64-lpar-dedicated.sh \
	tests/test-ppc64-lpar-shared.sh \
	tests/test-qemu.sh \
	tests/test-qemu-arm.sh \
	tests/test-qemu-smbios.sh \
	tests/test-qemu-smbios-kvm.sh \
	tests/test-rhel5-xen-dom0.sh \
	tests/test-rhel5-xen-domU-hvm.sh \
	tests/test-rhel5-xen-domU-hvm-ia64.sh \
	tests/test-rhel5-xen-domU-pv.sh \
	tests/test-rhev.sh \
	tests/test-vmm.sh \
	tests/test-xen-arm.sh \
	tests/test-zvm.sh

EXTRA_DIST = \
	virt-what.in \
	virt-what.pod \
	tests/aws-baremetal-x86/proc/cpuinfo \
	tests/aws-baremetal-x86/proc/self/status \
	tests/aws-baremetal-x86/sbin/dmidecode \
	tests/aws-baremetal-x86/sbin/uname \
	tests/aws-baremetal-x86/sbin/virt-what-cpuid-helper \
	tests/aws-kvm-x86/proc/cpuinfo \
	tests/aws-kvm-x86/proc/self/status \
	tests/aws-kvm-x86/sbin/dmidecode \
	tests/aws-kvm-x86/sbin/uname \
	tests/aws-kvm-x86/sbin/virt-what-cpuid-helper \
	tests/aws-xen-x86/proc/cpuinfo \
	tests/aws-xen-x86/proc/self/status \
	tests/aws-xen-x86/sbin/dmidecode \
	tests/aws-xen-x86/sbin/uname \
	tests/aws-xen-x86/sbin/virt-what-cpuid-helper \
	tests/baremetal/proc/cpuinfo \
	tests/baremetal/proc/self/status \
	tests/baremetal/sbin/dmidecode \
	tests/baremetal/sbin/uname \
	tests/baremetal/sbin/virt-what-cpuid-helper \
	tests/bhyve/proc/cpuinfo \
	tests/bhyve/sbin/dmidecode \
	tests/bhyve/sbin/uname \
	tests/bhyve/sbin/virt-what-cpuid-helper \
	tests/docker/.dockerinit \
	tests/docker/proc/cpuinfo \
	tests/docker/proc/self/status \
	tests/docker/sbin/dmidecode \
	tests/docker/sbin/uname \
	tests/docker/sbin/virt-what-cpuid-helper \
	tests/esx4.1/proc/cpuinfo \
	tests/esx4.1/proc/self/status \
	tests/esx4.1/sbin/dmidecode \
	tests/esx4.1/sbin/uname \
	tests/esx4.1/sbin/virt-what-cpuid-helper \
	tests/hyperv/proc/cpuinfo \
	tests/hyperv/proc/self/status \
	tests/hyperv/sbin/dmidecode \
	tests/hyperv/sbin/uname \
	tests/hyperv/sbin/virt-what-cpuid-helper \
	tests/kvm/proc/cpuinfo \
	tests/kvm/proc/self/status \
	tests/kvm/sbin/dmidecode \
	tests/kvm/sbin/uname \
	tests/kvm/sbin/virt-what-cpuid-helper \
	tests/kvm-explicit-cpu/proc/cpuinfo \
	tests/kvm-explicit-cpu/proc/self/status \
	tests/kvm-explicit-cpu/sbin/dmidecode \
	tests/kvm-explicit-cpu/sbin/uname \
	tests/kvm-explicit-cpu/sbin/virt-what-cpuid-helper \
	tests/ldoms/dev/mdesc \
	tests/ldoms/proc/cpuinfo \
	tests/ldoms/sbin/uname \
	tests/ldoms/sbin/virt-what-cpuid-helper \
	tests/linux-vserver/proc/cpuinfo \
	tests/linux-vserver/proc/self/status \
	tests/linux-vserver/sbin/dmidecode \
	tests/linux-vserver/sbin/uname \
	tests/linux-vserver/sbin/virt-what-cpuid-helper \
	tests/lkvm/proc/cpuinfo \
	tests/lkvm/proc/self/status \
	tests/lkvm/sbin/dmidecode \
	tests/lkvm/sbin/uname \
	tests/lkvm/sbin/virt-what-cpuid-helper \
	tests/lkvm-arm/proc/cpuinfo \
	tests/lkvm-arm/proc/device-tree/compatible \
	tests/lkvm-arm/proc/self/status \
	tests/lkvm-arm/sbin/dmidecode \
	tests/lkvm-arm/sbin/uname \
	tests/lkvm-arm/sbin/virt-what-cpuid-helper \
	tests/lxc/proc/1/environ \
	tests/lxc/proc/cpuinfo \
	tests/lxc/proc/self/status \
	tests/lxc/sbin/dmidecode \
	tests/lxc/sbin/uname \
	tests/lxc/sbin/virt-what-cpuid-helper \
	tests/lx86/proc/cpuinfo \
	tests/lx86/proc/self/status \
	tests/lx86/sbin/dmidecode \
	tests/lx86/sbin/uname \
	tests/lx86/sbin/virt-what-cpuid-helper \
	tests/parallels-desktop/proc/cpuinfo \
	tests/parallels-desktop/proc/self/status \
	tests/parallels-desktop/sbin/dmidecode \
	tests/parallels-desktop/sbin/uname \
	tests/parallels-desktop/sbin/virt-what-cpuid-helper \
	tests/ppc64-baremetal/proc/cpuinfo \
	tests/ppc64-baremetal/sbin/dmidecode \
	tests/ppc64-baremetal/sbin/uname \
	tests/ppc64-baremetal/sbin/virt-what-cpuid-helper \
	tests/ppc64-kvm/proc/cpuinfo \
	tests/ppc64-kvm/proc/self/status \
	tests/ppc64-kvm/sbin/dmidecode \
	tests/ppc64-kvm/sbin/uname \
	tests/ppc64-kvm/sbin/virt-what-cpuid-helper \
	tests/ppc64-lpar-dedicated/proc/cpuinfo \
	tests/ppc64-lpar-dedicated/proc/ppc64/lparcfg \
	tests/ppc64-lpar-dedicated/sbin/dmidecode \
	tests/ppc64-lpar-dedicated/sbin/uname \
	tests/ppc64-lpar-dedicated/sbin/virt-what-cpuid-helper \
	tests/ppc64-lpar-shared/sbin/dmidecode \
	tests/ppc64-lpar-shared/sbin/uname \
	tests/ppc64-lpar-shared/sbin/virt-what-cpuid-helper \
	tests/ppc64-lpar-shared/proc/cpuinfo \
	tests/ppc64-lpar-shared/proc/self/status \
	tests/ppc64-lpar-shared/proc/ppc64/lparcfg \
	tests/ppc64-lpar-shared/sbin/dmidecode \
	tests/ppc64-lpar-shared/sbin/uname \
	tests/ppc64-lpar-shared/sbin/virt-what-cpuid-helper \
	tests/qemu/proc/cpuinfo \
	tests/qemu/proc/self/status \
	tests/qemu/sbin/dmidecode \
	tests/qemu/sbin/uname \
	tests/qemu/sbin/virt-what-cpuid-helper \
	tests/qemu-arm/proc/cpuinfo \
	tests/qemu-arm/proc/device-tree/fw-cfg@9020000/compatible \
	tests/qemu-arm/proc/self/status \
	tests/qemu-arm/sbin/dmidecode \
	tests/qemu-arm/sbin/uname \
	tests/qemu-arm/sbin/virt-what-cpuid-helper \
	tests/qemu-smbios/proc/cpuinfo \
	tests/qemu-smbios/proc/self/status \
	tests/qemu-smbios/sbin/dmidecode \
	tests/qemu-smbios/sbin/uname \
	tests/qemu-smbios/sbin/virt-what-cpuid-helper \
	tests/qemu-smbios-kvm/proc/cpuinfo \
	tests/qemu-smbios-kvm/proc/self/status \
	tests/qemu-smbios-kvm/sbin/dmidecode \
	tests/qemu-smbios-kvm/sbin/uname \
	tests/qemu-smbios-kvm/sbin/virt-what-cpuid-helper \
	tests/rhel5-xen-dom0/proc/cpuinfo \
	tests/rhel5-xen-dom0/proc/self/status \
	tests/rhel5-xen-dom0/proc/xen/balloon \
	tests/rhel5-xen-dom0/proc/xen/capabilities \
	tests/rhel5-xen-dom0/proc/xen/privcmd \
	tests/rhel5-xen-dom0/proc/xen/xenbus \
	tests/rhel5-xen-dom0/proc/xen/xsd_kva \
	tests/rhel5-xen-dom0/proc/xen/xsd_port \
	tests/rhel5-xen-dom0/sbin/dmidecode \
	tests/rhel5-xen-dom0/sbin/uname \
	tests/rhel5-xen-dom0/sbin/virt-what-cpuid-helper \
	tests/rhel5-xen-dom0/sys/hypervisor/properties/pagesize \
	tests/rhel5-xen-dom0/sys/hypervisor/properties/changeset \
	tests/rhel5-xen-dom0/sys/hypervisor/properties/virtual_start \
	tests/rhel5-xen-dom0/sys/hypervisor/properties/capabilities \
	tests/rhel5-xen-dom0/sys/hypervisor/properties/writable_pt \
	tests/rhel5-xen-dom0/sys/hypervisor/type \
	tests/rhel5-xen-dom0/sys/hypervisor/vmcoreinfo \
	tests/rhel5-xen-dom0/sys/hypervisor/version/minor \
	tests/rhel5-xen-dom0/sys/hypervisor/version/major \
	tests/rhel5-xen-dom0/sys/hypervisor/version/extra \
	tests/rhel5-xen-dom0/sys/hypervisor/compilation/compiler \
	tests/rhel5-xen-dom0/sys/hypervisor/compilation/compiled_by \
	tests/rhel5-xen-dom0/sys/hypervisor/compilation/compile_date \
	tests/rhel5-xen-dom0/sys/hypervisor/uuid \
	tests/rhel5-xen-domU-hvm/proc/cpuinfo \
	tests/rhel5-xen-domU-hvm/proc/self/status \
	tests/rhel5-xen-domU-hvm/sbin/dmidecode \
	tests/rhel5-xen-domU-hvm/sbin/uname \
	tests/rhel5-xen-domU-hvm/sbin/virt-what-cpuid-helper \
	tests/rhel5-xen-domU-hvm-ia64/proc/cpuinfo \
	tests/rhel5-xen-domU-hvm-ia64/proc/self/status \
	tests/rhel5-xen-domU-hvm-ia64/sbin/dmidecode \
	tests/rhel5-xen-domU-hvm-ia64/sbin/uname \
	tests/rhel5-xen-domU-hvm-ia64/sbin/virt-what-cpuid-helper \
	tests/rhel5-xen-domU-hvm-ia64/sys/bus/xen/drivers/vbd/bind \
	tests/rhel5-xen-domU-hvm-ia64/sys/bus/xen/drivers/vbd/unbind \
	tests/rhel5-xen-domU-hvm-ia64/sys/bus/xen/drivers/vif/bind \
	tests/rhel5-xen-domU-hvm-ia64/sys/bus/xen/drivers/vif/unbind \
	tests/rhel5-xen-domU-hvm-ia64/sys/bus/xen/drivers_probe \
	tests/rhel5-xen-domU-pv/proc/cpuinfo \
	tests/rhel5-xen-domU-pv/proc/self/status \
	tests/rhel5-xen-domU-pv/proc/xen/balloon \
	tests/rhel5-xen-domU-pv/proc/xen/capabilities \
	tests/rhel5-xen-domU-pv/proc/xen/privcmd \
	tests/rhel5-xen-domU-pv/proc/xen/xenbus \
	tests/rhel5-xen-domU-pv/sbin/dmidecode \
	tests/rhel5-xen-domU-pv/sbin/uname \
	tests/rhel5-xen-domU-pv/sbin/virt-what-cpuid-helper \
	tests/rhel5-xen-domU-pv/sys/hypervisor/properties/pagesize \
	tests/rhel5-xen-domU-pv/sys/hypervisor/properties/changeset \
	tests/rhel5-xen-domU-pv/sys/hypervisor/properties/virtual_start \
	tests/rhel5-xen-domU-pv/sys/hypervisor/properties/capabilities \
	tests/rhel5-xen-domU-pv/sys/hypervisor/properties/writable_pt \
	tests/rhel5-xen-domU-pv/sys/hypervisor/type \
	tests/rhel5-xen-domU-pv/sys/hypervisor/vmcoreinfo \
	tests/rhel5-xen-domU-pv/sys/hypervisor/version/minor \
	tests/rhel5-xen-domU-pv/sys/hypervisor/version/major \
	tests/rhel5-xen-domU-pv/sys/hypervisor/version/extra \
	tests/rhel5-xen-domU-pv/sys/hypervisor/compilation/compiler \
	tests/rhel5-xen-domU-pv/sys/hypervisor/compilation/compiled_by \
	tests/rhel5-xen-domU-pv/sys/hypervisor/compilation/compile_date \
	tests/rhel5-xen-domU-pv/sys/hypervisor/uuid \
	tests/rhev/proc/cpuinfo \
	tests/rhev/proc/self/status \
	tests/rhev/sbin/dmidecode \
	tests/rhev/sbin/uname \
	tests/rhev/sbin/virt-what-cpuid-helper \
	tests/vmm/proc/cpuinfo \
	tests/vmm/sbin/dmidecode \
	tests/vmm/sbin/uname \
	tests/vmm/sbin/virt-what-cpuid-helper \
	tests/xen-arm/proc/cpuinfo \
	tests/xen-arm/proc/device-tree/hypervisor/compatible \
	tests/xen-arm/proc/self/status \
	tests/xen-arm/sbin/dmidecode \
	tests/xen-arm/sbin/uname \
	tests/xen-arm/sbin/virt-what-cpuid-helper \
	tests/zvm/proc/cpuinfo \
	tests/zvm/proc/self/status \
	tests/zvm/proc/sysinfo \
	tests/zvm/sbin/dmidecode \
	tests/zvm/sbin/uname \
	tests/zvm/sbin/virt-what-cpuid-helper \
	$(TESTS)
