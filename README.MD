
# PS4 11.50 - 13.52 WebKit Exploit

### **You can run this project on your PS4 from our website at [zrm.mariope.dev](zrm.mariope.dev)**

> **⚠️ THIS PROJECT WAS MADE BY [RawGame](https://www.facebook.com/RawGameStore/)**

> **⚠️ CAT IMAGES WERE GRABBED FROM [VueAfterFree](https://github.com/Vuemony/vue-after-free) REPO**

> This is a fork that just adds the [VueAfterFree](https://github.com/Vuemony/vue-after-free) Cat Images to the [RawGame web](https://raw-game.com/zrm/) exploit, please, support both proyects along with lapse and poops developers  
>
> I used [aidam19800](https://www.reddit.com/user/aidam19800/)'s extraction of the host source to build this, so special thanks for making the source code available to everyone else

A browser-based PS4 jailbreak project targeting firmware versions in the **11.50–13.52** range made by [RawGame](https://www.facebook.com/RawGameStore/), edited to include the VueAfterFree cat images that some users like me missed

The project combines firmware-specific offsets, JavaScript exploitation chains, memory primitives, and kernel payloads into a self-contained web-based loader. It is designed to run from the PS4 browser and includes offline caching so the required assets can remain available after the initial load even offline.

> **Disclaimer:** This project is intended for research, educational, and legitimate homebrew development purposes. Use it only on hardware and software you own or are authorized to modify. The authors are not responsible for damage, data loss, or other consequences resulting from its use.

## Features

- Automatic PS4 firmware detection.
- Firmware-specific exploit-chain selection.
- Support for the `lapse` and `poops` chains.
- Firmware-specific WebKit/kernel offsets.
- JavaScript memory read/write primitives.
- Worker-based RPC support for memory operations and execution pivots.
- Kernel patch blobs for supported firmware versions.
- Offline browser caching through the Application Cache manifest.
- Automatic retry and safety checks during exploit attempts.
- Configurable runtime parameters through URL query options.
- Lightweight browser UI with status and diagnostic output.

## Usage

The exploit runs on the PS4 Web Browser, you just need to Open the website or self-host on your PS4 Web Browser, wait for it to detect firmware and cache on your console for offline use
There are a few parameters you can use to modify how the webkit will execute

| Parameter | Effect |
| --------- | ------ |
| `?bug=lapse` / `?bug=poops` / '?bug=jbjs' | Force a chain instead of detecting firmware |
| `?verbose=1` | Full log without all details |
| `?slots=N` | Override the carrier array size |
| `?payload=1` | Run the payload even if kernel patching was skipped |

## TODO

 - [x] Cats in Poops chain 
 - [x] Cats in Lapse chain
 - [x] Cats in jb.js chain

## Troubleshooting

Most issues are usually solved by deleting Cookies and Website from your PlayStation, also, cat images will probably require Internet Access since those are not loaded into cache because there are 110 images and I'm not sure how unstable would it make this!

## Supported Firmware

The launcher currently routes firmware versions as follows:

| Firmware | Chain |
| --- | --- |
| 11.50 | `lapse` |
| 11.52 | `lapse` |
| 12.00 | `lapse` |
| 12.02 | `lapse` |
| 12.50 | `poops` |
| 12.52 | `poops` |
| 13.00 | `poops` |
| 13.02 | `jb.js` |
| 13.50 | `jb.js` |
| 13.52 | `jb.js` |

Theorically 11.00 could work since there are offsets for it

## Project Structure

```text
.
├── 13-52/
│   ├── patches/
│   │   ├── 1302.bin
│   │   ├── 1350.bin
│   │   └── 1352.bin
│   ├── cache.appcache
│   ├── core.js
│   ├── goldhen.bin
│   ├── index.html
│   ├── int64.js
│   ├── jb.html
│   ├── jb.js
│   ├── logo_raw.png
│   ├── mem.js
│   ├── payload2.bin
│   ├── ps4_offsets.js
│   └── rpc_worker.js
├── feil/                  # 60 imágenes de gatos
├── susec/                 # 50 imágenes de gatos
├── patches/
│   ├── 1100.bin
│   ├── 1150.bin
│   ├── 1200.bin
│   ├── 1250.bin
│   └── 1300.bin
├── CNAME
├── README.md
├── cache.appcache
├── chain_lapse.js
├── chain_poops.js
├── core.js
├── index.html
├── int64.js
├── logo_raw.png
├── mem.js
├── payload.bin
├── ps4_offsets.js
└── rpc_worker.js
