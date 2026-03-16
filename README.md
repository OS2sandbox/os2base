<p align="center">
  <h1 align="center">🌳 os2nornnet</h1>
  <p align="center">
    <strong>Device Management via GitOps</strong>
    <br />
    <br />
    <img src="https://img.shields.io/badge/platform-linux%20%7C%20bootc%20%7C%20systemd-blue" alt="Platform" />
    <img src="https://img.shields.io/badge/GitOps-blueviolet?logo=git&logoColor=white" alt="GitOps" />
    <a href="https://github.com/OS2sandbox/openclient-poc/issues">
      <img src="https://img.shields.io/github/issues/OS2sandbox/openclient-poc?color=informational&logo=github" alt="Open Issues" />
    </a>
    <img src="https://img.shields.io/badge/status-active%20%2F%20building-green" alt="Status" />
    <img src="https://img.shields.io/badge/license-TBD-lightgrey" alt="License" />
  </p>
</p>

| 🇩🇰 Dansk | 🇬🇧 English |
| :--- | :--- |
| _Nornnet leverer en professionel, moderne model for enheds håndtering ved at anvende eksisterende open-source standarder og metoder til skalerbar og sikker drift.._<br><br>👉 [**Læs mere**](#kernebegreber) | _Nornnet delivers a modern device management model, utilizing existing open-source standards and methods that ensures scalable and secure operations.._ <br><br>👉 [**Read more**](#key-concepts) |

<p align="center">
  <br />
  <strong>💡 Har du idéer eller fundet en fejl?</strong>
  <br />
  Vi bygger Nornnet i fællesskab, og alle bidrag er velkomne.
  <br />
  <a href="https://github.com/OS2sandbox/openclient-poc/issues">
    <strong>Deltag i samtalen på vores Issue Tracker →</strong>
  </a>
</p>

<br>

---

# Video: Getting Started with Bootable Containers 
[![Bootc: Getting Started](https://img.youtube.com/vi/bf1xqjLeA9M/maxresdefault.jpg)](https://www.youtube.com/watch?v=bf1xqjLeA9M)
> “I believe that bootable containers will change how we think about the IT infrastructure of the future.”
>
> In this video, Valentin Rothberg provides a concise overview of what bootable containers are, the technical concepts and architecture, as well as the value they provide. Bootable Containers take the same model we know and love from containerized applications and bring that to operating systems. Container tools like podman, docker, etc can now build, ship, and run operating systems just like applications. Bootc is the tool that brings containers to hardware.

<br><br><br>

### Kernebegreber

> De fem kernebegreber, der gør Nornnet robust og skalerbar.

#### 🏗️ Single Source of Truth med git
Flådens samlede tilstand defineres versioneret i Git. Infrastrukturændringer udføres via formelle **Pull Requests**, hvilket sikrer en fuld audit-log og 100% sporbarhed på alle ændringer.

#### 📦 Sikre, standardiserede OS-images
Operativsystem og konfigurationer leveres som uforanderlige **OCI-images**. Det sikrer, at alle enheder altid er identiske og sikkerhedsscannede, allerede før der rulles ud. Enhederne er låste som *read-only* for at undgå utilsigtet manipulation.

#### 🔒 Minimal angrebsflade
Enhederne benytter en **"pull"-model** til at hente opdateringer. Det betyder, at det ikke er nødvendigt med åbne management-porte (som SSH) ind udefra. Det sænker angrebsfladen betydeligt og gør systemet mere modstandsdygtigt.

#### 🛡️ Robuste opdateringer
Opdateringer sker transaktionelt. Det sikrer, at ingen enheder ender i en "halvfærdig" eller korrupt tilstand. Hvis et image fejler under udrulning, sørger systemet selv for en **automatisk rollback** til den forrige stabile version.

#### ⚙️ Indbygget livscyklus-styring
Vi fjerner behovet for tunge eksterne agenter ved at bruge Linux-systemets egen service manager: **systemd**. Den håndterer livscyklussen sikkert og effektivt som en integreret del af selve operativsystemet.

<br>

---

<br>

### Key Concepts
> The five key concepts that make Nornnet robust and scalable.

#### 🏗️ Git as Single Source of Truth
The fleet's desired state is version-controlled within Git. Changes are facilitated through formal **Pull Requests**, providing a complete audit log and full traceability for every modification.

#### 📦 Secure, Standardized OS Images
OS and configurations are delivered as immutable **OCI images**. This guarantees binary identity across the entire fleet. Images are pre-scanned for vulnerabilities, and the filesystem is locked as *read-only* during operation.

#### 🔒 Minimized Attack Surface
Devices utilize a **"pull" model** for updates, eliminating the need for open inbound management ports. This architecture hardens the devices against external threats and improves network resilience.

#### 🛡️ Robust Atomic Updates
Updates are transactional, preventing devices from entering corrupted intermediate states. Operational continuity is guaranteed via **automatic rollback** to the previous known-good state if an update fails validation.

#### ⚙️ Native Lifecycle Management
By utilizing the native linux service manager, **systemd**, we eliminate the need for third-party agents. Orchestration and service management are handled securely as a native part of the operating system.
