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
These are the processes running by a default install of Ubuntu Server 18.04.4.
The only non-default I took was to run sshd so I could log in and get this list.
### ps -ef 
`/sbin/init maybe-ubiquity`   
`[kthreadd]`   
`[kworker/0:0H]`   
`[mm_percpu_wq]`   
`[ksoftirqd/0]`   
`[rcu_sched]`   
`[rcu_bh]`   
`[migration/0]`   
`[watchdog/0]`   
`[cpuhp/0]`   
`[cpuhp/1]`   
`[watchdog/1]`   
`[migration/1]`   
`[ksoftirqd/1]`   
`[kworker/1:0H]`   
`[cpuhp/2]`   
`[watchdog/2]`   
`[migration/2]`   
`[ksoftirqd/2]`   
`[kworker/2:0H]`   
`[cpuhp/3]`   
`[watchdog/3]`   
`[migration/3]`   
`[ksoftirqd/3]`   
`[kworker/3:0H]`   
`[kdevtmpfs]`   
`[netns]`   
`[rcu_tasks_kthre]`   
`[kauditd]`   
`[kworker/1:1]`   
`[khungtaskd]`   
`[oom_reaper]`   
`[writeback]`   
`[kcompactd0]`   
`[ksmd]`   
`[khugepaged]`   
`[crypto]`   
`[kintegrityd]`   
`[kblockd]`   
`[kworker/3:1]`   
`[kworker/2:1]`   
`[ata_sff]`   
`[md]`   
`[edac-poller]`   
`[devfreq_wq]`   
`[watchdogd]`   
`[kswapd0]`   
`[kworker/u33:0]`   
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
