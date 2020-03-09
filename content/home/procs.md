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
`[ecryptfs-kthrea]`   
`[kthrotld]`   
`[acpi_thermal_pm]`   
`[ipv6_addrconf]`   
`[kstrp]`   
`[kworker/2:2]`   
`[charger_manager]`   
`[scsi_eh_0]`   
`[scsi_tmf_0]`   
`[scsi_eh_1]`   
`[scsi_tmf_1]`   
`[scsi_eh_2]`   
`[scsi_tmf_2]`   
`[scsi_eh_3]`   
`[scsi_tmf_3]`   
`[scsi_eh_4]`   
`[scsi_tmf_4]`   
`[scsi_eh_5]`   
`[scsi_tmf_5]`   
`[e1000e]`   
`[i915/signal:0]`   
`[i915/signal:1]`   
`[i915/signal:2]`   
`[kworker/3:1H]`   
`[raid5wq]`   
`[jbd2/sda2-8]`   
`[ext4-rsv-conver]`   
`[kworker/0:1H]`   
`[kworker/1:1H]`   
`[kworker/2:1H]`   
`/lib/systemd/systemd-journald`   
`[iscsi_eh]`   
`/sbin/lvmetad -f`   
`[ib-comp-wq]`   
`[ib-comp-unb-wq]`   
`[ib_mcast]`   
`[ib_nl_sa_wq]`   
`[rdma_cm]`   
`/lib/systemd/systemd-udevd`   
`/lib/systemd/systemd-timesyncd`   
`[irq/27-mei_me]`   
`/lib/systemd/systemd-networkd`   
`/lib/systemd/systemd-resolved`   
`/usr/sbin/atd -f`   
`/usr/bin/lxcfs /var/lib/lxcfs/`   
`/usr/sbin/rsyslogd -n`   
`/usr/bin/python3 /usr/bin/networkd-dispatcher --run-startup-triggers`   
`/usr/bin/dbus-daemon --system --address=systemd: --nofork --nopidfile --systemd-activation --syslog-only`   
`/usr/sbin/cron -f`   
`/usr/lib/accountsservice/accounts-daemon`   
`/usr/sbin/thermald --no-daemon --dbus-enable`   
`/lib/systemd/systemd-logind`   
`/usr/sbin/irqbalance --foreground`   
`/usr/lib/policykit-1/polkitd --no-debug`   
`/usr/bin/python3 /usr/share/unattended-upgrades/unattended-upgrade-shutdown --wait-for-signal`   
`/bin/login -p --`   
`[loop0]`   
`[kworker/0:6]`   
`[kworker/0:7]`   
`/usr/lib/snapd/snapd`   
`/lib/systemd/systemd --user`   
`(sd-pam)`   
`-bash`   
`/usr/sbin/sshd -D`   
`[kworker/1:2]`   
`[kworker/3:2]`   
`[kworker/u32:0]`   
`[kworker/u32:2]`   
`[kworker/u32:1]`   
`[kworker/1:0]`   
`[kworker/3:0]`   
`ps -ef`   
