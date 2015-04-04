A suid helper to let a process willingly drop privileges on Linux.

The <a href='http://code.google.com/p/chromium/wiki/LinuxSUIDSandbox'>Chrome/Chromium Linux sandbox</a> is based on this code and design.

It will allow a process to execute a target executable that
will be able to drop privileges:

<ul>
<li>the suid sandbox will create a new PID namespace or will switch uid/gid to isolate the process</li>
<li>a helper process, sharing the filesystem view of the existing process, will be created. It will accept a request to chroot() the process to an empty directory</li>
</ul>

This is convenient because an executable can be launched, load libraries and open files and get chroot()-ed to an empty directory when it wants to drop filesystem access.

<a href='http://www.cr0.org/paper/jt-ce-sid_linux.pdf'>This presentation</a> has more information.

Be sure to check the limitations in the <a href='https://code.google.com/p/setuid-sandbox/source/browse/README'>README</a> file as this can be dangerous.

You can contact us at [this address](mailto:setuidsbx-dev@googlegroups.com).