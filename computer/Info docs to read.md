#ai-written #todo #draft

# Info docs to read

DevOps-focused backlog from the GNU Info index, grouped by the Info manual reference in parentheses, e.g. `(coreutils)`.

The same manual can appear in both `Read` and `Skip` when only some parts are worth studying now.

## Read
### `(bash)`

- [ ] `Bash`: core shell and scripting environment for Linux ops, CI, and automation.

### `(info)`

- [ ] `Info`: learn the browser itself so the rest of the manuals are cheaper to use.

### `(info-stnd)`

- [ ] `info stand-alone`: same reason, but for normal terminal use outside Emacs.

### `(pinfo)`

- [ ] `Pinfo`: worth trying if stock `info` feels awkward.

### `(rluserman)`

- [ ] `RLuserman`: this is the user manual for using readline features in shells; practical editing and history shortcuts pay off every day.

### `(zsh)`

- [ ] `ZSH`: relevant for interactive shell work even if Bash remains the scripting target.

### `(coreutils)`

- [ ] `Common options`: many GNU tools reuse the same option patterns.
- [ ] `Coreutils`: umbrella manual for a huge amount of daily command-line work.
- [ ] `Date input formats`: avoids brittle date math in scripts and ad hoc ops work.
- [ ] `File permissions`: permission mistakes break services, SSH, deploys, and backups.
- [ ] `arch`: quick machine-architecture check when binaries or packages do not match.
- [ ] `b2sum`: modern checksum option worth knowing alongside SHA tools.
- [ ] `base32`: sometimes useful for encoding data into shell-safe text.
- [ ] `base64`: common for secrets, tokens, certificates, and API payloads.
- [ ] `basenc`: broader family of encodings beyond plain base64.
- [ ] `basename`: removes path prefixes cleanly in scripts.
- [ ] `cat`: basic file display and pipeline glue.
- [ ] `chcon`: useful when fixing SELinux file contexts directly.
- [ ] `chgrp`: group ownership matters for shared service files and deploy users.
- [ ] `chmod`: essential for permissions on scripts, keys, sockets, and data.
- [ ] `chown`: ownership is a constant source of Linux breakage.
- [ ] `chroot`: useful in rescue, image-building, and recovery workflows.
- [ ] `cksum`: checksum generation is useful for validation and quick integrity checks.
- [ ] `comm`: useful when comparing sorted lists such as package names or hosts.
- [ ] `cp`: basic file copying never stops mattering.
- [ ] `csplit`: useful when splitting generated output into predictable chunks.
- [ ] `cut`: quick field extraction from delimited text.
- [ ] `date`: used constantly in scripts, logs, and timestamps.
- [ ] `dd`: raw copies and imaging are important, and dangerous enough to learn properly.
- [ ] `df`: first-line disk-space check.
- [ ] `dir`: low-level variant of `ls`; worth recognising when it appears.
- [ ] `dircolors`: worth knowing because it controls `ls` colour behaviour across systems.
- [ ] `dirname`: strips filenames from paths safely in scripts.
- [ ] `du`: second-line disk usage check after `df`.
- [ ] `echo`: simple output in shell, though `printf` is often safer.
- [ ] `env`: inspect or modify environment for one command invocation.
- [ ] `expand`: occasionally needed when tabs break tooling or display.
- [ ] `expr`: old but still appears in portable shell scripts.
- [ ] `factor`: niche, but still part of coreutils and worth recognising rather than skipping.
- [ ] `false`: useful because exit status conventions matter in scripts.
- [ ] `fmt`: useful for quick text reflow in terminals and notes.
- [ ] `fold`: wraps long lines for display or transport.
- [ ] `groups`: quick identity and permission debugging.
- [ ] `head`: fast sampling of files and command output.
- [ ] `hostid`: low-ROI in practice, but still worth recognising because it does show up on Unix systems.
- [ ] `hostname`: always useful for making sure I am on the right box and the right name is configured.
- [ ] `id`: confirms user and group IDs during permission debugging.
- [ ] `install`: better than `cp` when mode, owner, and path creation matter; also worth re-reading from a deployment angle.
- [ ] `join`: useful for combining structured text on shared keys.
- [ ] `kill`: basic process control.
- [ ] `link`: rarely used directly, but worth understanding with hard links.
- [ ] `ln`: symbolic and hard links matter in deployments and system layout.
- [ ] `logname`: worth knowing as the login-name view distinct from effective identity.
- [ ] `ls`: basic filesystem visibility.
- [ ] `md5sum`: still encountered for legacy integrity checks even if not for security.
- [ ] `mkdir`: constant filesystem setup work.
- [ ] `mkfifo`: named pipes do come up in Unix plumbing and debugging.
- [ ] `mknod`: device files matter in containers, initramfs, and low-level admin.
- [ ] `mktemp`: safer temp files and directories in scripts.
- [ ] `mv`: moving and renaming files is constant work.
- [ ] `nice`: process priority matters on busy systems.
- [ ] `nl`: line numbering helps during reviews and debugging.
- [ ] `nohup`: useful when a command must survive disconnects.
- [ ] `nproc`: useful in scripts when sizing parallel work to CPU count.
- [ ] `numfmt`: handy when reformatting bytes and large counts in scripts.
- [ ] `od`: byte-level inspection is useful when files are not plain text.
- [ ] `paste`: useful for merging line-oriented outputs.
- [ ] `pathchk`: useful when checking portability of generated paths.
- [ ] `pinky`: low-ROI, but still worth recognising as a lightweight user-info command.
- [ ] `pr`: low-ROI for most ops work, but still worth recognising as part of the core text toolkit.
- [ ] `printenv`: quick environment inspection without extra shell noise.
- [ ] `printf`: safer and more predictable than `echo` in scripts.
- [ ] `ptx`: niche, but still part of coreutils and worth at least recognising rather than skipping.
- [ ] `pwd`: easy, but critical for avoiding mistakes.
- [ ] `readlink`: symlink debugging comes up constantly.
- [ ] `realpath`: canonical paths reduce ambiguity in scripts and debugging.
- [ ] `rm`: deletion is basic and dangerous enough to deserve care.
- [ ] `rmdir`: occasionally useful for explicit empty-directory cleanup.
- [ ] `runcon`: useful when testing or debugging SELinux contexts for a command.
- [ ] `seq`: good for loops, test data, and quick ranges.
- [ ] `sha1sum`: still appears in older tooling and legacy documentation.
- [ ] `sha2`: modern checksum family for integrity verification.
- [ ] `shred`: relevant when deletion needs to be harder to recover from.
- [ ] `shuf`: useful for sampling, test data, and randomized batch order.
- [ ] `sleep`: essential building block in scripts and retries.
- [ ] `sort`: fundamental text-processing primitive.
- [ ] `split`: useful for chunking large files and log exports.
- [ ] `stat`: often the fastest way to see what the kernel thinks about a file.
- [ ] `stdbuf`: useful when buffering makes pipelines confusing.
- [ ] `stty`: terminal-state debugging matters over SSH and serial consoles.
- [ ] `sum`: older checksum tool worth recognising when it shows up.
- [ ] `sync`: important when writes must hit disk; also worth re-reading from a storage/recovery angle.
- [ ] `tac`: occasionally the easiest way to read output from the end upward.
- [ ] `tail`: central for log work.
- [ ] `tee`: save output while still piping it onward.
- [ ] `test`: core shell conditional primitive.
- [ ] `timeout`: prevents hung commands from blocking automation forever.
- [ ] `touch`: file creation and timestamp nudging are common.
- [ ] `tr`: quick character-level transforms in pipelines.
- [ ] `true`: useful because explicit success is sometimes needed in scripts.
- [ ] `truncate`: useful for sparse files, image prep, and log reset work.
- [ ] `tsort`: occasionally useful when dependency order matters.
- [ ] `tty`: useful for checking whether a script has a terminal.
- [ ] `uname`: machine and kernel identity matter constantly.
- [ ] `unexpand`: sometimes needed when whitespace format matters.
- [ ] `uniq`: very common after `sort`.
- [ ] `unlink`: good to understand because it maps closely to the system call.
- [ ] `uptime`: quick machine health context.
- [ ] `users`: simple way to see logged-in users at a glance.
- [ ] `vdir`: worth recognising as the verbose directory-listing variant from coreutils.
- [ ] `wc`: fast counts for lines, words, and bytes.
- [ ] `who`: useful for multi-user boxes and access debugging.
- [ ] `whoami`: quick identity check.
- [ ] `yes`: useful for feeding repeated input, pressure-testing pipes, and understanding stdin behaviour.

### `(find)`

- [ ] `Finding files`: file selection and bulk operations are constant admin work.
- [ ] `find`: one of the most important admin commands on Unix.
- [ ] `locate`: fast file lookup is useful on large systems when the database is available.
- [ ] `updatedb`: useful if I rely on `locate` on managed systems.
- [ ] `xargs`: one of the most important ways to turn search output into actions.

### `(time)`

- [ ] `Time`: measuring command runtime is basic troubleshooting.

### `(diffutils)`

- [ ] `Diffutils`: comparing configs and patches is routine ops work.
- [ ] `cmp`: fast exact comparison when `diff` is too high-level.
- [ ] `diff`: core config and output comparison tool.
- [ ] `diff3`: useful when reconciling three-way conflicts and merges.
- [ ] `patch`: applying diffs still matters for fixes and vendor patches.
- [ ] `sdiff`: helpful when I want a side-by-side compare in terminal.

### `(gawk)`

- [ ] `awk`: explicit command-level entry because it is one of the main text-processing tools worth actually using.
- [ ] `Gawk`: very high ROI for parsing text output without reaching for Python.

### `(grep)`

- [ ] `grep`: one of the fastest ways to search logs, configs, and code.

### `(sed)`

- [ ] `sed`: good for non-interactive edits and stream transforms.

### `(tar)`

- [ ] `Tar`: standard archive format in Linux packaging, backups, and transfers.

### `(gzip)`

- [ ] `Gzip`: compressed logs and artifacts are everywhere.
- [ ] `gunzip`: decompression is routine.
- [ ] `zcat`: inspect compressed logs without unpacking them first.
- [ ] `zdiff`: compare compressed files directly.
- [ ] `zgrep`: search compressed logs directly.
- [ ] `zmore`: pager for compressed files.

### `(cpio)`

- [ ] `Cpio`: matters for initramfs, recovery, and some packaging internals.

### `(wget)`

- [ ] `Wget`: scriptable downloads fit servers and automation.

### `(nano)`

- [ ] `nano`: useful because it is often present on minimal systems.

### `(ed)`

- [ ] `Ed`: tiny fallback editor worth knowing for stripped-down environments.

### `(gettext)`

- [ ] `envsubst`: very handy for simple config templating in deploy scripts.

### `(accounting)`

- [ ] `acct`: process accounting can help with audit trails and historical activity.

### `(gnupg)`

- [ ] `gpg2`: package trust, signatures, and encrypted file exchange still matter.
- [ ] `gpg-agent`: useful once `gpg` becomes part of normal workflows.
- [ ] `dirmngr`: useful when key retrieval or keyserver access breaks.
- [ ] `dirmngr-client`: lower-level troubleshooting for the same key-distribution path.

### `(pinentry)`

- [ ] `pinentry`: worth understanding because passphrase prompts are a common failure point.

### `(grub2)`

- [ ] `GRUB2`: bootloader basics matter when a box stops booting.
- [ ] `grub2-install`: important in boot recovery and disk replacement situations.
- [ ] `grub2-mkconfig`: common step after kernel or boot config changes.
- [ ] `grub2-mkpasswd-pbkdf2`: useful when protecting bootloader access.
- [ ] `grub2-mkrelpath`: niche, but relevant when diagnosing GRUB path issues.
- [ ] `grub2-mkrescue`: useful when I need recovery media.
- [ ] `grub2-mount`: handy for examining filesystems through GRUB tooling.
- [ ] `grub2-probe`: useful for debugging how GRUB sees disks and filesystems.
- [ ] `grub2-script-check`: sanity-checks GRUB configs before reboot risk.

### `(which)`

- [ ] `Which`: useful for resolving command paths and shadowing problems.

### `(msmtp)`

- [ ] `msmtp`: useful if I ever need scripts or systems to send mail without a full mail stack.

### `(make)`

- [ ] `Make`: still common as a task runner and build entry point even outside pure C/C++ work.

### `(binutils)`

- [ ] `addr2line`: useful when a crash or backtrace gives raw addresses.
- [ ] `readelf`: high-value ELF inspection tool on Linux systems.
- [ ] `strings`: often the fastest way to learn something about an opaque binary.

### `(mtools)`

- [ ] `Mtools`: useful when dealing with FAT media or boot-related images from Unix.

### `(parted)`

- [ ] `parted`: disk layout work is a real DevOps responsibility.

### `(stow)`

- [ ] `Stow`: useful for dotfiles and symlink-managed config trees.

### `(bc)`

- [ ] `bc`: shell-friendly calculator for scripts and quick admin math.

### `(dc)`

- [ ] `dc`: less common than `bc`, but worth recognising because it appears in Unix lore and scripts.

## Skip for now

### `(readline)`

- Skip `Readline`: this is the library/API manual, not the user-facing shell-usage manual; lower value than `RLuserman` right now.

### `(history)`

- Skip `History`: library-level material, not worth active study right now.

### Emacs-related manuals

- Skip the editor ecosystem from this index: `Emacs` `(emacs)`, `Emacs FAQ` `(efaq)`, `IDN Library` in its Emacs-API sense `(libidn)`, `CC Mode` `(ccmode)`, `IDLWAVE` `(idlwave)`, `Octave mode` `(octave-mode)`, `Org Mode` `(org)`, `VHDL Mode` `(vhdl-mode)`, `nXML Mode` `(nxml-mode)`, `Elisp` `(elisp)`, `Emacs Lisp Intro` `(eintr)`, the Emacs library manuals such as `(auth)`, `(cl)`, `(dbus)`, `(emacs-mime)`, `(smtpmail)`, `(url)`, `(widget)`, the Emacs misc manuals such as `(autotype)`, `(bovine)`, `(calc)`, `(dired-x)`, `(ede)`, `(edt)`, `(eieio)`, `(ert)`, `(eww)`, `(epa)`, `(ebrowse)`, `(ediff)`, `(eglot)`, `(eshell)`, `(flymake)`, `(forms)`, `(htmlfontify)`, `(ido)`, `(modus-themes)`, `(pcl-cvs)`, `(reftex)`, `(remember)`, `(ses)`, `(srecode)`, `(semantic)`, `(speedbar)`, `(todo-mode)`, `(transient)`, `(vip)`, `(viper)`, `(wisent)`, `(woman)`, `(use-package)`, `(vtable)`, and the Emacs network manuals such as `(erc)`, `(eudc)`, `(emacs-gnutls)`, `(gnus)`, `(mh-e)`, `(mairix-el)`, `(message)`, `(newsticker)`, `(pgg)`, `(rcirc)`, `(sasl)`, `(sc)`, `(sieve)`, and `(tramp)`.

### `(xorrecord)`, `(xorriso)`, `(xorriso-dd-target)`, `(xorrisofs)`, `(libcdio)`

- Skip `Xorrecord`, `Xorriso`, `Xorriso-dd-target`, `Xorrisofs`, and `libcdio`: optical-media and ISO-burn tooling is too niche for this track.

### `(gettext)`

- Skip the localisation material in this manual except `envsubst`: `gettext`, `gettextize`, `autopoint`, `ISO3166`, `ISO639`, `msgattrib`, `msgcat`, `msgcmp`, `msgcomm`, `msgconv`, `msgen`, `msgexec`, `msgfilter`, `msgfmt`, `msggrep`, `msginit`, `msgmerge`, `msgunfmt`, `msguniq`, `ngettext`, and `xgettext`.

### `(libffi)`

- Skip `libffi`: low payoff unless I start writing against that API.

### `(libunistring)`

- Skip `GNU libunistring`: low payoff unless I start writing against that API.

### `(libidn)`

- Skip `libidn` and `idn` for now: useful only if internationalized domain names become a real problem I hit.

### `(libidn2)`

- Skip `libidn2` and `idn2` for now: useful only if internationalized domain names become a real problem I hit.

### `(nettle)`

- Skip `Nettle`: crypto-library background, not useful enough for current ops study.

### `(gmp)`

- Skip `gmp`: library API, not current ops priority.

### `(libgomp)`

- Skip `libgomp`: library/runtime internals, not current ops priority.

### `(libchewing)`

- Skip `libchewing`: wrong domain for this track.

### `(autoconf)`

- Skip `Autoconf`, `autoconf-invocation`, `autoheader`, `autom4te`, `autoreconf`, `autoscan`, `autoupdate`, `config.status`, `configure`, `ifnames`, and `testsuite` for now; useful mostly when I have to repair older build systems.

### `(automake)`

- Skip `Automake`, `aclocal-invocation`, `automake-invocation`, and `Automake-history` `(automake-history)` for now.

### `(libtool)`

- Skip `Libtool`, `libtool-invocation`, and `libtoolize` for now.

### `(as)`

- Skip `As` and `Gas` for now as part of the C/C++ toolchain.

### `(bfd)`

- Skip `Bfd` for now as part of the C/C++ toolchain.

### `(binutils)`

- Skip `Binutils`, `ar`, `c++filt`, `cxxfilt`, `dlltool`, `elfedit`, `nm`, `objcopy`, `objdump`, `ranlib`, `size`, `strip`, `windmc`, and `windres` for now as C/C++ toolchain material.

### `(cpp)`

- Skip `Cpp` for now as part of the C/C++ toolchain.

### `(cppinternals)`

- Skip `Cpplib` for now as part of the C/C++ toolchain.

### `(ctf-spec)`

- Skip `CTF` for now as part of the C/C++ toolchain.

### `(sframe-spec)`

- Skip `SFrame` for now as part of the C/C++ toolchain.

### `(annobin)`

- Skip `annobin` for now as part of the C/C++ toolchain.

### `(flex)`

- Skip `flex` for now as part of the C/C++ toolchain.

### `(bison)`

- Skip `bison` for now as part of the C/C++ toolchain.

### `(gcc)`

- Skip `gcc`, `g++`, `gcov`, `gcov-dump`, `gcov-tool`, and `lto-dump` for now as C/C++ toolchain material.

### `(gccgo)`

- Skip `Gccgo` for now as part of the C/C++ toolchain.

### `(gccinstall)`

- Skip `gccinstall` for now as part of the C/C++ toolchain.

### `(gccint)`

- Skip `gccint` for now as part of the C/C++ toolchain.

### `(gprof)`

- Skip `gprof` for now as part of the C/C++ toolchain.

### `(ld)`

- Skip `Ld` for now as part of the C/C++ toolchain.

### `(ldint)`

- Skip `Ld-Internals` for now as part of the C/C++ toolchain.

### `(source-highlight)`

- Skip `Source-highlight`: specialised developer tooling, not current ops priority.

### `(source-highlight-lib)`

- Skip `Source-highlight-lib`: specialised developer tooling, not current ops priority.

### `(autosprintf)`

- Skip `autosprintf`: specialised C++ support library, not current ops priority.

### `(pm-gawk)`

- Skip `pm-gawk`: niche variation, not what I need first.

### `(gawkinet)`

- Skip `awkinet`: niche networking add-on around gawk, not what I need first.

### `(m4)`

- Skip `M4`: mostly dragged in by older tooling and not worth active study now.

### `(grub2-dev)`

- Skip `grub2-dev`: GRUB development internals, not current ops priority.

### `(find-maint)`

- Skip `Maintaining Findutils`: contributor/internal material, not normal ops use.

### `(gawkworkflow)`

- Skip `Gawk Work Flow`: contributor/internal material, not normal ops use.

### `(web2c)`, `(dvips)`, `(kpathsea)`, `(tlbuild)`, `(groff)`

- Skip the typesetting stack: `Web2c`, `DVI-to-PostScript`, `Kpathsea`, `TLbuild`, `Groff`, `dvips`, `afm2tfm`, `kpsewhich`, `mktexfmt`, `mktexlsr`, `mktexmf`, `mktexpk`, `mktextex`, `mktextfm`, `install-tl`, `tlmgr`, and the related TeX/Web2c command docs such as `bibtex`, `dvicopy`, `dvitomp`, `dvitype`, `gftodvi`, `gftopk`, `gftype`, `mf`, `mft`, `mltex`, `mpost`, `patgen`, `pktogf`, `pktype`, `pltotf`, `pooltype`, `tangle`, `tex`, `tftopl`, `vftovp`, `vptovf`, and `weave`.

### `(liblouis)`

- Skip `Liblouis`: important in its own domain, but not this learning track.

### `(gzip)`

- Skip `gzexe` and `zforce` for now.

### `(gnupg)`

- Skip `gpgsm` for now; S/MIME matters far less often than plain `gpg2` in Linux ops.
