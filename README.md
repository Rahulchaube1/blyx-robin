<img src="assets/logo.png" width="112" height="112" alt="Robin logo">

# Robin

Convert a validated civil date into an ordinal, weekday and comparable day number. This Blyx workflow framework is part of the calendar, scheduling and local time collection.

Month lengths and century leap rules affect both date validation and weekday calculations. Resolve both from the same Gregorian day number. [Python, proleptic Gregorian calendar](https://docs.python.org/3/library/calendar.html)

## Install and run

Install [Blyx 0.2.1](https://www.blyx-lang.space/download) with a Rust toolchain and host linker for native builds.

```sh
git clone --depth 1 --branch v0.1.0 https://github.com/Rahulchaube1/blyx-robin.git
cd blyx-robin
blyxc native-run example.blyx
blyxc native-run tests.blyx
```

[Run the editable browser example](https://www.blyx-lang.space/play?example=package-robin) · [Package page](https://www.blyx-lang.space/packages/robin) · [Handbook](https://doc.blyx-lang.space/guide/robin)

## Import the module

Run this in the directory containing your application's entry file.

```sh
git clone --depth 1 --branch v0.1.0 https://github.com/Rahulchaube1/blyx-robin.git vendor/robin
```

```blyx
use vendor::robin::robin;

fn main() {
    let year = 1970.0;
    let month = 1.0;
    let day = 1.0;
    let result = robin_date(year, month, day);
    if len(result) == 0 { println!("invalid"); return; }
    let mut i = 0;
    while i < len(result) {
        println!(at(result, i));
        i += 1;
    }
}
```

Expected output

```text
719163
3
1
31
```

## API

`robin_date(year, month, day)`

Returns [day number with 0001-01-01 = 1, Monday-zero weekday, day-of-year, days in month]. This is a calendar computation independent of machine locale. Invalid arguments and nonfinite results return an empty vector. Integers carried in numeric vectors use the exact range from −(2^53−1) to 2^53−1.

| Argument | Domain |
| --- | --- |
| year | A positive exact integer |
| month | A positive exact integer |
| day | A positive exact integer |

## Run the command-line project

Run the example with your own numbers. Vector arguments accept up to 16 comma-separated entries; use `[]` for an empty vector. The imported API accepts longer vectors. Invalid arguments return a nonzero exit status.

```sh
blyxc native-run project.blyx -- 1970 1 1
```

## Libraries

- [GregorianDay](https://github.com/Rahulchaube1/blyx-gregorianday/tree/v0.1.0) — Validate a proleptic Gregorian date and calculate its day-of-year.
- [YearOrigin](https://github.com/Rahulchaube1/blyx-yearorigin/tree/v0.1.0) — Count Gregorian days before January 1 of a year.

This release includes identical copies of both library modules so a tagged clone can build offline.

## Verification and contributions

The regression suite in [tests.blyx](tests.blyx) checks the example, boundary cases and invalid inputs. Include a short reproducer and your compiler version in [an issue](https://github.com/Rahulchaube1/blyx-robin/issues). The source is dual-licensed under [MIT](LICENSE-MIT) or [Apache-2.0](LICENSE-APACHE). The package artwork uses [Lucide icons](https://lucide.dev/license); see [artwork notices](assets/NOTICE.txt).

## Connect with Rahul Chaube

[Portfolio](https://www.rahulchaube1.com/) · [GitHub](https://github.com/Rahulchaube1) · [LinkedIn](https://www.linkedin.com/in/rahulchaube1) · [Hugging Face](https://huggingface.co/oncody) · [X](https://x.com/RahulChaube_) · [EverestQ](https://www.everestqai.com/) · [Contact](https://www.rahulchaube1.com/contact)

[Blyx website](https://www.blyx-lang.space/) · [BlyxTorch](https://www.blyx-lang.space/packages/blyxtorch) · [Handbook](https://doc.blyx-lang.space/) · [Community](https://www.blyx-lang.space/community)

Support Rahul’s open-source work through [GitHub Sponsors](https://github.com/sponsors/Rahulchaube1) or [Buy Me a Coffee](https://buymeacoffee.com/rahulchaube).
