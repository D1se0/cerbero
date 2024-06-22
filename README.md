# Cerbero

Cerbero is a command line tool designed to perform brute force attacks against SSH and FTP services. This tool can be useful for security audits or penetration tests where the resistance of access credentials needs to be tested.

<p align="center">
  <img src="https://github.com/D1se0/cerbero/assets/164921056/064b49a7-e7f8-4548-9017-1a68390a032e" alt="Directorybrute" width="400">
</p>

---

## Main Features

- Support for brute force attacks on SSH and FTP services.
- Ability to manage multiple users and passwords through files or direct entries.
- Option to list users across known vulnerabilities in SSH versions.
- Thread management to improve performance during attacks.
- Intuitive and easy-to-use command line interface.

## Requirements

To run Cerbero, the following dependencies are required:

- `Python 3.x`
- Libraries Python:
  - `paramiko`
  - `ftplib`
  - `colorama`

## You can install the dependencies by running:

### To install only the tool `cerbero.py`

```bash
./requeriments.sh
```

### To install only the tool `cerbero_only_ssh.py`

```bash
./requeriments_only_ssh.sh
```

## Use

### Basic Usage Examples

**SSH attack with a specific username and password:**

```bash
 python3 cerbero.py -H <target_ip> -u <username> -p <password> -s ssh
```

**SSH attack with a user and password dictionary:**

```bash
 python3 cerbero.py -H <target_ip> -u <username> -P <file_passwords> -s ssh
```

**SSH attack with a user dictionary and specific password:**

```bash
 python3 cerbero.py -H <target_ip> -U <file_usernames> -p <password> -s ssh
```

**SSH attack with a user dictionary and password dictionary:**

```bash
 python3 cerbero.py -H <target_ip> -U <file_usernames> -P <file_passwords> -s ssh
```

**FTP attack with a user and password dictionary:**

```bash
 python3 cerbero.py -H <target_ip> -u <username> -P <file_passwords> -s ftp
```

**FTP attack with a user dictionary and specific password:**

```bash
 python3 cerbero.py -H <target_ip> -U <file_usernames> -p <password> -s ftp
```

**FTP attack with username and password files:**

```bash
python cerbero.py -H <target_ip> -U <FILE_USERS> -P <FILE_PASSWORDS> -s ftp
```

**SSH or FTP attack with username and passwords using various combinations on the user:**

```bash
 python3 cerbero.py -H <target_ip> -u <username> -P <file_passwords> -s ssh -e n s r
```

### Explanation

`n`: Deals with a null password attempt.

`s`: Use the username as a password.

`r`: Reverses the username and uses it as a password.

### Available options

`-H`, `--host`: Specifies the IP address of the destination host.

`-s`, `--service`: Defines the service to attack (ssh or ftp).

`-u`, `--user`: Provides a single user for authentication.

`-p`, `--passwd`: Provides a one-time password for authentication.

`-U`, `--user-file`: Specifies a file with a list of users.

`-P`, `--passwd-file`: Specifies a file with a list of passwords.

`-t`, `--threads`: Number of threads to use to increase the speed of the attack (default: 5).

`-o`, `--output-file`: Saves the results to a specified file.

`-c`, `--success-continue`: It continues with the next valid username/password combination after finding one.

`-e`, `--extra-params`: Additional parameters to customize user/password combinations.

`-en`, `--enumerate-users`: Attempts to enumerate users by exploiting known vulnerabilities in SSH versions.

### Running as Root

To run Cerbero with all necessary permissions, it is recommended to run it as root or with equivalent privileges, especially if low ports are required or multiple simultaneous connections are made.

### Contributions

If you would like to contribute to Cerbero, we are open to suggestions, problem reports, and improvement requests! Please create an issue in this repository or submit a pull request with your changes.

## Thanks

Cerbero was created by Diseo (@d1se0) as a personal project. We thank all contributors and users for their support and feedback.
