---
title: "Activitat: Gestió de Contrasenyes"
author: "Equip Tècnic"
date: "2026-11-09"
description: "Manual operatiu i anàlisi comparativa per a la implementació d'un gestor de contrasenyes corporatiu."
keywords: ["seguretat", "bitwarden", "keepassxc", "gestor de contrasenyes", "manual operatiu"]
---

# Activitat: Gestió de Contrasenyes

## Fase 1: Anàlisi i Justificació

### 1. Introducció i Justificació

L'ús de credencials febles o reutilitzades suposa un dels vectors de risc més crítics per a qualsevol organització:

* **Atacs de força bruta i diccionari:** Eines automatitzades capaços de comprovar milions de combinacions per segon. Si la clau és poc complexa, resulta compromesa de manera immediata.
* **Credential stuffing:** Si es produeix una filtració de credencials en un servei extern i l'usuari empra la mateixa contrasenya a l'entorn de treball, els atacants aconsegueixen accés directe als nostres sistemes (correu, VPN, etc.).
* **Gestió ineficient:** Registrar claus en suports físics, fulls de càlcul sense xifrar o arxius de text plans impedeix auditar accessos i vulnera la traçabilitat.

#### Per què cal implementar un gestor?

* Genera automàticament claus robustes, extenses i úniques per a cada aplicació sense necessitat de memoritzar-les.
* Centralitza i protegeix tota la informació sota una única contrasenya mestra fortament xifrada.
* Mitiga l'impacte del phishing, atès que les extensions oficials només faciliten les credencials si el domini de destí coincideix plenament.

---

### 2. Comparativa Tècnica: Bitwarden vs. KeePassXC

| Criteri Tècnic | Bitwarden (Online / Núvol) | KeePassXC (Offline / Escriptori) |
| :--- | :--- | :--- |
| **Emmagatzematge** | Centralitzat en infraestructura pròpia o al núvol del proveïdor. | Fitxer local xifrat (`.kdbx`) allotjat a disc o dispositiu extern. |
| **Xifratge i Seguretat** | Arquitectura Zero-Knowledge extrem a extrem amb AES-256. | Protecció local mitjançant AES-256 o ChaCha20. Claus només en memòria RAM. |
| **Sincronització** | Transparència i automatització entre tots els dispositius registrats. | Manual (transferència de fitxers) o mitjançant serveis de tercers (Nextcloud/Syncthing). |
| **Multi-dispositiu** | Excel·lent cobertura (Windows, Linux, macOS, iOS, Android, navegadors). | Bona a sistemes d'escriptori; requeriment d'aplicacions externes en mòbils. |
| **Llicència i Cost** | Open Source (GPLv3). Model freemium amb opcions empresarials. | Open Source (GPLv3). Gratuït, sense models de subscripció. |
| **Dependència de Xarxa** | Requereix connexió per actualitzar (disposa de mode de lectura offline). | Completament autònom respecte a Internet (apte per a entorns aïllats). |

---

### 3. Avantatges i Inconvenients

#### Bitwarden (Online)
* **Pros:** Interfície intuïtiva, sincronització contínua i facilitat per compartir elements de forma segura entre membres del departament tècnic.
* **Contres:** Estar subjecte a connectivitat de xarxa per actualitzar canvis i emmagatzematge en servidors externs.

#### KeePassXC (Offline)
* **Pros:** Sobirania total sobre l'arxiu `.kdbx`, absència de trànsit cap a Internet i caràcter totalment lliure.
* **Contres:** Dependència absoluta de còpies de seguretat pròpies davant fallades de disc, i gestió manual de la sincronització entre equips i terminals mòbils.

---

### 4. Recomanació

Es proposa l'ús de **Bitwarden** per al personal tècnic. La sincronització automàtica entre terminals i l'agilitat en la compartició de recursos corporatius compensen el model local, garantint alhora un estàndard de seguretat elevat gràcies al xifratge Zero-Knowledge.

---

## Fase 2: Guia d'Ús Tècnica (Manual Operatiu - Bitwarden)

Aquest document detalla el procediment pas a pas per instal·lar, configurar i utilitzar Bitwarden com a solució de gestió de contrasenyes per a equips tècnics.

### 1. Instal·lació i Configuració Inicial

#### 1.1 Descàrrega i instal·lació de l'aplicació d'escriptori
1. Obre el navegador web a la màquina virtual (Windows 11) i accedeix a la ruta oficial: [Bitwarden Download](https://bitwarden.com/download/).
2. Descarrega el paquet d'instal·lació corresponent a Windows.
3. Executa l'arxiu obtingut (`Bitwarden-Installer.exe`) i completa l'assistent d'instal·lació seguint els paràmetres predeterminats.

#### 1.2 Alta d'usuari i Contrasenya Mestra
1. Un cop finalitzada la instal·lació, obre l'aplicació Bitwarden i selecciona l'opció **Crear compte** (*Create Account*).
2. Introdueix l'adreça de correu electrònic corporatiu assignada.
3. Estableix la **Contrasenya Mestra** (*Master Password*).

> **Important:** Aquesta clau és l'única eina capaç de desxifrar la resta del repositori. Es recomana una longitud superior a 14-16 caràcters, combinant majúscules, minúscules, dígits numèrics i caràcters especials. La seva pèrdua implica la impossibilitat irrecuperable d'accedir al compte.

4. (Opcional) Configura una pista recordatòria i valida la creació del compte.

---

### 2. Generació de Contrasenyes Segures

Per prevenir l'ús de patrons previsibles, es farà ús del generador integrat a l'aplicació:

1. Dins de l'entorn de Bitwarden (aplicació o extensió), localitza la secció de **Generador** (*Generator*).
2. Ajusta els criteris seguint la política de seguretat establerta:
   * **Tipus:** Contrasenya (*Password*).
   * **Longitud mínima:** 16 caràcters.
   * **Joc de caràcters actiu:** Majúscules (A-Z), Minúscules (a-z), Nombres (0-9) i Símbols (!@#$%^&*).
3. Selecciona **Generar contrasenya** o utilitza la drecera per copiar directament el codi aleatori generat.

---

### 3. Casos d'Ús i Emplenament Automàtic

#### 3.1 Emmagatzematge d'una credencial de correu
1. Accedix al panell **El meu repositori** (*Vault*) i prem el botó **+** (*Afegir element*).
2. Completa els camps obligatoris:
   * **Nom:** Correu Corporatiu / Gmail Enterprise.
   * **Usuari:** `usuari@empresa.com`.
   * **Contrasenya:** Utilitza el generador automàtic per assignar una clau complexa.
   * **URI / Web:** `https://mail.google.com` (o l'adreça corresponent al servei de correu).
3. Desa els canvis prement **Desar** (*Save*).

#### 3.2 Emmagatzematge d'una credencial d'aplicació o servei intern
1. Prem novament el botó **+** (*Afegir element*).
2. Introdueix els atributs del servei corporatiu (per exemple, infraestructura interna o plataforma Cloud):
   * **Nom:** Panell Servidor Web / Nextcloud.
   * **Usuari:** `admin_tecnic`.
   * **Contrasenya:** Clau generada de 16+ caràcters.
   * **URI 1:** `https://panell.empresa.local`.
3. Confirma l'operació amb **Desar**.

---

### 4. Gestió de Còpies de Seguretat (Backup)

#### 4.1 Exportació de dades del repositori
Per garantir la disponibilitat de la informació davant qualsevol contingència, s'ha de realitzar regularment una còpia de seguretat:

1. Dins de l'aplicació de Bitwarden, navega fins a **Ajustos** (*Settings*) > **Exportar repositori** (*Export Vault*).
2. Tria el format d'exportació adequat:
   * **JSON xifrat (*Encrypted JSON*):** Opció recomanada. Preserva el xifratge de les dades mitjançant la contrasenya del compte o una clau addicional de xifratge.
   * **CSV / JSON pla:** Desaconsellat per motius de seguretat, ja que exposa les contrasenyes en text clar.
3. Introdueix la teva **Contrasenya Mestra** per autoritzar i descarregar l'arxiu.

#### 4.2 Directrius d'emmagatzematge segur de la còpia
Per protegir el fitxer de còpia exportat, cal seguir aquestes premisses:
* **Dispositiu USB xifrat:** Emmagatzema el fitxer de backup en una memòria USB protegida amb BitLocker (entorns Windows) o LUKS (entorns Linux).
* **Emmagatzematge al núvol segur:** En cas d'utilitzar emmagatzematge en línia, s'ha de verificar que el fitxer estigui prèviament xifrat (mitjançant el format JSON xifrat de Bitwarden o eines com VeraCrypt o 7-Zip amb xifratge AES-256).
* **Custòdia física:** Mantingues la memòria USB en un espai físic segur, com ara una caixa de seguretat o un armari tancat de l'oficina.