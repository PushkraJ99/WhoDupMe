# WhoDupMe <a href="https://twitter.com/intent/follow?screen_name=PushkraJ99"><img src="https://img.shields.io/twitter/follow/DreyAnd.svg?style=social&label=Follow"></a>

## Contents:

- [Installation](#Installation)
- [Usage](#Usage)

## About the tool:

* This tool serves as a little utility which allows a bug bounty hunter to **discover who gave him a duplicate** on his HackerOne report.
* As a result he *may* get in contact with the hunter or eventually hire a hitman on him! (for legal reasons this is a joke)


Note: For this tool to work the report you got a duplicate on has to be in *resolved* state.
## Installation:

#### From source:

```bash
go install github.com/DreyAnd/WhoDupMe/cmd/WhoDupMe@latest
```

#### From GitHub:

You can follow these steps:

```bash
git clone https://github.com/DreyAnd/WhoDupMe
cd WhoDupMe/cmd/WhoDupMe; go build
sudo mv WhoDupMe /usr/local/bin 
WhoDupMe -h

WhoDupMe --program_name=" " --report_id=" " --h1_session=" "
```

## Usage:

To display the help menu use the `-h` argument:
```
Usage:
  main [OPTIONS]

Application Options:
      --help          Show Usage Information
      --program_name= Name of the program where you got a duplicate on
      --h1_session=   HackerOne Account Session Cookie
      --report_id=    HackerOne Report ID

Help Options:
  -h, --help          Show this help message
```
### Example usage:

![Image](https://i.imgur.com/IENFeQj.png)

### How to get the needed parameters:

* `--program_name` - You can get this simply by looking at the URL of the targeted BBP:

![Image](https://i.imgur.com/Rv3MwLj.png)

* `--h1_session` - The purpose of this one is for private programs, which is a bit annoying sadly, but you can follow these steps to get it:

1. Open https://hackerone.com while logged-in.
2. Open Chrome DevTools -> `Application`
3. Inside the `Cookies` section find the `__Host-session` cookie and copy it:

![Image](https://i.imgur.com/BkUMfRd.png) 

* `--report-id` - This is just the report you got duped to, which is the reason why you're looking at this tool in the first place. Anyways you can find it in your report like this:

![Image](https://i.imgur.com/ER4eZRC.png)

## Special Thanks:

* [Dexter0us](https://twitter.com/0xDexter0us) for letting me know about this trick in the HackerOne GraphQL API.


## TODO:

* ~~Add concurrency for more speed.~~
* Add the possibility to automatically get all duplicated report IDs for a program and dump info for all.
* Add a debug `-v` mode
