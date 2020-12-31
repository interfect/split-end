# `split-end`: Split a file from the end

Do you have a large file and a small disk? Do you want your large file to be in smaller pieces? Then `split-end` is the tool for you!

This tool allows you to split an extremely large file into smaller parts, even when you don't have the free disk space to store a copy of the file. You only need the extra space to store the one part file that is in progress at any given time.

## Disclaimer

This tool may not actually work for you, or for anyone. It may eat your data. If you're in a situation where you have data worth more than $0 and you don't have space for 2 copies, and you intend to trust it to random code you found On Line, this tool will actually detect your unforgivable offense against the Backup Gods and secretly corrupt your data out of spite. No warranties. You're somehow not allowed to sue me because I said so.

## Installation and Usage

Simply:

1. `git clone https://github.com/interfect/split-end.git`

2. `cd split-end`

3. `./split-end ~/source-file.dat ~/dest-name.dat`

This will create files `~/dest-name.dat.part00000`, `~/dest-name.dat.part00001`, ... to contain the chunks of your file. Each file will be 4 GiB (unless you edit the script). Files will be created from the *end* of the source file first, counting down to part 0, and after each part is created the data will be trimmed from the end of the source file. At the end of the process, the source file will have size 0, and can be safely deleted.

