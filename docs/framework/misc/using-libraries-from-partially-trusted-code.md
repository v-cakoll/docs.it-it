---
title: Utilizzo di librerie da codice parzialmente attendibile
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], partially trusted code
- partially trusted code
- partial trust
- AllowPartiallyTrustedCallersAttribute attribute
- code access security, partially trusted code
- APTCA
ms.assetid: dd66cd4c-b087-415f-9c3e-94e3a1835f74
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7a3bbbaa565a6c118082456a1ab6d7af59db7067
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982475"
---
# <a name="using-libraries-from-partially-trusted-code"></a>Utilizzo di librerie da codice parzialmente attendibile
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
> [!NOTE]
>  In questo argomento viene descritto il comportamento degli assembly con nome sicuro e si applica solo a [livello 1](../../../docs/framework/misc/security-transparent-code-level-1.md) assembly. [Codice SecurityTransparent, livello 2](../../../docs/framework/misc/security-transparent-code-level-2.md) gli assembly nel [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] o versioni successive non sono interessati dai nomi sicuri. Per altre informazioni sulle modifiche apportate al sistema di sicurezza, vedere [modifiche della sicurezza](../../../docs/framework/security/security-changes.md).  
  
 Le applicazioni che non sono ritenute del tutto attendibili dall'host o sandbox non possono chiamare librerie gestite condivise a meno che il writer delle librerie non lo consenta in modo specifico mediante l'uso dell'attributo <xref:System.Security.AllowPartiallyTrustedCallersAttribute>. Di conseguenza, i writer delle applicazioni devono tenere presente che alcune librerie non saranno disponibili da un contesto parzialmente attendibile. Per impostazione predefinita, tutto il codice eseguito in una relazione di trust parziale [sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md) e non è in elenco di assembly totalmente attendibili è parzialmente attendibile. Se non si prevede che il codice venga eseguito da un contesto parzialmente attendibile o venga chiamato da un codice parzialmente attendibile, non sono rilevanti le informazioni contenute in questa sezione. Se tuttavia si scrive codice che deve interagire con codice parzialmente attendibile o agire da un contesto parzialmente attendibile, si devono prendere in considerazione i seguenti fattori:  
  
- Le librerie devono essere firmate con un nome sicuro per essere condivise da più applicazioni. I nomi sicuri consentono al codice di essere inserito in Global Assembly Cache o aggiunto all'elenco totalmente attendibile di un <xref:System.AppDomain> di sandboxing e consente agli utenti di verificare da quale altro utente ha origine una particolare parte di codice mobile.  
  
- Per impostazione predefinita, nome sicuro [livello 1](../../../docs/framework/misc/security-transparent-code-level-1.md) librerie condivise eseguono implicita [LinkDemand](../../../docs/framework/misc/link-demands.md) per l'attendibilità totale automaticamente, senza il writer delle librerie debba eseguire alcuna operazione.  
  
- Se un chiamante non dispone dell'attendibilità totale ma continua a chiamare quel tipo di libreria, il runtime genera un'eccezione <xref:System.Security.SecurityException> e al chiamante non è consentito collegarsi alla libreria.  
  
- Per disabilitare il **LinkDemand** e impedire che venga generata l'eccezione, è possibile inserire le **AllowPartiallyTrustedCallersAttribute** attributo nell'ambito degli assembly di una scheda SCSI libreria. Questo attributo consente alle librerie di essere chiamate da un codice gestito parzialmente attendibile.  
  
- Il codice parzialmente attendibile a cui è concesso l'accesso a una libreria con questo attributo continua a essere oggetto di altre restrizioni definite da <xref:System.AppDomain>.  
  
- Non vi è alcuna modalità programmatica per codice parzialmente attendibile di chiamare una libreria che non ha il **AllowPartiallyTrustedCallersAttribute** attributo.  
  
 Le librerie che appartengono a un'applicazione specifica non richiedono un nome sicuro o la **AllowPartiallyTrustedCallersAttribute** attributo e non è possibile farvi riferimento da codice potenzialmente dannoso di fuori dell'applicazione. Questo tipo di codice è protetto da un uso improprio intenzionale o non intenzionale mediante codice mobile parzialmente attendibile senza altre operazioni da parte dello sviluppatore.  
  
 È consigliabile abilitare in modo esplicito l'utilizzo di codice parzialmente attendibile per i tipi di codice seguenti:  
  
- Codice che ha stato attentamente sottoposto a test per le vulnerabilità di sicurezza ed è conforme con le linee guida descritte nel [indicazioni per la codifica protetto](../../../docs/standard/security/secure-coding-guidelines.md).  
  
- Librerie del codice con nome sicuro che sono scritte in modo specifico per scenari parzialmente attendibili.  
  
- Tutti i componenti (parzialmente o totalmente attendibili) firmati con un nome sicuro che saranno chiamati dal codice scaricato da Internet.  
  
> [!NOTE]
>  Alcune classi nella libreria di classi .NET Framework non è il **AllowPartiallyTrustedCallersAttribute** attributo e non può essere chiamato da codice parzialmente attendibile.  
  
## <a name="see-also"></a>Vedere anche

- [Sicurezza dall'accesso di codice](../../../docs/framework/misc/code-access-security.md)
