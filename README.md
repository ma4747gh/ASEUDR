# ASEUDR - Active Subdomains Enumeration Using DNS Resolvers

ASEUDR is a Python script designed for active enumeration of subdomains using DNS resolvers. It verifies DNS resolver validity, checks for geolocation of a baseline root domain, and performs NXDOMAIN validation.

## Requirements

- Python 3.6 or higher
- Required Python packages listed in `requirements.txt`

## Installation

1. Clone the repository:

   ```bash
   git clone <repository_url>
   cd <repository_name>
   ```

## Usage

### Basic Usage

Run ASEUDR with the following command:

```bash
python aseudr.py <dns_resolvers_file_path> -dfp <domains_file_path> -brd <baseline_root_domain> -nxd <nxdomain> [-dnv] [-t <threads>] [-or <output_dns_resolvers>] [-od <output_domains>] [-edv] [-m <mode>] [-w <wordlist_file_path>] [-d <domain>]
```

### Arguments

- `dns_resolvers_file_path`: Path to the file containing DNS resolvers.
- `-dfp, --domains_file_path`: Path to the file containing domains.
- `-brd, --baseline_root_domain`: Baseline root domain to validate DNS resolvers (default: bbc.com).
- `-nxd, --nxdomain`: Root domain to validate DNS resolvers using NXDOMAIN validation (default: google.com).
- `-dnv, --disable_nxdomain_validation`: Disable NXDOMAIN validation.
- `-t, --threads`: Number of threads to use (default: 1).
- `-or, --output_dns_resolvers`: File path to save valid DNS resolvers (default: dns_resolvers.txt).
- `-od, --output_domains`: File path to save valid domains (default: valid_domains.txt).
- `-edv, --enable_dns_validator`: Enable DNS validator.
- `-m, --mode`: Desired mode (`resolver` or `brute-force`, default: resolver).
- `-w, --wordlist_file_path`: Path to file containing subdomains (required for brute-force mode).
- `-d, --domain`: Domain to process (required for brute-force mode).

## Examples

### Example 1: Using DNS resolvers file and domains file

```bash
python aseudr.py resolvers.txt -dfp domains.txt
```

### Example 2: Using brute-force mode with a wordlist

```bash
python aseudr.py resolvers.txt -m brute-force -w subdomains.txt -d example.com
```

## Acknowledgments

- Coded by Mohamed Ahmed (ma4747gh)
