Make a script file secure that only user can execute it, Not even root

- Add condition at the top in script file that if userID is 0 then
  script file will not execute → if \[ \"\$EUID\" -eq 0 \]

- Change permissions of the file → chmod 700 filename.sh

- Then encrypt the file → gpg -c list_all_repos.sh

- decrypt and run it using command (Only user with permission can
  decrypt it) → gpg -d list_all_repos.sh.gpg \| bash

  **Note:**

- *gpg -d \...* decrypts the file and turns it into a stream of
  plain-text code inside the computer\'s RAM.

- **The Pipe (*****\|*****)** acts like a temporary tunnel in memory. It
  immediately squirts that text straight into the mouth of the
  ***bash*** program.

- ***bash*** reads the lines of code directly from RAM, executes them
  one by one, and then finishes.
