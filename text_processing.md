
---

## 🔵 **3️⃣ 3_text_processing.md**
```markdown
# ✂️ Text Processing in Linux

---

## 🧩 The `cut` Command

Extracts specific parts of text from a file.

### Cut by character:
```bash
cut -c 5 sample.txt
Cut by field:
cut -f 2 sample.txt

Using a custom delimiter:
cut -f 1 -d ";" sample.txt
---
The paste Command

Merges lines from multiple files into one.

Example:
paste -s sample2.txt
paste -d ' ' -s sample2.txt

The -s flag joins lines sequentially, and -d changes the delimiter.
---
The head Command

Displays the first 10 lines of a file by default.
head /var/log/syslog
head -n 15 /var/log/syslog
---
The tail Command

Displays the last 10 lines of a file.
tail /var/log/syslog
tail -n 20 /var/log/syslog
tail -f /var/log/syslog  # Monitor file live
---
expand and unexpand
Convert tabs to spaces:
expand sample.txt
expand sample.txt > result.txt

Convert spaces to tabs:
unexpand -a result.txt
---
oin and split
Join two files by common field:
join file1.txt file2.txt

Join by different fields:
join -1 2 -2 1 file1.txt file2.txt


Split large files:
split -l 1000 somefile

sort

Sorts lines alphabetically:
sort file.txt

Reverse order:
sort -r file.txt

Numeric sort:
sort -n file.txt
---
tr (Translate)

Used to replace or delete characters.

Convert lowercase → uppercase:
echo "hello" | tr a-z A-Z

Delete digits:
echo "My age is 22" | tr -d '0-9'

Remove extra spaces:
echo "Hello     world" | tr -s ' '
---
uniq (Unique)

Removes duplicate adjacent lines from text.
uniq reading.txt
uniq -c reading.txt   # Count duplicates
uniq -u reading.txt   # Show unique lines only
uniq -d reading.txt   # Show only duplicates

Tip: uniq only removes adjacent duplicates — sort the file first.
sort reading.txt | uniq
---
wc and nl
Word count:
wc file.txt      # lines, words, bytes
wc -l file.txt   # line count only

Number lines:
nl file.txt
---
grep

Search text for a pattern.

Basic search:
grep fox sample.txt

Flags:

-i → ignore case

-c → count matches

-o → show only matches

-v → invert match

Advanced:
grep -e "-v" file.txt
grep -f patterns.txt file.txt

Combine with other commands:
env | grep -i USER
ls /dir | grep '.txt$'
