+++
# A Demo section created with the Blank widget.
# Any elements can be added in the body: https://sourcethemes.com/academic/docs/writing-markdown-latex/
# Add more sections by duplicating this file and customizing to your requirements.

widget = "blank"  # See https://sourcethemes.com/academic/docs/page-builder/
headless = true  # This file represents a page section.
active = true  # Activate this widget? true/false
weight = 25  # Order that this section will appear.

title = "All Processes"
subtitle = ""

[design]
  # Choose how many columns the section has. Valid values: 1 or 2.
  columns = "1"

[design.background]
  # Apply a background color, gradient, or image.
  #   Uncomment (by removing `#`) an option to apply it.
  #   Choose a light or dark text color by setting `text_color_light`.
  #   Any HTML color name or Hex value is valid.

  # Background color.
  # color = "navy"
  
  # Background gradient.
  # gradient_start = "DarkGreen"
  # gradient_end = "ForestGreen"
  
  # Background image.
  # image = "image.jpg"  # Name of image in `static/img/`.
  # image_darken = 0.6  # Darken the image? Range 0-1 where 0 is transparent and 1 is opaque.
  # image_size = "cover"  #  Options are `cover` (default), `contain`, or `actual` size.
  # image_position = "center"  # Options include `left`, `center` (default), or `right`.
  # image_parallax = true  # Use a fun parallax-like fixed background effect? true/false
  
  # Text color (true=light or false=dark).
  text_color_light = false

[design.spacing]
  # Customize the section spacing. Order is top, right, bottom, left.
  padding = ["20px", "0", "20px", "0"]

[advanced]
 # Custom CSS. 
 css_style = ""
 
 # CSS class.
 css_class = ""
+++
These are the processes running on a default install of Ubuntu Server 18.04.4.
The only non-default I took was to run sshd so I could log in and get this list.
### ps -ef 
`/sbin/init maybe-ubiquity` the one true [process to start them all](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/6/html/installation_guide/s2-boot-init-shutdown-init) the [maybe-ubiquity](https://askubuntu.com/questions/1165399/why-maybe-ubiquity-on-default-kernel-command-line) part is from GRUB     
`[kthreadd]` [kernel thread master](https://subscription.packtpub.com/book/application_development/9781785883057/1/ch01lvl1sec13/kernel-threads) for spawning off processes largely to manage hardware. Kthread processes are shown in [square brackets].   
`[kworker/0:0H]` a [kernel worker thread placeholder](https://askubuntu.com/questions/33640/kworker-what-is-it-and-why-is-it-hogging-so-much-cpu)    
`[mm_percpu_wq]` wow! really not a lot about the memory management per cpu work queue thread, other than [cryptic messages in the kernel maintainers list](https://gitlab.collabora.com/tcl/linux/commit/ce612879ddc78ea7e4de4be80cba4ebf9caa07ee)   
`[ksoftirqd/0]` a way of [handling hardware interrupt requests](https://www.supportsages.com/what-does-ksoftirqd-do/) outside a regular handler   
`[rcu_sched]` the [Read Copy Update scheduler](https://www.quora.com/What-is-the-purpose-of-rcu_sched-Linux-Kernel-Thread) that synchronizes data across writer and readers   
`[rcu_bh]` a cousin of the rcu_sched above, it provides [grace periods](https://www.quora.com/What-is-the-purpose-of-rcu_bh-Linux-Kernel-Thread) in the RCU subsystem.   
`[migration/0]` [Distributes processes across cores](https://superuser.com/questions/440906/what-is-the-migration-process). One such process per core.
`[watchdog/0]` Checks to [ensure the system's still running](https://linuxhint.com/linux-kernel-watchdog-explained/), and reboots if hung, hopefully.   
`[cpuhp/0]` Process that supports [physically adding and removing CPUs](https://www.kernel.org/doc/html/latest/core-api/cpu_hotplug.html) from the system.   
`[cpuhp/1]` [lscpu](https://linux.die.net/man/1/lscpu) says this machine has 4 cores, so these one-per-core kernel threads are repeated with different /n suffixes    
`[watchdog/1]` ditto   
`[migration/1]` ditto   
`[ksoftirqd/1]` ditto   
`[kworker/1:0H]` ditto   
`[cpuhp/2]` ditto   
`[watchdog/2]` ditto   
`[migration/2]` ditto   
`[ksoftirqd/2]` ditto   
`[kworker/2:0H]` ditto   
`[cpuhp/3]` ditto   
`[watchdog/3]` ditto   
`[migration/3]` ditto   
`[ksoftirqd/3]` ditto   
`[kworker/3:0H]` ditto   
`[kdevtmpfs]` this thread [populates and maintains](https://www.spinics.net/lists/selinux/msg17455.html) a device node tree    
`[netns]` this maintains the [network namespace](https://blogs.igalia.com/dpino/2016/04/10/network-namespaces/)   
`[rcu_tasks_kthre]` clearly a part of the Read Copy Update subsystem, but I'll be hanged if I can find ANYTHING about this thread on the web.    
`[kauditd]` the kernel thread responsible for [auditing security events](https://wiki.gentoo.org/wiki/SELinux/Tutorials/The_security_context_of_a_process)   
`[kworker/1:1]` another kernel thread placeholder, see above   
`[khungtaskd]` [looks for hung tasks](https://www.quora.com/What-is-the-purpose-of-khungtaskd-Linux-Kernel-Daemon) every two minutes   
`[oom_reaper]` cleans up [processes that are Out Of Memory](https://lwn.net/Articles/666024/).   
`[writeback]` handles [slow writes](https://lwn.net/Articles/682582/) to block devices   
`[kcompactd0]` handles background [memory compaction](https://www.linux-magazine.com/Issues/2015/179/Kernel-News)   
`[ksmd]` [kernel samepage merging](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/virtualization_tuning_and_optimization_guide/chap-ksm) daemon, used by the KVM hypervisor.    
`[khugepaged]` keeps track of [huge virtual memory pages](https://www.quora.com/What-is-the-purpose-of-khugepaged-Linux-Kernel-Daemon) efficiently    
`[crypto]` [provides an API interface](https://www.quora.com/What-is-the-purpose-of-crypto-Linux-Kernel-Thread) to the kernel crypto module   
`[kintegrityd]` [checks the integrity](https://unix.stackexchange.com/questions/337104/what-is-kintegrityd-and-why-it-has-20-nice-value) of block devices by writing/reading data to and from them.   
`[kblockd]` [checks for congestion](https://www.quora.com/What-is-the-purpose-of-kblockd-Linux-Kernel-Thread) in I/O pipes   
`[kworker/3:1]` another generic kernel thread, see above.   
`[kworker/2:1]` ditto   
`[ata_sff]` handles [ATA Small Form Factor](https://cateee.net/lkddb/web-lkddb/ATA_SFF.html) interfaces   
`[md]` handles [multiple device](https://www.linuxquestions.org/questions/slackware-14/md-process-208982/) interfaces, e.g. RAID arrays   
`[edac-poller]` handles [memory error detection and correction](https://www.kernel.org/doc/html/v4.13/driver-api/edac.html)    
`[devfreq_wq]` apparently allows for the [reuse of frequently-used kernel workqueues](https://lore.kernel.org/patchwork/patch/1164316/)   
`[watchdogd]` probably has something to do with the [watchdog thread](http://www.crawford-space.co.uk/old_psc/watchdog/watchdog-background.html). This is another one with almost no documentation.   
`[kswapd0]` The [manager of virtual memory](https://askubuntu.com/questions/259739/kswapd0-is-taking-a-lot-of-cpu). An ancient and venerable subsystem.   
`[kworker/u33:0]` Another generic kernel thread ready to be used. See above.   
`[ecryptfs-kthrea]` This [encrypts and decrypts](https://www.quora.com/Linux-Kernel-What-is-the-purpose-of-ecryptfs-kthrea-Kernel-Thread) data passing out to the filesystem.    
`[kthrotld]` Controls bandwidth on a request queue by [throttling requests](https://askubuntu.com/questions/986526/what-is-kthrotld)    
`[acpi_thermal_pm]` Provides an API interface to the ACPI to provider [thermal management](https://wiki.ubuntu.com/Kernel/PowerManagement/ThermalIssues)   
`[ipv6_addrconf]` handles the IPv6 [configuration workqueue](https://github.com/torvalds/linux/blob/master/net/ipv6/addrconf.c)   
`[kstrp]` the [Kernel Stream Processor](https://www.kernel.org/doc/Documentation/networking/strparser.txt)   
`[kworker/2:2]` another worker thread placeholder, see the first one above   
`[charger_manager]` about what you'd expect: a [battery charger manager](https://www.kernel.org/doc/html/latest/power/charger-manager.html)   
`[scsi_eh_0]` Linux boxes almost never have SCSI disks anymore. This is the handles errors from [other types of disks](http://events17.linuxfoundation.org/sites/events/files/slides/SCSI-EH.pdf) that appear as SCSI   
`[scsi_tmf_0]` handles disk [Task Mangement Functions](https://www.t10.org/ftp/t10/document.06/06-179r0.pdf)   
`[scsi_eh_1]` same as above for the next disk   
`[scsi_tmf_1]` ditto  
`[scsi_eh_2]` ditto  
`[scsi_tmf_2]` ditto  
`[scsi_eh_3]` ditto   
`[scsi_tmf_3]` ditto   
`[scsi_eh_4]` ditto   
`[scsi_tmf_4]` ditto   
`[scsi_eh_5]` ditto   
`[scsi_tmf_5]` ditto   
`[e1000e]` Handles the [Intel Gigabit Ethernet](https://www.intel.com/content/www/us/en/support/articles/000005480/network-and-i-o/ethernet-products.html) devices   
`[i915/signal:0]` Handles the [Intel i915 Graphics](https://www.kernel.org/doc/html/v4.14/gpu/i915.html) drivers   
`[i915/signal:1]` ditto   
`[i915/signal:2]` ditto   
`[kworker/3:1H]` another placeholder thread   
`[raid5wq]` Probably a RAID5 driver, can't find any info on it.   
`[jbd2/sda2-8]` Updates the [filesystem journal](https://unix.stackexchange.com/questions/343591/why-is-most-the-of-disk-io-attributed-to-jbd2-and-not-to-the-process-that-is-act)   
`[ext4-rsv-conver]` Handles [writeback conversion work](https://unix.stackexchange.com/questions/463210/some-documentation-for-the-ext4-rsv-conver-process) from the ext4 filesystem.   
`[kworker/0:1H]` another placeholder thread   
`[kworker/1:1H]` another placeholder thread  
`[kworker/2:1H]` another placeholder thread  
`/lib/systemd/systemd-journald` and into userland! this is the process that [collects logging data](https://www.freedesktop.org/software/systemd/man/systemd-journald.service.html)   
`[iscsi_eh]` Can't find much info on this one either, probably the [iSCSI error handler](https://sourceforge.net/p/scst/mailman/message/30629304/)   
`/sbin/lvmetad -f` The Logical Volume Manager [metadata caching process](https://unix.stackexchange.com/questions/166832/what-is-lvmetad-and-why-would-i-want-or-need-to-use-it)   
`[ib-comp-wq]` Found one reference to it in the kernel mailing list. It has to do with the InfiniBand driver, and it's now [cpu-bound](https://lwn.net/Articles/718114/)   
`[ib-comp-unb-wq]` Dealing with the [InfiniBand WorkQueue](https://gitlab.freedesktop.org/lyudess/linux/commit/5c5702e259dc66e6fceed5117effab79c186e87a)   
`[ib_mcast]` Handling [InfiniBand Multicast groups](https://dox.ipxe.org/ib__mcast_8c.html)   
`[ib_nl_sa_wq]` No info on this one, either. Some InfiniBand WorkQueue   
`[rdma_cm]` [Remote Direct Memory Access](https://wiki.debian.org/RDMA), usually part of InfiniBand   
`/lib/systemd/systemd-udevd` The part of systemd that handles [devices coming and going](http://man7.org/linux/man-pages/man8/systemd-udevd.service.8.html)   
`/lib/systemd/systemd-timesyncd` The systemd way of [synchronizing the system clock](https://feeding.cloud.geek.nz/posts/time-synchronization-with-ntp-and-systemd/) to an external timekeeper. The supposedly better replacement for ntpd.    
`[irq/27-mei_me]` One of the daemons that handles [IRQ interrupts](https://linuxmusicians.com/viewtopic.php?t=19065&start=15)   
`/lib/systemd/systemd-networkd` The part of the systemd juggernaut that [handles networking](https://wiki.archlinux.org/index.php/Systemd-networkd)   
`/lib/systemd/systemd-resolved` The systemd [Domain Name Service resolution manager](https://www.freedesktop.org/software/systemd/man/systemd-resolved.service.html)   
`/usr/sbin/atd -f` One of the few old-timers left: The [at daemon](https://www.lifewire.com/atd-linux-command-4095628) that handles one-time delayed job execution   
`/usr/bin/lxcfs /var/lib/lxcfs/` Manages [filesystems for fuse containers](https://ubuntu.com/blog/introducing-lxcfs)   
`/usr/sbin/rsyslogd -n` The [remote system logger](http://man7.org/linux/man-pages/man8/rsyslogd.8.html) daemon.   
`/usr/bin/python3 /usr/bin/networkd-dispatcher --run-startup-triggers` Handles [changes to the systemd-networkd](http://manpages.ubuntu.com/manpages/bionic/man8/networkd-dispatcher.8.html)   
`/usr/bin/dbus-daemon --system --address=systemd: --nofork --nopidfile --systemd-activation --syslog-only` The [Dbus message bus daemon](https://dbus.freedesktop.org/doc/dbus-daemon.1.html) without which there would be no systemd functionality   
`/usr/sbin/cron -f` An old subsystem I've used for decades: the [cron daemon](https://linuxacademy.com/blog/linux/the-cron-daemon/) for regularly scheduled tasks   
`/usr/lib/accountsservice/accounts-daemon` Provides Dbus interface to [modifiying account information](http://forums.debian.net/viewtopic.php?f=5&t=129556)   
`/usr/sbin/thermald --no-daemon --dbus-enable` The user-land deamon to [monitor the system's heat](https://wiki.debian.org/thermald)   
`/lib/systemd/systemd-logind` About what it appears it [handles the login process](https://www.freedesktop.org/software/systemd/man/systemd-logind.service.html). Gone are the gettys.   
`/usr/sbin/irqbalance --foreground` [Distributes IRQs among the processors](https://www.thegeekdiary.com/linux-os-service-irqbalance/)   
`/usr/lib/policykit-1/polkitd --no-debug` Facilitates letting [unprivileged processes talk to privileged](https://wiki.archlinux.org/index.php/Polkit) ones.   
`/usr/bin/python3 /usr/share/unattended-upgrades/unattended-upgrade-shutdown --wait-for-signal` Keeps the [system from shutting down while software is being updated](https://askubuntu.com/questions/1098757/ubuntu-18-10-unattended-upgrades-shutdown-wait-for-signal)   
`/bin/login -p --` The actual [login process](https://linux.die.net/man/1/login) that manages a user login   
`[loop0]` Not much information about this either. Possibly a [loopback filesystem thread](http://linux-vserver.org/Loop_Device)?   
`[kworker/0:6]` another placeholder thread    
`[kworker/0:7]` ditto  
`/usr/lib/snapd/snapd` The runner for the [Snap packages](https://wiki.archlinux.org/index.php/Snap)   
`/lib/systemd/systemd --user` The user-land [heart of systemd](https://www.linux.com/tutorials/understanding-and-using-systemd/)   
`(sd-pam)` a [helper process for the Pluggable Authentication Module](https://systemd-devel.freedesktop.narkive.com/nWBQzgXB/systemd-user-and-sd-pam-user-processes-in-login-shell) system   
`-bash` What I'm using now, the [Bourne-again Shell](https://www.gnu.org/software/bash/)   
`/usr/sbin/sshd -D` The [Secure Shell server process](https://www.ssh.com/ssh/sshd)   
`[kworker/1:2]` another placeholder thread   
`[kworker/3:2]` ditto  
`[kworker/u32:0]` ditto  
`[kworker/u32:2]` ditto  
`[kworker/u32:1]` ditto  
`[kworker/1:0]` ditto  
`[kworker/3:0]` ditto  
`ps -ef` List the status of [all processes](http://man7.org/linux/man-pages/man1/ps.1.html)   
