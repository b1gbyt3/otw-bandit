# OTW bandit 

```ba
ssh <username>@<remote>
```

***-p*** port to connect to on the remote host

---

add this to ~/.zshrc or ~/.bashrc:

```bash
function bandit() {
  ssh bandit$1@bandit.labs.overthewire.org -p 2220
}
```

for fish add this to config.fish:

```bash
function bandit
  ssh bandit$argv[1]@bandit.labs.overthewire.org -p 2220
end
```

---

## Level $0$

```bash
bandit 0
```

> password for bandit$0$: `bandit0`

![SCR-20250202-CinQ9Nnk](/Users/elias/Library/Caches/Clop/images/SCR-20250202-CinQ9Nnk.png)

```bash
ls
cat readme
```

![SCR-20250202-KNlMr3wm](/Users/elias/Library/Caches/Clop/images/SCR-20250202-KNlMr3wm.png)

<details>
  <summary>password for bandit1</summary>
  ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
</details>

---

## Level 1

```bash
ls -lah
cat ./-
```

![SCR-20250202-dUJvM2ej](/Users/elias/Library/Caches/Clop/images/SCR-20250202-dUJvM2ej.png)

<details>
  <summary>password for banditw</summary>
  263JGJPfgU6LtdEvgfWU1XP5yac29mFx
</details>

---

## Level 2

```bash
ls -lah
cat ./"spaces in this filename"
```

![SCR-20250202-MYP3S6oa](/Users/elias/Library/Caches/Clop/images/SCR-20250202-MYP3S6oa.png)

<details>
  <summary>password for bandit3</summary>
  MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
</details>

---

## Level 3

```bash
ls -lah
cd inhere
ls -lah
cat ./...Hiding-From-You
```

![SCR-20250202-fp4aQ6Pm](/Users/elias/Library/Caches/Clop/images/SCR-20250202-fp4aQ6Pm.png)

<details>
  <summary>password for bandit4</summary>
  2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
</details>

---

## Level 4

```bash
file <options> <filepath>
```

```bash
grep <options> <search terms> <filepath>
```

***-i*** ignore case distinctions in patterns and input data

to use the results as input use **xargs** which will pass the file names to **grep**

***-E*** interpret PATTERNS as extended regular expressions

```bash
... | xargs grep -i ...
```

---

```bash
ls -lah
cd inhere
ls -lah
file ./-* | grep text
```

![SCR-20250202-kz48VK7Q](/Users/elias/Library/Caches/Clop/images/SCR-20250202-kz48VK7Q.png)

<details>
  <summary>password for bandit5</summary>
  4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
</details>

---

## Level 5

```bash
find <starting directory> <options> <search terms>
```

***-type*** indicates the type of file or directory you're searching for. 

	- **f:** This means "regular file"
	- **d:** Searches for directories (folders)
	- **l:** Searches for symbolic links to other files

***-iname*** tells *find* to ignore case-sensitivity

***-size*** filter results by size

- ***b***  for 512-byte blocks (this is the default if no suffix is used)

- ***c***  for bytes

- ***w***  for two-byte words

- ***k***  for kibibytes (KiB, units of 1024 bytes)

- ***M***  for mebibytes (MiB, units of 1024 * 1024 = 1048576 bytes)

- ***G***  for gibibytes (GiB, units of 1024 * 1024 * 1024 = 1073741824 bytes)

***-exec*** combine commands to perform actions when files are located

	- without `{}` and `\;`, the command will not work correctly

***-group*** file belongs to group

***-user*** file is owned by user

---

```bash
ls -lah
cd inhere
ls -lah
find . -type f -size 1033c -exec file {} \; | grep text
cat ./maybehere07/.file2
```

![SCR-20250202-hVMeyqYx](/Users/elias/Library/Caches/Clop/images/SCR-20250202-hVMeyqYx.png)

<details>
  <summary>password for bandit6</summary>
  HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
</details>

---

## Level 6

```bash
cd /
find . -type f -size 33c -user bandit7 -group bandit6 2> dev/null
cat ./var/lib/dpkg/info/bandit7.password
```

![SCR-20250202-NjDyOWJD](/Users/elias/Library/Caches/Clop/images/SCR-20250202-NjDyOWJD.png)

<details>
  <summary>password for bandit7</summary>
  morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
</details>

---

## Level 7

```bash
ls -lah
find . -type f -iname "data.txt" | xargs grep -i "millionth"
```

![SCR-20250202-26ITiCQf](/Users/elias/Library/Caches/Clop/images/SCR-20250202-26ITiCQf.png)

<details>
  <summary>password for bandit8</summary>
  dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
</details>

---

## Level 8

```bash
uniq <options> <input> <output>
```

***-u*** only print unique lines

***-d*** only print duplicate lines, one for each group

***-D***   print all duplicate lines

***-c*** prefix lines by the number of occurrences

***-i*** ignore differences in case when comparing

---

```bash
ls -lah
sort data.txt | uniq -iu
```

![SCR-20250202-fJs3FtnF](/Users/elias/Library/Caches/Clop/images/SCR-20250202-fJs3FtnF.png)

<details>
  <summary>password for bandit9</summary>
  4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
</details>

---

## Level 9

```bash
strings <options> <input> //print the sequences of printable characters in files
```

---

```bash
ls -lah
strings data.txt | grep -E "={2,}"
```

![SCR-20250202-9J3GmSC9](/Users/elias/Library/Caches/Clop/images/SCR-20250202-9J3GmSC9.png)

<details>
  <summary>password for bandit10</summary>
  FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
</details>

---

## Level 10

```bash
base64 <options> <filepath>
```

***-d*** decode data

---

```bash
ls -lah
base64 -d data.txt | cat
```



![SCR-20250202-n94BBN2u](/Users/elias/Library/Caches/Clop/images/SCR-20250202-n94BBN2u.png)

<details>
  <summary>password for bandit11</summary>
  dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
</details>

---

## Level 11

```bash
tr <optons> <string1> <string2>
```

![ROT13_table_with_example.svg](/Users/elias/Library/Caches/Clop/images/ROT13_table_with_example.svg.png)

```bash
ls -lah
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

![SCR-20250202-XWbXMeCD](/Users/elias/Library/Caches/Clop/images/SCR-20250202-XWbXMeCD.png)

<details>
  <summary>password for bandit12</summary>
  7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
</details>

---

## Level 12

```bash
xxd <options> <infile>
```

***-r*** convert (or patch) hex dump into binary

---

```bash
gunzip <infile> // decompresses gzip files
```

---

```bash
bunzip2 <infile> // decompresses bzip2 files
```

---

```bash
tar <options> <infile>
```

***-x*** extract files from an archive

***-f*** use archive file or device ARCHIVE

***-z*** filter the archive through **gzip**

---

```bash
ls
mktemp -d
cp data.txt /tmp/tmp.jZKJMBTyU3/dump.txt
cd /tmp/tmp.jZKJMBTyU3
ls
xxd -r dump.txt > data
vim uncompressor.sh
```

uncompressor.sh:

```bash
#!/bin/bash

process_file() {
    local filename="$1"
    local file_type
    file_type=$(file "$filename")

    if echo "$file_type" | grep -q 'ASCII text'; then
        echo "Found ASCII text file: $filename"
        echo
        cat "$filename"
        return
    fi

    case "$file_type" in
        *gzip*)
            echo "Gzipped file detected: $filename"
            mv "$filename" "$filename.gz"
            gunzip "$filename.gz"
            process_file "$filename"
            ;;
        *bzip2*)
            echo "Bzip2 file detected: $filename"
            mv "$filename" "$filename.bz2"
            bunzip2 "$filename.bz2"
            process_file "$filename"
            ;;
        *tar*)
            echo "Tar archive detected: $filename"
            tar -xf "$filename"
            for extracted_file in $(tar -tf "$filename"); do
                process_file "$extracted_file"
            done
            ;;
        *)
            echo "Unknown filetype: $filename"
            ;;
    esac
}

process_file "$1"
```

```bash
chmod +x uncompressor.sh
./uncompressor.sh data
```

![SCR-20250202-BBsqCkxn](/Users/elias/Library/Caches/Clop/images/SCR-20250202-BBsqCkxn.png)

<details>
  <summary>password for bandit13</summary>
  FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
</details>

## 

