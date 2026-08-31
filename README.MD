
# PS4 11.50 - 13.00 WebKit Exploit

### **You can run this project on your PS4 from our website at [zrm.mariope.dev](zrm.mariope.dev)**

> **⚠️ THIS PROJECT WAS MADE BY [RawGame](https://www.facebook.com/RawGameStore/)**

> **⚠️ CAT IMAGES WERE GRABBED FROM [VueAfterFree](https://github.com/Vuemony/vue-after-free) REPO**

> This is a fork that just adds the [VueAfterFree](https://github.com/Vuemony/vue-after-free) Cat Images to the [RawGame web](https://raw-game.com/zrm/) exploit, please, support both proyects along with lapse and poops developers  
>
> I used [aidam19800](https://www.reddit.com/user/aidam19800/)'s extraction of the host source to build this, so special thanks for making the source code available to everyone else

A browser-based PS4 jailbreak project targeting firmware versions in the **11.50–13.00** range made by [RawGame](https://www.facebook.com/RawGameStore/), edited to include the VueAfterFree cat images that some users like me missed

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

## TODO

 - [x] Cats in Poops chain 
 - [ ] Cats in Lapse chain (disabled due to a bug temporarilly)

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

Theorically 11.00 could work since there are offsets for it

## Project Structure

```text
.
├── index.html
├── run_lapse.html
├── run_poops.html
├── chain_lapse.js
├── chain_poops.js
├── core.js
├── mem.js
├── int64.js
├── rpc_worker.js
├── ps4_offsets.js
├── payload.bin
├── patches/
│   ├── 1100.bin
│   ├── 1150.bin
│   ├── 1200.bin
│   ├── 1250.bin
│   └── 1300.bin
├── cache.appcache
├── logo_raw.png
└── EXTRACTION_MANIFEST.json
