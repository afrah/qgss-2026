# QGSS 2026 — Frequently Asked Questions

> For full details, always refer to the official **QGSS 2026 Attendee Guide**. This FAQ summarizes the most common community questions and points to the guide and to qBraid's official docs where relevant.

## IBM Quantum / QGSS

### Labs & Submissions

**Where can I find the labs?**
All labs are posted on the QGSS 2026 community GitHub repository:
https://github.com/qiskit-community/qgss-2026

**Is Lab 0 graded?**
No. Lab 0 is a pre-event setup exercise and is not graded.

**How many labs are there, and how long do they take?**
There are **4 graded core labs**. Each lab takes an estimated **2–4 hours** to complete. Bonus exercises are **not** required for completion.

**What is the last day for lab submission?**
Labs must be submitted no later than **Wednesday, 31 July, 12:00 PM ET**, as stated in the Attendee Guide. You can submit each notebook **multiple times** — only your **highest score** counts toward your cumulative average.

**How do I check the status of a submitted job?**
Lab notebooks contain a commented cell with the job IDs. After submitting, you should receive a confirmation message with job IDs for both the Sampler and Estimator. You can then check whether a job is `queued`, `done`, etc.

For details on monitoring jobs, retrieving submitted jobs, and more, see:
https://quantum.cloud.ibm.com/docs/en/guides/monitor-job

> **Note:** Hardware execution consumes your usage time. Be mindful of how much time you use on real hardware. Only run the optional hardware cells when you are ready, and monitor your usage in the IBM Quantum Platform dashboard.

> **Important:** Do **NOT** share your lab solutions on your personal GitHub or anywhere else. This may lead to disqualification from earning a badge.

**Lab0 reference documentation**

- Bits, gates and circuits — https://quantum.cloud.ibm.com/learning/en/courses/utility-scale-quantum-computing/bits-gates-and-circuits
- Qiskit implementation (multiple systems / quantum information) — https://quantum.cloud.ibm.com/learning/en/courses/basics-of-quantum-information/multiple-systems/quantum-information
- GHZ state — https://quantum.cloud.ibm.com/learning/en/courses/utility-scale-quantum-computing/utility-iii

### IBM Quantum Account

**How do I set up my IBM Quantum account for the labs?**
Grading and submission use the **upgraded IBM Quantum Platform** on IBM Cloud. If you haven't migrated yet, follow the official migration guide to register on the new platform. For QGSS, create an instance using the **Open Plan**, which includes **10 minutes of free QPU time per month**.

Account setup, saving your API key and instance (CRN), and authenticating with `QiskitRuntimeService`:
https://quantum.cloud.ibm.com/docs/en/guides/cloud-setup

> **Note:** In the notebook, both the **API key** and the **CRN** must be entered inside `"double quotes"`.

**I don't have a credit card. How do I create an IBM Quantum account?**
Creating a new account currently requires a credit card for verification. To avoid any charges during QGSS, be sure to select the **Open Plan**, which offers limited free usage.

Alternatively, there is a **30-day free trial that does not require a credit card**:
https://cloud.ibm.com/registration?utm_content=quantum-trial&target=https%3A%2F%2Fquantum.cloud.ibm.com

**What if my trial account has expired? / I can't create an instance / my account won't convert to a trial. What do I do?**

First, don't worry about timing: because submissions stay open until the last day (**29 July**), an expired trial account won't stop you from finishing the school — you can still submit all your solutions on the final day. If you have an **academic email address**, you can also create a longer trial account via IBM SkillsBuild: https://skillsbuild.org/

If you specifically **can't create an instance**, this usually happens when your IBM Cloud account was created **before** the trial registration flow existed and was never completed with a credit card. These accounts can't be converted into trial accounts. Register a **new trial account with a different email address**:

1. Clear all cookies and site data for IBM websites (or use a private/incognito window).
2. Disable any ad blockers or similar browser extensions.
3. Close and reopen the browser.
4. Open the trial registration link:
   https://cloud.ibm.com/registration?utm_content=quantum-trial&target=https%3A%2F%2Fquantum.cloud.ibm.com
5. Register with a **different email** than before and choose a **personal account**.
6. Confirm the email with the verification code.
7. No subscription or payment info should be required. In **Account Settings**, the Account Type should show **Trial**.
8. Generate an API key and select **Create New Instance**. Wait for it to be created (refresh if needed).

It's perfectly fine if this email doesn't match the one you registered for the event with — see the badge-claim note below.

### Badges, Certificates & Tracks

**What are the requirements for a certificate or badge?**
You must watch **80% of all core IBM Quantum lectures** to qualify. Special guest lectures, panel discussions, Q&As, and workshops are **not graded** and do not affect your final score. There are three levels:

- **Certificate of Completion** — 80% of core lectures viewed
- **Quantum Fundamentals Badge** — 80% of core lectures viewed **+ 1–2 labs** completed
- **Quantum Excellence Badge** — 80% of core lectures viewed **+ 3–4 labs** completed

At the end of the event you'll complete a form to claim your badge. Provide your full name and the **IBM Cloud IAM ID** linked to the account you used during QGSS (the form includes instructions for finding your IAM ID). This is how your badge is matched even if the account email differs from your event-registration email.

**Is there attendance?**
You can watch sessions either live or recorded. The 80% watch requirement is calculated by the platform (based on how much of each video you have watched).

**How much time should I plan for?**
Plan for a minimum of **35 hours** across the full Summer School; **45 hours** is recommended to allow time for discussion and collaboration with other students. The program is self-paced apart from the final lab submission deadline.

### ON24 (Streaming Platform)

**What is ON24, and where do I watch the lectures?**
ON24 is the platform used for all streamed and live content this year — lectures, labs, workshops, and related details (registration required).

**How do I access ON24 / join a session?**

1. Head to the **Qiskit Global Summer School engagement hub** (link in the Attendee Guide, page 13). You must be registered for the event, and you may need to log in with the email address you registered with.
2. Once logged in, navigate to a tab: **Lectures**, **Lab**, or **Workshops**.
3. Click the session you want to join. If it has already happened, press play to open the on-demand media player.

> **Tip:** Use **Google Chrome** for the best (headache-free) viewing experience. If a pop-up asks you to register, click the **login** tab and enter your registered email.

**I can't log in to ON24 / I'm having trouble accessing a session. Who do I contact?**
First, make sure you're logging in with the **exact email address you registered for the event with**, try **Google Chrome**, and clear your cache or use a private/incognito window. If you still can't get in, reach out in the Discord `#technical-support` channel, or visit https://support.on24.com/hc/en-us/sections/20952746518939-Support. Please allow **1–2 business days** for a response.

### Discord & Support

**How do I get access to the QGSS Discord channels?**
Click the **"Verify"** button in the `#verification` channel. This confirms your status as a Summer School student and unlocks the channels so you can collaborate. Key core channels: `#verification`, `#announcements`, `#code-of-conduct`.

> **Note:** Discord is a third-party platform. IBM does not control, monitor, or endorse user-generated content on the server. Any issues with platform functionality, account access, or content moderation should be directed to Discord.

**Where do I go for support?**

- `#general-support` — general support questions or requests
- `#technical-support` — support requests regarding the IBM Quantum Platform
- **Email:** quantum.events@us.ibm.com — for requests involving personal or sensitive information (may have longer reply times)

Please allow **1–2 business days** for a response, avoid submitting the same request in multiple places, and avoid DMing the QGSS team.

**How do I report a Code of Conduct violation?**
Review the IBM Quantum Community Code of Conduct (in the Attendee Guide / `#code-of-conduct`). You can report anonymous violations or inappropriate content by emailing **quantum.events@us.ibm.com**.

### General

**Will the sessions be recorded? Is live participation required?**
Yes — all lectures, core labs, panels, and Q&As are recorded. Live participation is encouraged but **not required**; you can join live or watch on-demand.

**Can my friend/colleague be added to the Summer School or Discord?**
Unfortunately no — the event is at capacity.

**Can I download or share the course content?**
Not yet. The team will share the content (and more) as an update to the **Qiskit YouTube channel** later this year. Please keep course materials among registered attendees only.

---

## Environment

**Which environments can I use to run the labs?**

- qBraid Lab — recommended for QGSS (Qiskit preconfigured, QGSS 2026 env ready)
- Google Colab
- Locally via Jupyter Notebook or Visual Studio Code

IBM also lists other supported online lab environments (OVHcloud AI Notebooks, IBM watsonx.ai / Watson Studio, Microsoft Azure ML Studio) in the official guide:
https://quantum.cloud.ibm.com/docs/en/guides/online-lab-environments

### qBraid (Environment & Kernel)

qBraid is **recommended for beginners** because it comes with the QGSS 2026 environment pre-configured. For all qBraid-specific questions, refer to qBraid's official documentation below. A qBraid setup video is available in the `#qbraid-support` channel.

**How do I select the environment and kernel for each lab?**
An "active" environment in the sidebar only means it is available in the kernel selector. To actually use an environment in a notebook, you must select it explicitly from the kernel selector in the **upper-right corner** of the notebook.

- See qBraid docs — Switch notebook kernel:
  https://docs.qbraid.com/v2/lab/user-guide/notebooks#switch-notebook-kernel

**I'm getting `ModuleNotFoundError`. What should I do?**
This usually means you need to switch your kernel to the QGSS 2026 environment. See the switch-notebook-kernel link above.

**Do I need to manually shut down my qBraid instance? / How do I manage session behavior?**
You can configure session check-ins, idle timeout, and auto-shutdown in the qBraid Lab Settings.

- See qBraid docs — Settings:
  https://docs.qbraid.com/v2/lab/user-guide/settings

(Thanks to: [Maja](https://github.com/Q-Bees), [Dustin](https://github.com/phasefactor), [Dimple](https://github.com/dimple12M) and awesome QGSS mentors)
