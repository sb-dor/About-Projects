# Cafe POS

#### Own project · in development · source code is private

Flutter (Windows, macOS, Android, iOS) · Dart server · Drift (SQLite) · WebSocket · control + freezed

**Cafe POS** is a local system for cafés and quick-service restaurants that works without the
internet. The venue's PC runs the database and a Dart server; tablets connect to it over the local
Wi-Fi. Guests order on a self-service kiosk and pay at the cashier, the kitchen sees the order on its
screen, an order board shows when it is ready, and the owner runs the menu, stock, money and reports
from the staff app.

## What it includes

- **Staff app (Windows, macOS)**: sales and payments, stop-list, receipts and returns, cash accounts.
- **Kiosk, kitchen display and order board** on Android and iOS tablets.
- **Stock**: recipes, receipts, transfers, production, write-offs, stocktakes, shelf life and labels,
  food cost, minimum stock and a "need to buy" list.
- **Suppliers**: payments, advances, returns and supplier orders.
- **Promotions and loyalty**: promo codes, discount reasons, customers, bonuses and levels.
- **Staff**: clock in and out by PIN, timesheets, payroll, bonuses and penalties, tips.
- **Reports**: profit, discounts, customers, stock reports and an "anomalies" report (cancellations,
  refunds, large discounts).
- **Operations**: HTTPS with certificate pinning between tablets and the server, licenses, backups,
  updates, a Windows service and installer, error reports to Sentry.

**How it is built:** a Dart pub workspace with 4 apps and 6 shared packages (core rules, API contract,
API client, design system, licensing, telemetry); money is stored as integers; about 600 test files.
I write the specs, plans and architecture rules, AI agents (Claude Code) write code against them, and I
review every change.

## Screenshots

### Staff app (desktop)

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/cafe_pos/desktop_home.webp" width="420" alt="Cafe POS staff app home screen" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/cafe_pos/desktop_profit.webp" width="420" alt="Cafe POS profit report" />
</p>

### Self-service kiosk (tablet)

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/cafe_pos/tablet_kiosk_start.webp" width="280" alt="Cafe POS kiosk start screen" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/cafe_pos/tablet_kiosk_where.webp" width="280" alt="Cafe POS kiosk dine in or take away" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/cafe_pos/kiosk_menu.webp" width="280" alt="Cafe POS kiosk menu" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/cafe_pos/tablet_kiosk_dish.webp" width="280" alt="Cafe POS kiosk dish with options" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/cafe_pos/tablet_kiosk_cart.webp" width="280" alt="Cafe POS kiosk cart with a promotion" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/cafe_pos/tablet_kiosk_loyalty.webp" width="280" alt="Cafe POS kiosk phone number for bonuses" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/cafe_pos/tablet_kiosk_done.webp" width="280" alt="Cafe POS kiosk order number and payment" />
</p>

### Kitchen display and order board (tablet)

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/cafe_pos/kitchen_display.webp" width="280" alt="Cafe POS kitchen display" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/cafe_pos/tablet_kitchen_history.webp" width="280" alt="Cafe POS kitchen display history" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/cafe_pos/order_board.webp" width="280" alt="Cafe POS order board" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/cafe_pos/tablet_board_qr.webp" width="280" alt="Cafe POS order board with payment QR codes" />
</p>

### Connecting a tablet to the venue server

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/cafe_pos/tablet_pairing.webp" width="280" alt="Cafe POS tablet pairing" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/cafe_pos/tablet_pairing_fingerprint.webp" width="280" alt="Cafe POS tablet pairing certificate fingerprint check" />
</p>

### Phone

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/cafe_pos/phone_kiosk_start.webp" width="150" alt="Cafe POS phone kiosk start screen" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/cafe_pos/phone_kiosk_menu.webp" width="150" alt="Cafe POS phone kiosk menu" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/cafe_pos/phone_kiosk_dish.webp" width="150" alt="Cafe POS phone kiosk dish" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/cafe_pos/phone_kiosk_cart.webp" width="150" alt="Cafe POS phone kiosk cart" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/cafe_pos/phone_kiosk_done.webp" width="150" alt="Cafe POS phone kiosk order number" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/cafe_pos/phone_pairing_code.webp" width="150" alt="Cafe POS phone pairing code" />
</p>

-----

# Extracter: Audio to Text

#### Own project · open source

Flutter · whisper.cpp · FFmpeg · Drift

**Extracter** turns audio and video recordings into text right on the device. Lectures, meetings,
interviews, podcasts and voice notes are transcribed offline with OpenAI Whisper models
(whisper.cpp), and FFmpeg takes the audio track from video files. Nothing is uploaded, there is no
account, and the app keeps working in airplane mode once a speech model is downloaded.

## Features

- **Any format**: MP3, M4A, WAV, OGG, OPUS, FLAC, AAC, MP4, MOV, MKV, WEBM, AVI and more.
- **100% offline and private**: speech recognition runs on the device.
- **About 100 languages** with automatic language detection, plus translation into English.
- **Live results** with progress for every file, and a **batch queue** for several files.
- **Timestamps** for every sentence; copy as clean paragraphs or with timestamps.
- **Export** to TXT, SRT or VTT subtitles.
- **Full-text search** across all transcripts.
- **Models from Tiny to Large v3 Turbo**: download once, switch any time, delete the ones you don't need.
- Runs on **Android, iOS and macOS**.

_Take a look at the app
on [Google Play Store](https://play.google.com/store/apps/details?id=com.bdaynabday.extracter)_
and the source code on [GitHub](https://github.com/sb-dor/Extracter)

## Screenshots

### Android — Portrait

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/extracter/screenshot_01.webp" width="150" alt="Extracter transcribing an audio file" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/extracter/screenshot_02.webp" width="150" alt="Extracter speech models" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/extracter/screenshot_03.webp" width="150" alt="Extracter transcript history and search" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/extracter/screenshot_04.webp" width="150" alt="Extracter transcript with timestamps" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/extracter/screenshot_05.webp" width="150" alt="Extracter copy with or without timestamps" />
</p>

### Android — Tablet

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/extracter/tablet_01.webp" width="300" alt="Extracter tablet transcription queue" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/extracter/tablet_02.webp" width="300" alt="Extracter tablet history" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/extracter/tablet_03.webp" width="300" alt="Extracter tablet transcript view" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/extracter/tablet_04.webp" width="300" alt="Extracter tablet copy options" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/extracter/tablet_05.webp" width="300" alt="Extracter tablet speech models" />
</p>

-----

# FAgent — Flutter Code Agent

#### Own project · open source

Flutter (macOS desktop) · Agent Client Protocol · MCP · Drift

**FAgent** is an open-source desktop workspace for Flutter development with AI coding agents. It
does not ship its own AI: it drives Claude Code, Codex or Gemini CLI over the Agent Client Protocol
(ACP) and gives them what a Flutter project needs: the running app, the Dart tooling and built-in
Flutter rules. Chat with the agent, run the app with hot reload, point at a widget and read or edit
the code, all in one window.

## Features

- **Chat with your agent**: text, thinking, tool calls, the plan and changed files arrive live; a
  Changes pane shows every change as a diff; permission requests in a dialog.
- **Run the app**: devices, build modes, hot reload and hot restart, logs; send a build or runtime
  error to the agent in one click.
- **Widget picker**: click a widget in the running app and the chat gets its name, file and line,
  ancestors and a screenshot.
- **Code view**: explorer and editor with a Dart language server (completion, diagnostics, go to
  definition, find references, format on save).
- **17 built-in Flutter rules** (architecture, controllers, repositories, widgets, navigation,
  security, testing and more), collected from the Flutter community and from leading Flutter
  engineers, written into each project so agents build features the same way every time.
- **New project wizard** that lays out a project following those rules.
- The app's own MCP server and the Dart MCP server are connected to every session.
- 160+ automated tests.

_Take a look at the source code
on [GitHub](https://github.com/sb-dor/FAgent)_

## Screenshots

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/FAgent/main/docs/images/chat.png" width="300" alt="FAgent chat with the agent, plan and Changes pane" />
  <img src="https://raw.githubusercontent.com/sb-dor/FAgent/main/docs/images/run.png" width="300" alt="FAgent Run tab with logs, hot reload and hot restart" />
  <img src="https://raw.githubusercontent.com/sb-dor/FAgent/main/docs/images/code.png" width="300" alt="FAgent Code view with Dart analysis" />
  <img src="https://raw.githubusercontent.com/sb-dor/FAgent/main/docs/images/rules.png" width="300" alt="FAgent built-in Flutter rules and skills" />
  <img src="https://raw.githubusercontent.com/sb-dor/FAgent/main/docs/images/new-project.png" width="300" alt="FAgent new project wizard" />
</p>

-----

# Frustbite — audio for Dart & Flutter

#### Own project · open source

Dart · Flutter · Rust (FFI, WebAssembly)

**Frustbite** reads audio from pure Dart: stream info, tags, cover art, waveforms and PCM. A Rust
core does the decoding and is reached through FFI on Android, iOS, macOS, Linux and Windows and
through WebAssembly on the web (dart2js and dart2wasm). No FFmpeg and no C codecs.

## Features

- Decodes MP3, AAC-LC (M4A, ADTS), ALAC, FLAC, Vorbis, Opus and WAV.
- Peak or RMS waveforms with bounded memory, even for hour-long files.
- Tags and embedded cover art.
- `waveformAsync` and `decodeAsync` run on a background isolate.
- Benchmarks (180 s stereo file): WAV decoding 9x faster than the pure-Dart `wav` package, MP3
  decoding 83x faster than a pure-Dart decoder.
- CI, a documentation site and a minimal Flutter showcase.

Built with AI coding agents to my specs and rules; I review every change. The repository structure
and release flow are adapted from PlugFox's pixer (MIT).

_Take a look at the source code
on [GitHub](https://github.com/sb-dor/frustbite) and the
[documentation](https://sb-dor.github.io/frustbite/)_

## Screenshots

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/frustbite/main/docs/images/showcase-ios.png" width="250" alt="Frustbite showcase on iPhone" />
  <img src="https://raw.githubusercontent.com/sb-dor/frustbite/main/packages/benchmark/chart.png" width="520" alt="Frustbite benchmark chart" />
</p>

-----

# Packly — Travel Packing List

#### Own project

Flutter · AI (Google Gemini) · offline sync

**Packly** keeps every packing list in one place, organized and synced across devices. Its newest
feature is an **AI photo scan**: lay your things out, take one photo, and the app recognises the
items, sorts them into categories and builds the packing list automatically. You choose what gets
added.

## Features

- **Scan a photo, get a list**: AI finds the items in the photo and sorts them into categories.
- **A list for every trip** with a destination and dates; active and archived trips are kept apart.
- **Templates**: save any trip as a template or start from a ready-made one (weekend, beach,
  business, winter).
- **Categories with emoji**, quantities and drag-to-reorder.
- **Import a list** pasted from notes or a chat; Packly sorts it into categories with a preview.
- **Packing progress** down to the percentage.
- **Share or print** a list, or save it as a PDF.
- **Sign in with Google or email**; lists sync across devices and work **offline**, syncing when
  back online.
- Light and dark themes.

_Take a look at the app
on [Google Play Store](https://play.google.com/store/apps/details?id=com.bdaynabday.packly)_

## Screenshots

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/packly/screenshot_01.webp" width="150" alt="Packly add items from a photo" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/packly/screenshot_02.webp" width="150" alt="Packly AI-found items to review" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/packly/screenshot_03.webp" width="150" alt="Packly packing list by category" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/packly/screenshot_04.webp" width="150" alt="Packly all trips" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/packly/screenshot_05.webp" width="150" alt="Packly packing progress" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/packly/screenshot_06.webp" width="150" alt="Packly weekend trip list" />
</p>

-----

# Pregnancy Tracker

#### Own project

Flutter · offline · English and Russian

**Pregnancy Tracker** walks with the user through pregnancy one week at a time: how the baby is
developing, changes in the body, and practical tips. Medical content follows WHO, NHS, ACOG, CDC
and Ministry of Health sources. Everything stays on the phone: no account, no ads, no tracking.

## Features

- **Week by week**: baby development and size, body changes and tips, with guidance that follows
  WHO, ACOG or the Russian Ministry of Health.
- **Tools**: contraction timer, movement counting, symptoms, weight, notes, appointments and a
  hospital bag checklist.
- **Reminders** for appointments and weekly updates.
- **Warning signs** on every week that mean the user should contact the care team.
- **Private by design**: data stays on the device and can be exported at any time.
- Available in **English and Russian**.

_Take a look at the app
on [Google Play Store](https://play.google.com/store/apps/details?id=com.bdaynabday.pregnancy)_

## Screenshots

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/pregnancy_tracker/screenshot_01.webp" width="150" alt="Pregnancy Tracker today screen" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/pregnancy_tracker/screenshot_02.webp" width="150" alt="Pregnancy Tracker weeks list" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/pregnancy_tracker/screenshot_03.webp" width="150" alt="Pregnancy Tracker week guidance" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/pregnancy_tracker/screenshot_04.webp" width="150" alt="Pregnancy Tracker tools" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/pregnancy_tracker/screenshot_05.webp" width="150" alt="Pregnancy Tracker contraction timer" />
</p>

-----

# My work at Avera Inc. (2022 – 2026)

From February 2022 to November 2026 I was the main Flutter developer at Avera Inc., building POS
Cloud, Hotel CRM, Construction CRM and Doru24. I also wrote Laravel backends for POS Mobile, PizzaHouse.tj, Alshema and part of TajMix. The source
code of these apps belongs to the company and is private; the sections below describe them.

# Doru24 (not released yet)

#### Flutter · Android and iOS · in development

**Doru24** is a pharmacy marketplace made of two Flutter apps:

- **Customer app:** browse medicines and compare prices across pharmacies without an account, then
  sign in to order, upload prescription photos, pick a delivery address, track orders and leave
  reviews.
- **Pharmacy staff app:** an order queue with barcode-scan picking and courier assignment,
  prescription checks for managers and owners, stock with expiry-date batches, product requests and
  a daily dashboard. Employee, manager and owner roles; Russian, English and Tajik.

-----

# Avera POS Reports

Flutter

**Avera POS Reports** is an offline-first companion app for owners and managers using Avera POS.
It keeps essential business data close at hand, with sales and revenue reports for custom periods,
period-over-period comparisons, inventory levels and stock movement, staff and shift performance,
and a dashboard of the most important figures. Reports remain available without an internet
connection and synchronize with the Avera POS server when the device comes back online. The app is
designed for shops, cafés, restaurants, and retail outlets and requires an active Avera POS account.

_Take a look at the app
on [Google Play Store](https://play.google.com/store/apps/details?id=tj.avera.reports)_

## Screenshots

### Android — Portrait

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_reports/screenshot_01.webp" width="150" alt="Avera POS Reports revenue overview" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_reports/screenshot_02.webp" width="150" alt="Avera POS Reports suppliers directory" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_reports/screenshot_03.webp" width="150" alt="Avera POS Reports shift monitoring" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_reports/screenshot_04.webp" width="150" alt="Avera POS Reports cash desk overview" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_reports/screenshot_05.webp" width="150" alt="Avera POS Reports inventory levels" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_reports/screenshot_06.webp" width="150" alt="Avera POS Reports product search and scanner" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_reports/screenshot_07.webp" width="150" alt="Avera POS Reports top-selling products" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_reports/screenshot_08.webp" width="150" alt="Avera POS Reports receipts" />
</p>

### Android — Tablet

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_reports/tablet_01.webp" width="300" alt="Avera POS Reports tablet sales overview" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_reports/tablet_02.webp" width="300" alt="Avera POS Reports tablet top-selling products" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_reports/tablet_03.webp" width="300" alt="Avera POS Reports tablet inventory levels" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_reports/tablet_04.webp" width="300" alt="Avera POS Reports tablet cash flow" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_reports/tablet_05.webp" width="300" alt="Avera POS Reports tablet supplier balances" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_reports/tablet_06.webp" width="300" alt="Avera POS Reports tablet settings and directories" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_reports/tablet_07.webp" width="300" alt="Avera POS Reports tablet multi-store selector" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_reports/tablet_08.webp" width="300" alt="Avera POS Reports tablet business dashboard" />
</p>

-----

# Avera Hotel CRM

Flutter

**Avera Hotel CRM** turns a phone or tablet into a complete hotel reception terminal for
independent hotels and small chains. It connects directly to the hotel's Avera server, keeping
reservations, check-ins, payments, and room availability synchronized with the front desk in real
time. Staff can manage the full guest stay, scan passports and visas with OCR, use visual room and
rate calendars, run cash desk shifts and multicurrency payments, print documents from editable
templates, and monitor daily operations from anywhere. Role-based access and
multi-property support give each employee the right tools while keeping every hotel's data
separate.

The app has 101 feature modules and 218 test files.

_Take a look at the app
on [Google Play Store](https://play.google.com/store/apps/details?id=tj.avera.hotel&hl=en)_

## Screenshots

### Android — Portrait

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_hotel/screenshot_01.webp" width="150" alt="Avera Hotel CRM room calendar" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_hotel/screenshot_02.webp" width="150" alt="Avera Hotel CRM shift management" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_hotel/screenshot_03.webp" width="150" alt="Avera Hotel CRM accounts and balances" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_hotel/screenshot_04.webp" width="150" alt="Avera Hotel CRM revenue and expenses" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_hotel/screenshot_05.webp" width="150" alt="Avera Hotel CRM payments and refunds" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_hotel/screenshot_06.webp" width="150" alt="Avera Hotel CRM hotels, rooms, and room types" />
</p>

-----

# Avera Сохтмон (Avera Construction)

Flutter

**Avera Сохтмон** is a CRM built specifically for construction businesses, helping them manage
projects from planning to completion. It covers project tracking with budgets and completion
progress, blueprints and unit types, buildings and construction stages, clients and a sales
pipeline, contracts and document templates, and a full cashdesk for payments, transfers, and
withdrawals. Available on Web, Windows, macOS, Linux, Android, and iOS, it gives construction
companies a single tool to run their business from any device.

It has 120 feature modules, 65 of them with separate desktop and mobile layouts, contract and
installment-schedule PDFs, and five roles with 147 permissions. The web version runs on Firebase
Hosting at [avera-construction.web.app](https://avera-construction.web.app), and Windows gets its own
installer.

_Take a look at the app
on [Google Play Store](https://play.google.com/store/apps/details?id=tj.avera.sokhtmon&hl=en)_

## Screenshots

> **Info:** Each screenshot below is labeled with the platform it was captured on.

### Web

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_construction/web/web_1.png" width="300" alt="Web" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_construction/web/web_2.png" width="300" alt="Web" />
</p>

### Windows

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_construction/desktop/windows/windows_1.png" width="300" alt="Windows" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_construction/desktop/windows/windows_2.png" width="300" alt="Windows" />
</p>

### macOS

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_construction/desktop/macos/macos_1.png" width="300" alt="macOS" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_construction/desktop/macos/macos_2.png" width="300" alt="macOS" />
</p>

### Linux

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_construction/desktop/linux/linux_1.png" width="300" alt="Linux" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_construction/desktop/linux/linux_2.png" width="300" alt="Linux" />
</p>

### Android

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_construction/mobile/android/android_1.png" width="150" alt="Android" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_construction/mobile/android/android_2.png" width="150" alt="Android" />
</p>

### iOS

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_construction/mobile/ios/ios_1.png" width="150" alt="iOS" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_construction/mobile/ios/ios_2.png" width="150" alt="iOS" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_construction/mobile/ios/ios_3.png" width="150" alt="iOS" />
</p>

-----

# Avera POS Cloud

Flutter

**Avera POS Cloud** is the replacement for Avera POS Mobile, which struggled to gain traction with
businesses due to bugs stemming from its earlier, less experienced development. Avera POS Cloud
gives businesses full control over their sales, inventory, and reporting from any device. Available
on Web, Windows, macOS, Android, and iOS, it lets store owners and staff manage operations
seamlessly whether they're behind a desktop, on a tablet, or on the move. The web experience is a
separate app built with Nuxt + TypeScript, giving businesses a dedicated, fast interface for
managing their operations from the browser.

I built the Flutter app: about 400 feature modules covering sales, stock and supply, cash desks,
profit and cash-flow reports, HR (KPI, payroll), production, approvals and an audit log. It works
offline with Drift and syncs each entity separately, prints receipts over Bluetooth and TCP (ESC/POS),
and ships as two white-label builds.

**GPS tracking for field staff (Android).** Users with the Applicant role must turn on location and
open a shift before they can work. During the shift the app tracks location in the background
through a foreground service, drops inaccurate points, keeps them in an offline queue and uploads
them in batches, and notifies the employee when they approach a customer's address. Managers see
shifts and visited city zones. A public version of the module is in
[gps_tracker](https://github.com/sb-dor/gps_tracker).

_Take a look to the app
on [Google Play Store](https://play.google.com/store/apps/details?id=tj.avera.web&hl=ru)_
on [App Store](https://apps.apple.com/tj/app/avera-pos-cloud/id6757835809)

## Screenshots

> **Info:** Each screenshot below is labeled with the platform it was captured on.

### Web

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_cloud/web/web_1.png" width="300" alt="Web" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_cloud/web/web_2.png" width="300" alt="Web" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_cloud/web/web_3.png" width="300" alt="Web" />
</p>

### Windows

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_cloud/desktop/windows/windows_1.png" width="300" alt="Windows" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_cloud/desktop/windows/windows_2.png" width="300" alt="Windows" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_cloud/desktop/windows/windows_3.png" width="300" alt="Windows" />
</p>

### macOS

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_cloud/desktop/macos/macos_1.png" width="300" alt="macOS" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_cloud/desktop/macos/macos_2.png" width="300" alt="macOS" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_cloud/desktop/macos/macos_3.png" width="300" alt="macOS" />
</p>

### Android

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_cloud/mobile/android/android_1.png" width="150" alt="Android" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_cloud/mobile/android/android_2.png" width="150" alt="Android" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_cloud/mobile/android/android_3.png" width="150" alt="Android" />
</p>

### iOS

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_cloud/mobile/ios/ios_1.png" width="150" alt="iOS" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_cloud/mobile/ios/ios_2.png" width="150" alt="iOS" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_cloud/mobile/ios/ios_3.png" width="150" alt="iOS" />
</p>

-----

# Avera POS Mobile

Flutter + Laravel (including Admin app with Laravel)

**Avera Mobile POS** System is designed to empower businesses of all sizes, from small boutiques to
large retail chains. With its robust features, intuitive interface, and flexibility, it's the
perfect solution for stores and warehouses operations and taking business to the next level.

## Key features include:

- **Sales Management.**
- **Inventory Control**
- **Reporting**
- **Multi-Store Support**

**My role.** This was my first project at Avera: I started it as an intern in 2022 and kept developing
it until Avera POS Cloud replaced it. The system has four parts:

- **Client app (Flutter, Android and iOS):** sales and returns, supplier invoices and payments,
  warehouse transfers, stocktakes, assortments and price changes, discounts, a cash desk with
  currency conversion, and reports with charts. It works offline with SQLite, scans barcodes,
  prints receipts on Bluetooth ESC/POS printers, creates PDF invoices and tracks employees on shift
  by city zones.
- **Backend (Laravel):** a REST API with 239 routes and support for several stores.
- **Admin app (Flutter) and its backend (Laravel):** used by Avera staff to give clients access:
  client stores, servers and databases, tariffs and payments.

_Take a look to the app
on [Google Play Store](https://play.google.com/store/apps/details?id=tj.avera.posmobile)_
on [App Store](https://apps.apple.com/tj/app/avera-pos/id6494738399)

## Screenshots

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_mobile/Screenshot_2024-04-30-05-22-08-673_tj.avera.posmobile.jpg" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_mobile/photo_2024-04-30_05-44-07.jpg" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/avera_pos_mobile/photo_2024-04-30_05-44-03.jpg" width="150" />
  <img src="https://github.com/sb-dor/About-Projects/blob/master/assets/avera_pos_mobile/Screenshot_2024-04-30-05-22-34-571_tj.avera.posmobile.jpg" width="150" />
  <img src="https://github.com/sb-dor/About-Projects/blob/master/assets/avera_pos_mobile/Screenshot_2024-04-30-05-22-40-001_tj.avera.posmobile.jpg" width="150" />
  <img src="https://github.com/sb-dor/About-Projects/blob/master/assets/avera_pos_mobile/Screenshot_2024-04-30-05-22-48-553_tj.avera.posmobile.jpg" width="150" />
  <img src="https://github.com/sb-dor/About-Projects/blob/master/assets/avera_pos_mobile/Screenshot_2024-04-30-05-23-51-749_tj.avera.posmobile.jpg" width="150" />
  <img src="https://github.com/sb-dor/About-Projects/blob/master/assets/avera_pos_mobile/Screenshot_2024-04-30-05-23-57-118_tj.avera.posmobile.jpg" width="150" />
</p>

-----

# TajMix

Flutter + Laravel (partly)

**TajMix** transforms the car-buying experience, making it seamless and hassle-free.
With powerful search filters, side-by-side car comparisons, and fair price evaluations, finding the
perfect vehicle has never been easier. Effortlessly update your contact details, explore detailed
listings, and make informed decisions—all in one intuitive app.

_Take a look to the app
on [Google Play Store](https://play.google.com/store/apps/details?id=tj.avera.tajmix)_
on [App Store](https://apps.apple.com/ru/app/tajmix/id6748384879?platform=iphone)

## Screenshots

> **Info:** Test project images were used because the real ones contain pictures of actual cars and
> license plates, which cannot be used due to privacy restrictions.

https://github.com/user-attachments/assets/276551eb-c524-4e28-bf8b-4d0e4d1a82e7
<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/drom.tj/Simulator Screenshot - iPhone 16 - 2025-03-23 at 09.41.13.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/drom.tj/Simulator Screenshot - iPhone 16 - 2025-03-23 at 09.41.46.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/drom.tj/Simulator Screenshot - iPhone 16 - 2025-03-23 at 09.42.24.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/drom.tj/Simulator Screenshot - iPhone 16 - 2025-03-23 at 09.42.35.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/drom.tj/Simulator Screenshot - iPhone 16 - 2025-03-23 at 09.44.22.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/drom.tj/Simulator Screenshot - iPhone 16 - 2025-03-23 at 09.44.37.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/drom.tj/Simulator Screenshot - iPhone 16 - 2025-03-23 at 09.44.57.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/drom.tj/Simulator Screenshot - iPhone 16 - 2025-03-23 at 09.45.08.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/drom.tj/Simulator Screenshot - iPhone 16 - 2025-03-23 at 09.45.32.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/drom.tj/Simulator Screenshot - iPhone 16 - 2025-03-23 at 09.45.53.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/drom.tj/Simulator Screenshot - iPhone 16 - 2025-03-23 at 09.46.22.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/drom.tj/Simulator Screenshot - iPhone 16 - 2025-03-23 at 09.46.27.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/drom.tj/Simulator Screenshot - iPhone 16 - 2025-03-23 at 10.13.30.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/drom.tj/Simulator Screenshot - iPhone 16 - 2025-03-23 at 09.49.15.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/drom.tj/Simulator Screenshot - iPhone 16 - 2025-03-23 at 09.49.46.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/drom.tj/Simulator Screenshot - iPhone 16 - 2025-03-23 at 09.49.56.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/drom.tj/Simulator Screenshot - iPhone 16 - 2025-03-23 at 09.50.31.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/drom.tj/Simulator Screenshot - iPhone 16 - 2025-03-23 at 09.50.49.png" width="150" />
</p>

-----

# PizzaHouse.tj

Flutter + Laravel

**PizzaHouse.tj** revolutionizes the way you order pizza, bringing convenience and deliciousness
right
to your fingertips. With our user-friendly interface and extensive menu options, satisfying your
pizza cravings has never been easier.

_Take a look to the app
on [Google Play Store](https://play.google.com/store/apps/details?id=tj.avera.pizzahouse)_
on [App Store](https://apps.apple.com/tj/app/pizzahouse-tj/id6447666135)

## Screenshots

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/pizza_house/Screenshot_2024-04-30-05-50-46-144_tj.avera.pizzahouse.jpg" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/pizza_house/Screenshot_2024-04-30-05-51-00-096_tj.avera.pizzahouse.jpg" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/pizza_house/Screenshot_2024-04-30-05-51-10-929_tj.avera.pizzahouse.jpg" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/pizza_house/Screenshot_2024-04-30-05-51-20-893_tj.avera.pizzahouse.jpg" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/pizza_house/Screenshot_2024-04-30-05-51-36-786_tj.avera.pizzahouse.jpg" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/pizza_house/Screenshot_2024-04-30-05-51-39-672_tj.avera.pizzahouse.jpg" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/pizza_house/Screenshot_2024-04-30-05-51-55-260_tj.avera.pizzahouse.jpg" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/pizza_house/Screenshot_2024-04-30-05-52-26-656_tj.avera.pizzahouse.jpg" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/pizza_house/Screenshot_2024-04-30-05-52-33-558_tj.avera.pizzahouse.jpg" width="150" />
</p>

-----

# Komnata (Has't released yet)

Flutter + Laravel

**Komnata** transforms the way you find and list apartments, bringing your perfect space
right to your fingertips. With our intuitive interface and extensive property options, discovering
your next home has never been easier.

## Screenshots

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/komnata/Simulator%20Screenshot%20-%20iPhone%2016%20-%202025-11-30%20at%2012.25.51.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/komnata/Simulator%20Screenshot%20-%20iPhone%2016%20-%202025-11-30%20at%2012.25.56.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/komnata/Simulator%20Screenshot%20-%20iPhone%2016%20-%202025-11-30%20at%2012.19.12.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/komnata/Simulator%20Screenshot%20-%20iPhone%2016%20-%202025-11-30%20at%2012.19.31.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/komnata/Simulator%20Screenshot%20-%20iPhone%2016%20-%202025-11-30%20at%2012.20.15.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/komnata/Simulator%20Screenshot%20-%20iPhone%2016%20-%202025-11-30%20at%2012.26.07.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/komnata/Simulator%20Screenshot%20-%20iPhone%2016%20-%202025-11-30%20at%2012.27.30.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/komnata/Simulator%20Screenshot%20-%20iPhone%2016%20-%202025-11-30%20at%2012.27.41.png" width="150" />
</p>

-----

# Ecommerce Admin App

Flutter + Laravel

**Ecommerce Admin App** is a draft tool designed to manage the backend operations of the Ecommerce
App.
It offers a comprehensive solution for overseeing product listings, tracking orders, and managing
customer information. With features like real-time inventory updates, customizable product pages,
and detailed sales analytics, this app streamlines ecommerce operations. It also supports bulk
product uploads via Excel file imports, saving time on manual entry. As a draft version, this app
is a prototype intended for the development of real, fully-functional ecommerce applications.

## Screenshots

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_admin/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.19.34.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_admin/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.20.07.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_admin/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.19.20.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_admin/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.20.10.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_admin/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.18.07.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_admin/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.17.04.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_admin/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.17.32.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_admin/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.16.37.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_admin/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.16.31.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_admin/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.19.30.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_admin/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.20.35.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_admin/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.21.09.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_admin/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.21.15.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_admin/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.21.25.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_admin/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.21.30.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_admin/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.21.42.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_admin/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.24.56.png" width="150" />
</p>

-----

# Ecommerce App

Flutter + Laravel

**Ecommerce App** offers a seamless shopping experience, allowing users to browse, search, and
purchase products with ease. Featuring a clean, intuitive interface, it lets customers view detailed
product descriptions, read reviews, and make secure payments. With personalized recommendations and
easy navigation, the app ensures an enjoyable shopping journey. The app also supports real-time
order
tracking and provides notifications for special deals and promotions, ensuring users never miss out
on
the latest offers. Whether shopping for essentials or discovering new products, Ecommerce App brings
everything you need right to your fingertips. This version is a draft prototype intended for the
development of real, fully-functional ecommerce applications.

## Screenshots

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_app/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.25.31.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_app/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.25.52.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_app/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.26.06.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_app/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.26.15.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_app/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.26.21.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_app/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.26.32.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_app/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.26.53.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_app/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.27.04.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_app/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.27.07.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_app/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.27.20.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_app/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.27.25.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_app/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.27.31.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_app/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.28.09.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_app/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.28.52.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_app/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.29.07.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_app/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.29.48.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_app/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.29.54.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_app/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.30.09.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_app/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.30.17.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_app/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.30.21.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ecommerce_app/Simulator Screenshot - iPhone 16 - 2025-03-23 at 13.30.36.png" width="150" />
</p>

-----

# FTube

#### Own project

FTube is a versatile Flutter application that allows users to watch, download videos, and extract
audios from videos effortlessly. With its intuitive interface and powerful features, FTube
revolutionizes your video streaming and downloading experience.

## Features

- **Video Downloading**: FTube provides to download any video or video's audio from YouTube,
  with just a few taps.
- **Audio Extraction**: Extract audio tracks from videos and save them as MP3.
- **Multiple Resolutions**: Choose from a range of video resolutions to ensure optimal viewing
  quality or save storage space.
- **Customizable Downloads**: Personalize your download settings to suit your preferences, including
  download location, video quality, and more.
- **User-Friendly Interface**: Enjoy a clean and intuitive user interface designed to enhance your
  navigation and usability experience.

_Take a look to the app's releases
on my [GitHub Page](https://github.com/sb-dor/FTube)

_If you want to download the latest version of the app take a look
this [link](https://github.com/sb-dor/FTube/releases)

## Screenshots

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ftube/Screenshot_20240317_114456.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ftube/Screenshot_20240317_114547.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ftube/Screenshot_20240317_114712.png" width="150" />
  <img src="https://github.com/sb-dor/About-Projects/blob/master/assets/ftube/Screenshot_20240317_114652.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ftube/Screenshot_20240317_114808.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ftube/Screenshot_20240317_114848.png" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/ftube/Screenshot_20240317_114951.png" width="150" />
</p>

-----

# Zudras

#### Participated in the development of the application!

The grocery ordering app provides an easy-to-use interface for purchasing essential items. It offers
users a wide range of products to browse and order. Customers can personalize their orders and
choose a convenient delivery time. Thanks to available promotions and discounts, users can save on
purchases. Overall, it is a convenient solution for hassle-free grocery shopping.

_Take a look to the app
on [Google Play Store](https://play.google.com/store/apps/details?id=tj.avera.estore)_
on [App Store](https://apps.apple.com/tj/app/zudras-tj/id6446891667)

## Screenshots

<p align="center">
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/zudras.tj/zudras1.jpg" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/zudras.tj/zudras2.jpg" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/zudras.tj/zudras3.jpg" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/zudras.tj/zudras4.jpg" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/zudras.tj/zudras5.jpg" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/zudras.tj/zudras6.jpg" width="150" />
  <img src="https://raw.githubusercontent.com/sb-dor/About-Projects/master/assets/zudras.tj/zudras7.jpg" width="150" />
</p>
