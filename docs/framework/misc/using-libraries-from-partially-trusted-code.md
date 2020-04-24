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
ms.openlocfilehash: 61291a07639c3f92a05f78dff49f6b20f1aee77e
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645723"
---
# <a name="using-libraries-from-partially-trusted-code"></a>Utilizzo di librerie da codice parzialmente attendibile
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
> [!NOTE]
> In questo argomento viene affrontato il comportamento degli assembly con nome sicuro e si applica solo agli assembly di [livello 1.](security-transparent-code-level-1.md) [Security-Transparent Code, assembly di livello 2](security-transparent-code-level-2.md) in.NET Framework 4 o versioni successive non sono interessati da nomi sicuri. Per ulteriori informazioni sulle modifiche apportate al sistema di protezione, vedere [Modifiche alla sicurezza](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).  
  
 Le applicazioni che non sono ritenute del tutto attendibili dall'host o sandbox non possono chiamare librerie gestite condivise a meno che il writer delle librerie non lo consenta in modo specifico mediante l'uso dell'attributo <xref:System.Security.AllowPartiallyTrustedCallersAttribute>. Di conseguenza, i writer delle applicazioni devono tenere presente che alcune librerie non saranno disponibili da un contesto parzialmente attendibile. Per impostazione predefinita, tutto il codice eseguito in una [sandbox](how-to-run-partially-trusted-code-in-a-sandbox.md) con attendibilità parziale e non presente nell'elenco degli assembly con attendibilità totale è parzialmente attendibile. Se non si prevede che il codice venga eseguito da un contesto parzialmente attendibile o venga chiamato da un codice parzialmente attendibile, non sono rilevanti le informazioni contenute in questa sezione. Se tuttavia si scrive codice che deve interagire con codice parzialmente attendibile o agire da un contesto parzialmente attendibile, si devono prendere in considerazione i seguenti fattori:  
  
- Le librerie devono essere firmate con un nome sicuro per essere condivise da più applicazioni. I nomi sicuri consentono al codice di essere inserito in Global Assembly Cache o aggiunto all'elenco totalmente attendibile di un <xref:System.AppDomain> di sandboxing e consente agli utenti di verificare da quale altro utente ha origine una particolare parte di codice mobile.  
  
- Per impostazione predefinita, le librerie condivise di [livello 1](security-transparent-code-level-1.md) con nome sicuro eseguono automaticamente un LinkDemand implicito per [l'attendibilità](link-demands.md) totale, senza che il writer della libreria debba eseguire alcuna operazione.  
  
- Se un chiamante non dispone dell'attendibilità totale ma continua a chiamare quel tipo di libreria, il runtime genera un'eccezione <xref:System.Security.SecurityException> e al chiamante non è consentito collegarsi alla libreria.  
  
- Per disabilitare **il LinkDemand** automatico e impedire la generazione dell'eccezione, è possibile inserire l'attributo **AllowPartiallyTrustedCallersAttribute** nell'ambito dell'assembly di una libreria condivisa. Questo attributo consente alle librerie di essere chiamate da un codice gestito parzialmente attendibile.  
  
- Il codice parzialmente attendibile a cui è concesso l'accesso a una libreria con questo attributo continua a essere oggetto di altre restrizioni definite da <xref:System.AppDomain>.  
  
- Non esiste un modo a livello di codice per il codice parzialmente attendibile per chiamare una libreria che non dispone dell'attributo **AllowPartiallyTrustedCallersAttribute.**  
  
 Le librerie private per un'applicazione specifica non richiedono un nome sicuro o l'attributo **AllowPartiallyTrustedCallersAttribute** e non è possibile farvi riferimento da codice potenzialmente dannoso all'esterno dell'applicazione. Questo tipo di codice è protetto da un uso improprio intenzionale o non intenzionale mediante codice mobile parzialmente attendibile senza altre operazioni da parte dello sviluppatore.  
  
 È consigliabile abilitare in modo esplicito l'utilizzo di codice parzialmente attendibile per i tipi di codice seguenti:  
  
- Codice che è stato diligentemente testato per le vulnerabilità della sicurezza ed è conforme alle linee guida descritte in Linee guida per la [codifica sicura](../../standard/security/secure-coding-guidelines.md).  
  
- Librerie del codice con nome sicuro che sono scritte in modo specifico per scenari parzialmente attendibili.  
  
- Tutti i componenti (parzialmente o totalmente attendibili) firmati con un nome sicuro che saranno chiamati dal codice scaricato da Internet.  
  
> [!NOTE]
> Alcune classi nella libreria di classi .NET Framework non dispongono dell'attributo **AllowPartiallyTrustedCallersAttribute** e non possono essere chiamate da codice parzialmente attendibile.  
  
## <a name="see-also"></a>Vedere anche

- [Sicurezza dall'accesso di codiceCode Access Security](code-access-security.md)
