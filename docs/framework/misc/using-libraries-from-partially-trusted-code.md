---
title: Utilizzo di librerie da codice parzialmente attendibile
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security [.NET Framework], partially trusted code
- partially trusted code
- partial trust
- AllowPartiallyTrustedCallersAttribute attribute
- code access security, partially trusted code
- APTCA
ms.assetid: dd66cd4c-b087-415f-9c3e-94e3a1835f74
caps.latest.revision: "25"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7a452370df7c18f3e3f0190a14979099152485f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="using-libraries-from-partially-trusted-code"></a>Utilizzo di librerie da codice parzialmente attendibile
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
> [!NOTE]
>  In questo argomento viene descritto il comportamento degli assembly con nome sicuro e si applica solo a [livello 1](../../../docs/framework/misc/security-transparent-code-level-1.md) assembly. [Il codice SecurityTransparent, livello 2](../../../docs/framework/misc/security-transparent-code-level-2.md) assembly il [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] o versioni successive non sono interessati dai nomi sicuri. Per ulteriori informazioni sulle modifiche al sistema di sicurezza, vedere [modifiche della sicurezza](../../../docs/framework/security/security-changes.md).  
  
 Le applicazioni che ritenute del tutto attendibili dall'host o sandbox non è consentito chiamare condiviso librerie gestite, a meno che il writer delle librerie consenta in modo specifico mediante l'utilizzo del <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attributo. Di conseguenza, i writer delle applicazioni devono tenere presente che alcune librerie non saranno disponibili da un contesto parzialmente attendibile. Per impostazione predefinita, tutto il codice che viene eseguito in un contesto di attendibilità parziale [sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md) e non in elenco di assembly totalmente attendibili è parzialmente attendibile. Se non si prevede che il codice venga eseguito da un contesto parzialmente attendibile o venga chiamato da un codice parzialmente attendibile, non sono rilevanti le informazioni contenute in questa sezione. Se tuttavia si scrive codice che deve interagire con codice parzialmente attendibile o agire da un contesto parzialmente attendibile, si devono prendere in considerazione i seguenti fattori:  
  
-   Le librerie devono essere firmate con un nome sicuro per essere condivise da più applicazioni. I nomi sicuri consentono al codice di essere inserito in Global Assembly Cache o aggiunto all'elenco totalmente attendibile di un <xref:System.AppDomain> di sandboxing e consente agli utenti di verificare da quale altro utente ha origine una particolare parte di codice mobile.  
  
-   Per impostazione predefinita, con nome sicuro [livello 1](../../../docs/framework/misc/security-transparent-code-level-1.md) librerie condivise eseguono implicita [LinkDemand](../../../docs/framework/misc/link-demands.md) per l'attendibilità totale automaticamente, senza il writer delle librerie debba eseguire alcuna operazione.  
  
-   Se un chiamante non dispone dell'attendibilità totale ma continua a chiamare quel tipo di libreria, il runtime genera un'eccezione <xref:System.Security.SecurityException> e al chiamante non è consentito collegarsi alla libreria.  
  
-   Per disabilitare l'automatico **LinkDemand** e impedire che venga generata un'eccezione, è possibile inserire il **AllowPartiallyTrustedCallersAttribute** attributo nell'ambito degli assembly di una scheda SCSI libreria. Questo attributo consente alle librerie di essere chiamate da un codice gestito parzialmente attendibile.  
  
-   Il codice parzialmente attendibile a cui è concesso l'accesso a una libreria con questo attributo continua a essere oggetto di altre restrizioni definite da <xref:System.AppDomain>.  
  
-   Non è a livello di codice per codice parzialmente attendibile di chiamare una libreria che non dispone di **AllowPartiallyTrustedCallersAttribute** attributo.  
  
 Le librerie che sono private per un'applicazione specifica non richiedono un nome sicuro o **AllowPartiallyTrustedCallersAttribute** attributo e non può fare riferimento codice potenzialmente dannoso di fuori dell'applicazione. Questo tipo di codice è protetto da un uso improprio intenzionale o non intenzionale mediante codice mobile parzialmente attendibile senza altre operazioni da parte dello sviluppatore.  
  
 È consigliabile abilitare in modo esplicito l'utilizzo di codice parzialmente attendibile per i tipi di codice seguenti:  
  
-   Codice che sia stato attentamente testato vulnerabilità della sicurezza e sia conforme con le istruzioni riportate in [indicazioni per la generazione di codice protetto](../../../docs/standard/security/secure-coding-guidelines.md).  
  
-   Librerie del codice con nome sicuro che sono scritte in modo specifico per scenari parzialmente attendibili.  
  
-   Tutti i componenti (parzialmente o totalmente attendibili) firmati con un nome sicuro che saranno chiamati dal codice scaricato da Internet.  
  
> [!NOTE]
>  Alcune classi nella libreria di classi .NET Framework non dispone di **AllowPartiallyTrustedCallersAttribute** attributo e non può essere chiamato da codice parzialmente attendibile.  
  
## <a name="see-also"></a>Vedere anche  
 [Sicurezza dall'accesso di codice](../../../docs/framework/misc/code-access-security.md)
