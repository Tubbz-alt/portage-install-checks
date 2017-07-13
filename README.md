# Portage Install Checks
Extra post-install QA checks for Portage, with output in both human and machine-readable formats.

## For humans
1. Install these checks to ``/usr/local/lib/install-qa-check.d`` or ``/usr/lib/install-qa-check.d``
2. Enable QA logging in ``/etc/portage/make.conf``: ``PORTAGE_ELOG_CLASSES="log warn error qa"``
3. emerge your package
4. Check the build log and hope there's no new QA violations

## For machines
QA violations are logged to ``"${T}"/qa.log`` in [YAML](http://yaml.org/):
```
- tag: share-elf
  files:
    - "/usr/share/bin/foo"
    - "/usr/share/bin/bar"
```
