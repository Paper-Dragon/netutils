````yaml
╭ [0] ╭ Target: nmaguiar/netutils:build (alpine 3.20.3) 
│     ├ Class : os-pkgs 
│     ╰ Type  : alpine 
├ [1] ╭ Target: Java 
│     ├ Class : lang-pkgs 
│     ╰ Type  : jar 
╰ [2] ╭ Target         : Python 
      ├ Class          : lang-pkgs 
      ├ Type           : python-pkg 
      ╰ Vulnerabilities ─ [0] ╭ VulnerabilityID : CVE-2024-52804 
                              ├ PkgName         : tornado 
                              ├ PkgPath         : opt/mitmproxy/lib/python3.12/site-packages/tornado-6.4.1.dist
                              │                   -info/METADATA 
                              ├ PkgIdentifier    ╭ PURL: pkg:pypi/tornado@6.4.1 
                              │                  ╰ UID : c01a8ef5d574c81 
                              ├ InstalledVersion: 6.4.1 
                              ├ FixedVersion    : 6.4.2 
                              ├ Status          : fixed 
                              ├ Layer            ╭ Digest: sha256:886b4765147d7f2858934c8c07c689625799c2f4a12ef
                              │                  │         5fb468e1db10eee08c6 
                              │                  ╰ DiffID: sha256:e47b55d49d4b7f43cdea24cf5c5b48dc45bc0d1876e4f
                              │                            31f081d27cb46047306 
                              ├ SeveritySource  : ghsa 
                              ├ PrimaryURL      : https://avd.aquasec.com/nvd/cve-2024-52804 
                              ├ DataSource       ╭ ID  : ghsa 
                              │                  ├ Name: GitHub Security Advisory pip 
                              │                  ╰ URL : https://github.com/advisories?query=type%3Areviewed+ec
                              │                          osystem%3Apip 
                              ├ Title           : Tornado is a Python web framework and asynchronous networking
                              │                    library. ... 
                              ├ Description     : Tornado is a Python web framework and asynchronous networking
                              │                    library. The algorithm used for parsing HTTP cookies in
                              │                   Tornado versions prior to 6.4.2 sometimes has quadratic
                              │                   complexity, leading to excessive CPU consumption when parsing
                              │                    maliciously-crafted cookie headers. This parsing occurs in
                              │                   the event loop thread and may block the processing of other
                              │                   requests. Version 6.4.2 fixes the issue. 
                              ├ Severity        : HIGH 
                              ├ CweIDs           ╭ [0]: CWE-400 
                              │                  ╰ [1]: CWE-770 
                              ├ VendorSeverity   ─ ghsa: 3 
                              ├ CVSS             ─ ghsa ╭ V3Vector: CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:N/I:N/A:H 
                              │                         ╰ V3Score : 7.5 
                              ├ References       ╭ [0]: https://github.com/advisories/GHSA-7pwv-g7hj-39pr 
                              │                  ├ [1]: https://github.com/tornadoweb/tornado 
                              │                  ├ [2]: https://github.com/tornadoweb/tornado/commit/d5ba4a1695
                              │                  │      fbf7c6a3e54313262639b198291533 
                              │                  ├ [3]: https://github.com/tornadoweb/tornado/security/advisori
                              │                  │      es/GHSA-8w49-h785-mj3c 
                              │                  ╰ [4]: https://nvd.nist.gov/vuln/detail/CVE-2024-52804 
                              ├ PublishedDate   : 2024-11-22T16:15:34.417Z 
                              ╰ LastModifiedDate: 2024-11-22T16:15:34.417Z 
````
