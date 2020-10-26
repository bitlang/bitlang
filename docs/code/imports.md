# Imports
Bit can import any other Bit file, as well as some other languages, such as JSON and YAML, directly.

```bit
import /* relative filename */ as /* identifier */
import /* filename */ from /* some sources: see below */ as /* identifier */
import from /* source: see below */ as /* identifier*/

# For example
import centidays.bit as cd
import settings.bit from config as settings
import from github:bitlang/time as time
```

## Sources
Valid sources that don't require filenames include:
* https urls (usually to a Git repository), such as "https://github.com/bitlang/udp.git"
* ssh/sftp urls (to a Git repository or public file/folder), such as "ssh://bit@mirror.some.edu/module/"
* FTP is insecure so it is not defined here
* GitHub projects, such as "github:bitlang/tcp" (versions supported)
* Dependencies: "package:uuid"
* Core modules: "core:time"

When using these sources, [`project.bit`][projectbit] is read to determine the executable. 

Valid sources which require filenames include:
* "config", for the app configuration data folder (read-write)
* "userdata", for user-accessible data (read-write). Falls back on "config" if the platform doesn't support it
* "system", for read-only system data. These "files" are virtual and have no extension
* "temp", for temporary data (read-write). On Linux these are stored in /tmp and have a hyphen and the process ID appended

[projectbit]: ../projectbit.md