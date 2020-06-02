---
title: Oggetti Principal e Identity
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- WindowsIdentity objects
- GenericIdentity objects
- GenericPrincipal objects
- identity objects, about identity objects
- security [.NET Framework], identity objects
- principal objects, about principal objects
- security [.NET Framework], principals
- WindowsPrincipal objects
ms.assetid: aa5930ad-f3d7-40aa-b6f6-c6edcd5c64f7
ms.openlocfilehash: cece51370fb269121e776e865275cd464c1af095
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291227"
---
# <a name="principal-and-identity-objects"></a>Oggetti Principal e Identity
Il codice gestito può individuare l'identità o il ruolo di un'entità tramite un <xref:System.Security.Principal.IPrincipal> oggetto che contiene un riferimento a un <xref:System.Security.Principal.IIdentity> oggetto. Può essere utile paragonare oggetti Identity e Principal a concetti familiari quali account utente e di gruppo. Nella maggior parte degli ambienti di rete, gli account utente rappresentano utenti o programmi, mentre gli account di gruppo rappresentano determinate categorie di utenti e i diritti che essi detengono. Analogamente, gli oggetti Identity di .NET Framework rappresentano utenti, mentre i ruoli rappresentano appartenenze e contesti di sicurezza. In .NET Framework l'oggetto Principal incapsula sia un oggetto Identity che un ruolo. Le applicazioni di .NET Framework concedono diritti al principale sulla base dell'identità che esso presenta oppure, più comunemente, al ruolo che esso riveste.  
  
## <a name="identity-objects"></a>Oggetti Identity  
 L'oggetto Identity incapsula informazioni sull'utente o sull'entità da convalidare. Nella forma più semplice, gli oggetti Identity contengono un nome e un tipo di autenticazione. Il nome può essere quello di un utente o di un account Windows, mentre il tipo di autenticazione può corrispondere a un protocollo di accesso supportato, quale Kerberos V5, oppure a un valore personalizzato. Il .NET Framework definisce un <xref:System.Security.Principal.GenericIdentity> oggetto che può essere utilizzato per la maggior parte degli scenari di accesso personalizzati e un oggetto più specializzato <xref:System.Security.Principal.WindowsIdentity> che può essere utilizzato quando si desidera che l'applicazione si basi sull'autenticazione di Windows. È inoltre possibile definire una classe di identità personalizzata che contenga informazioni utente personalizzate.  
  
 L' <xref:System.Security.Principal.IIdentity> interfaccia definisce le proprietà per l'accesso a un nome e un tipo di autenticazione, ad esempio Kerberos V5 o NTLM. Tutte le classi **Identity** implementano l'interfaccia **IIdentity**. Non è necessaria alcuna relazione tra un oggetto **Identity** e il token di processo di Windows NT sotto cui un thread è in esecuzione. Se tuttavia l'oggetto **Identity** è un oggetto **WindowsIdentity**, si presupporrà che l'identità rappresenti un token di sicurezza di Windows NT.  
  
## <a name="principal-objects"></a>Oggetti Principal  
 L'oggetto Principal rappresenta il contesto di sicurezza in cui viene eseguito il codice. Le applicazioni che implementano la sicurezza basata sui ruoli concedono diritti sulla base del ruolo associato all'oggetto Principal. Analogamente agli oggetti Identity, il .NET Framework fornisce un <xref:System.Security.Principal.GenericPrincipal> oggetto e un <xref:System.Security.Principal.WindowsPrincipal> oggetto. È inoltre possibile definire classi di principali personalizzate.  
  
 L' <xref:System.Security.Principal.IPrincipal> interfaccia definisce una proprietà per l'accesso a un oggetto **Identity** associato, nonché un metodo per determinare se l'utente identificato dall'oggetto **Principal** è un membro di un determinato ruolo. Tutte le classi **Principal** implementano l'interfaccia **IPrincipal** nonché ulteriori proprietà e metodi eventualmente necessari. Common Language Runtime fornisce ad esempio la classe **WindowsPrincipal**, che implementa funzionalità aggiuntive per il mapping tra l'appartenenza a un gruppo di Windows NT o Windows 2000 e i ruoli.  
  
 Un oggetto **Principal** è associato a un oggetto Context ( <xref:System.Runtime.Remoting.Messaging.CallContext> ) di chiamata all'interno di un dominio applicazione ( <xref:System.AppDomain> ). Viene sempre creato un contesto di chiamata predefinito con ciascun nuovo **AppDomain**, così esiste sempre un contesto di chiamata disponibile per accettare l'oggetto **Principal**. Quando viene creato un nuovo thread, per tale thread viene creato anche un oggetto **CallContext**. Il riferimento all'oggetto **Principal** viene automaticamente copiato dal thread di origine al **CallContext** del nuovo thread. Se il runtime non è in grado di determinare quale oggetto **Principal** appartiene al creatore del thread, si atterrà ai criteri predefiniti per la creazione di oggetti **Principal** e **Identity**.  
  
 Dei criteri configurabili specifici di un dominio applicazione definiscono le regole in base alle quali decidere quale tipo di oggetto **Principal** associare a un nuovo dominio applicazione. Dove consentito dai criteri di sicurezza, il runtime può creare oggetti **Principal** e **Identity** che riflettono il token del sistema operativo associato al thread di esecuzione corrente. In base all'impostazione predefinita, il runtime utilizza oggetti **Principal** e **Identity** che rappresentano utenti non autenticati. Il runtime non crea questi oggetti **Principal** e **Identity** predefiniti finché il codice non tenta di accedervi.  
  
 Il codice attendibile che crea un dominio applicazione può impostare i criteri di sicurezza del dominio applicazione che controllano la costruzione degli oggetti **Principal** e **Identity** predefiniti. Questi criteri specifici del dominio applicazione si applicano a tutti i thread di esecuzione di tale dominio applicazione. Un host attendibile non gestito ha intrinsecamente la possibilità di impostare questo criterio, ma il codice gestito che imposta questo criterio deve disporre <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> di per il controllo dei criteri di dominio.  
  
 Quando si trasmette un oggetto **Principal** tra più domini applicazione, ma all'interno dello stesso processo e quindi sullo stesso computer, l'infrastruttura remota consente di copiare nel contesto del chiamato un riferimento all'oggetto **Principal** associato al contesto del chiamante.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: creare un oggetto WindowsPrincipal](how-to-create-a-windowsprincipal-object.md)
- [Procedura: Creare oggetti GenericPrincipal e GenericIdentity](how-to-create-genericprincipal-and-genericidentity-objects.md)
- [Sostituzione di oggetti Principal](replacing-a-principal-object.md)
- [Rappresentazione e ripristino](impersonating-and-reverting.md)
- [Sicurezza basata sui ruoli](role-based-security.md)
- [Concetti principali sulla sicurezza](key-security-concepts.md)
