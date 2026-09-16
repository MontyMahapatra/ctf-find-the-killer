# 🔎 CTF: The NovaEdge Case — Find the Killer

**Category:** Digital Forensics / DFIR
**Difficulty:** Beginner / Intro
**Format:** Jeopardy-style, story-driven
**Flags:** 4

> ⚠️ **Challenge Notice:** The flags and final killer are intentionally **not published** here. Solve the investigation before looking for a walkthrough.

---

## 📖 The Story

Late on the night of **November 14, 2024**, **Arjun Mehta**, CEO and co-founder of **NovaEdge Technologies**, was found dead in his 5th-floor office.

Earlier that evening, Arjun told colleagues he was staying late to discuss a **“serious accounting issue”** with someone before the next morning’s board meeting.

Three people are known to have had access to the building that night:

| Suspect          | Role                                      |
| ---------------- | ----------------------------------------- |
| **Neha Kapoor**  | Co-founder / CFO                          |
| **Suresh Yadav** | Night security guard                      |
| **Priya Sinha**  | Ex-employee, terminated two weeks earlier |

You are the digital forensics analyst assigned to the case.

Four pieces of digital evidence have been recovered from company systems and personal devices.

Your mission is to analyze the evidence, recover the hidden flags, connect the clues, and determine **who killed Arjun Mehta**.

---

## 🎯 Objective

Analyze every file inside the `evidence/` directory and recover the hidden flag from each stage.

All flags follow this format:

```text
FLAG{...}
```

There are **4 flags total**.

The **4th flag reveals the killer**.

### Final submission format

```text
Flag 1: FLAG{...}
Flag 2: FLAG{...}
Flag 3: FLAG{...}
Flag 4: FLAG{...}

Killer: <name>
Motive: <one sentence>
```

---

## 🗂️ Evidence Files

| File                                 | Description                                                      |
| ------------------------------------ | ---------------------------------------------------------------- |
| `evidence/01_crime_scene_photo.jpg`  | Crime-scene photo auto-synced from a phone backup service        |
| `evidence/02_email_dump.txt`         | Exported company mail-server data containing raw message headers |
| `evidence/03_recovered_fragment.bin` | Corrupted fragment recovered from unallocated disk space         |
| `evidence/04_locked_evidence.zip`    | Password-protected archive recovered from a cloud backup         |

---

## 🧰 Suggested Tools

You can solve this challenge using common forensic utilities:

* `exiftool` — inspect image metadata / EXIF
* `strings` — extract readable text from binary data
* `xxd` — inspect binary data in hexadecimal
* `binwalk` — inspect recovered or embedded content
* `unzip` — open the final archive after discovering its password
* Any text editor — inspect raw email headers

**No expensive commercial tooling is required.**

---

## 🧩 Investigation Flow

### Evidence 1 — Photo

Start with the image.

Don't rely only on what you can see. Inspect the metadata and look for unusual information.

Pay particular attention to:

* Timestamps
* Software information
* Comments
* Other metadata fields

---

### Evidence 2 — Emails

Never trust the display name or email body alone.

Inspect the **raw email headers**.

Pay attention to:

* `Received:`
* `X-` prefixed headers
* Sender-related information

Compare what a suspect claims with what the mail infrastructure actually records.

---

### Evidence 3 — Recovered Fragment

The binary file is intentionally provided as raw recovered data.

Extract readable strings and examine the recovered information carefully.

Some evidence may help you **eliminate suspects** rather than directly identify the killer.

---

### Evidence 4 — Locked Archive

The final archive is password protected.

The password is **not intended to be brute-forced**.

Instead, it is derived from information discovered during the earlier investigation.

Once you recover the password, open the archive and obtain the final flag.

---

## 💡 Progressive Hints

Progressive hints are available in:

[`hints.md`](hints.md)

Try solving each evidence stage yourself before revealing the hints.

---

## 🏁 Challenge Rules

### 🚨 Please don't spoil the challenge

* **Do not publish the flags publicly.**
* Do not include flags in blogs.
* Do not include flags in YouTube videos.
* Do not include flags in screenshots or thumbnails.
* Do not post the actual flag values on LinkedIn or other social media.
* Walkthroughs are welcome, but **redact the flags**.
* You can share your methodology, commands, clues, and reasoning.

For example:

```text
FLAG{REDACTED}
```

Let's keep the challenge enjoyable for everyone who wants to solve it themselves.

---

## 🧠 Learning Objectives

This CTF is designed to practice:

* EXIF / metadata analysis
* Email-header investigation
* Basic binary-data analysis
* String extraction
* Evidence correlation
* Timeline reasoning
* Password discovery from forensic clues
* DFIR investigation methodology
* Analytical thinking

---

## 📌 Difficulty

**Beginner / Intro DFIR**

This challenge intentionally puts many of the required clues in front of you.

The main challenge is recognizing:

> **Where should I look?**

Then validating the evidence and connecting the artifacts together.

---

## ⚠️ Disclaimer

This is a **fictional training scenario** created for educational purposes.

All names, organizations, and events are fictional.

Use forensic and security techniques only in environments where you have appropriate authorization.

---

## 👤 Author

Created by **Monty Mahapatra** for digital-forensics and cybersecurity learning.

If you enjoyed the challenge:

⭐ Star the repository
🔗 Share it with other DFIR learners
💬 Tell me how you approached the investigation

**Happy hunting. 🔎**
