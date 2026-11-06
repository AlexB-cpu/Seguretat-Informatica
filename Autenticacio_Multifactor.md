
# NF1AA3 – Autenticació multifactor (MFA)

## Guia d'usuari: Configuració de l'autenticació multifactor amb Google Authenticator

**Activitat:** NF1AA3 – Autenticació multifactor  
**Objectiu:** Protegir els comptes corporatius mitjançant la verificació en dos passos.

---

## 1. Introducció

L'autenticació multifactor (MFA) és un sistema de seguretat que permet protegir els comptes informàtics mitjançant dos o més factors d'autenticació.

Tradicionalment, per iniciar sessió només calia introduir un nom d'usuari i una contrasenya. Amb l'MFA, a més de la contrasenya, cal proporcionar un segon element de verificació, com ara un codi temporal generat per una aplicació mòbil.

Aquesta mesura augmenta la seguretat dels comptes i dificulta que persones no autoritzades hi puguin accedir, encara que coneguin la contrasenya.

## 2. Requisits previs

Abans de començar, necessitarem:

- Un ordinador amb connexió a Internet.
- Un telèfon mòbil Android o iOS.
- Un compte corporatiu de Google del domini `mataro.epiaedu.cat`.
- Accés a Google Play o App Store.
- L'aplicació Google Authenticator instal·lada.

## 3. Instal·lació de Google Authenticator

**Pas 1.** Obrim la botiga d'aplicacions del nostre telèfon mòbil:

- Android: [Google Play](https://play.google.com/store/apps/details?id=com.google.android.apps.authenticator2).
- iPhone: [App Store](https://apps.apple.com/app/google-authenticator/id388497605).

**Pas 2.** Cerquem l'aplicació Google Authenticator.

**Pas 3.** Instal·lem l'aplicació i l'obrim.

**Pas 4.** Deixem l'aplicació preparada per afegir-hi el nostre compte corporatiu.

![Instal·lació de Google Authenticator](media/01.jpg)

*Figura 1. Instal·lació de Google Authenticator.*

## 4. Accés a la configuració de seguretat de Google

**Pas 1.** Obrim el navegador de l'ordinador i accedim al nostre compte corporatiu de Google.

**Pas 2.** Introduïm les nostres credencials (correu electrònic i contrasenya).

**Pas 3.** Accedim a la configuració del compte mitjançant aquest enllaç:

[Configuració de seguretat de Google](https://myaccount.google.com/security)

**Pas 4.** Comprovem que estem utilitzant el compte corporatiu correcte.

**Pas 5.** Busquem l'apartat «Inici de sessió a Google».

![Seguretat del compte Google](media/02.jpg)

*Figura 2. Configuració de seguretat del compte de Google.*

## 5. Activació de la verificació en dos passos

**Pas 1.** Dins de l'apartat «Inici de sessió a Google», seleccionem «Verificació en dos passos».

**Pas 2.** Google ens demanarà que confirmem la nostra identitat introduint la contrasenya.

**Pas 3.** Seguim les instruccions de l'assistent de configuració.

**Pas 4.** Vinculem el nostre telèfon mòbil al compte seguint les indicacions de Google.

**Pas 5.** Un cop activada la verificació en dos passos, seleccionem l'opció d'afegir o configurar una aplicació d'autenticació.

![Verificació en dos passos](media/03.jpg)

*Figura 3. Activació de la verificació en dos passos.*

## 6. Vinculació amb Google Authenticator

**Pas 1.** A la configuració de Google, seleccionem «Aplicació Authenticator».

**Pas 2.** Google mostrarà un codi QR a la pantalla de l'ordinador.

**Pas 3.** Obrim Google Authenticator al mòbil.

**Pas 4.** Seleccionem l'opció per afegir un compte i escollim «Escanejar un codi QR».

**Pas 5.** Apuntem la càmera del mòbil cap al codi QR que apareix a l'ordinador.

**Pas 6.** L'aplicació afegirà automàticament el compte i començarà a generar codis temporals de sis dígits.

**Pas 7.** Introduïm a Google el codi de sis dígits que apareix a l'aplicació per confirmar la vinculació.

És important introduir el codi abans que caduqui, ja que es renova periòdicament.

![Vinculació mitjançant QR](media/04.jpg)

*Figura 4. Vinculació del compte mitjançant el codi QR.*

## 7. Comprovació del codi d'autenticació

Un cop vinculat el compte, Google Authenticator començarà a generar codis temporals de sis dígits.

**Pas 1.** Obrim l'aplicació Google Authenticator.

**Pas 2.** Busquem el compte corporatiu que hem afegit.

**Pas 3.** Consultem el codi de sis dígits que apareix a la pantalla.

**Pas 4.** Introduïm el codi a Google quan ens ho demani.

Els codis canvien automàticament cada pocs segons i només són vàlids durant un període limitat.

![Codis de sis dígits](media/05.jpg)

*Figura 5. Codis temporals generats per Google Authenticator.*

## 8. Generació de codis de seguretat de reserva

És recomanable generar codis de seguretat per poder accedir al compte en cas de perdre el mòbil, quedar-se sense bateria o no tenir accés a l'aplicació d'autenticació.

**Pas 1.** Tornem a l'apartat «Verificació en dos passos» del compte de Google.

**Pas 2.** Cerquem l'opció «Codis de seguretat».

**Pas 3.** Seleccionem l'opció per generar els codis.

**Pas 4.** Google proporcionarà deu codis d'un sol ús.

**Pas 5.** Els descarreguem o imprimim i els guardem en un lloc segur.

Cada codi només es pot utilitzar una vegada.

> **Recomanació:** No compartiu els codis de seguretat amb ningú i guardeu-los en un lloc segur i separat del mòbil.

![Codis de seguretat](media/06.jpg)

*Figura 6. Generació dels codis de seguretat de reserva.*

## 9. Prova del funcionament de l'MFA

Per comprovar que la configuració s'ha realitzat correctament, iniciarem una sessió de prova.

**Pas 1.** Tanquem la sessió del compte de Google.

**Pas 2.** Tornem a iniciar sessió introduint el correu electrònic i la contrasenya.

**Pas 3.** Google sol·licitarà una segona verificació.

**Pas 4.** Seleccionem «Provar una altra manera» si volem utilitzar Google Authenticator.

**Pas 5.** Escollim l'opció de l'aplicació d'autenticació.

**Pas 6.** Obrim Google Authenticator i introduïm el codi temporal de sis dígits.

**Pas 7.** Si el codi és correcte, podrem accedir al nostre compte.

![Inici de sessió amb MFA](media/07.jpg)

*Figura 7. Inici de sessió amb el segon factor d'autenticació.*

## 10. Recomanacions de seguretat

Per mantenir el compte protegit, és important seguir aquestes recomanacions:

- Utilitzar una contrasenya llarga, segura i diferent per a cada servei.
- No compartir mai els codis de verificació amb altres persones.
- No facilitar el codi QR de configuració a tercers.
- Mantenir el telèfon mòbil protegit amb PIN, contrasenya o biometria.
- Guardar els codis de seguretat en un lloc segur i separat del mòbil.
- No aprovar notificacions d'inici de sessió que no hàgim sol·licitat.
- Avisar el responsable informàtic si perdem el mòbil o sospitem que algú ha accedit al nostre compte.

També és recomanable mantenir actualitzats tant el sistema operatiu del mòbil com l'aplicació d'autenticació.

## 11. Conclusions

L'autenticació multifactor és una mesura molt important per millorar la seguretat dels comptes corporatius.

Gràcies a Google Authenticator, podem afegir un segon factor de verificació de manera senzilla, ràpida i gratuïta.

Aquest sistema redueix el risc d'accessos no autoritzats, ja que no és suficient conèixer la contrasenya: també cal disposar del dispositiu mòbil vinculat o d'un altre mètode de verificació.

Per tant, es recomana que tots els usuaris de l'organització activin l'autenticació multifactor per protegir la informació corporativa.

---

**Fi de la guia – NF1AA3**
