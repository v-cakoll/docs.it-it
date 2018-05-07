---
title: Linee guida per la generazione di codice sicuro
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- managed wrapper to native code implementation
- secure coding
- reusable components
- library code that exposes protected resources
- code, security
- code security
- secure coding, options
- components [.NET Framework], security
- code security, options
- security-neutral code
- security [.NET Framework], coding guidelines
ms.assetid: 4f882d94-262b-4494-b0a6-ba9ba1f5f177
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f8d61e76a657c7341ec7dfcede6d7dc9943d4659
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="secure-coding-guidelines"></a>Linee guida per la generazione di codice sicuro
La sicurezza basata sull'evidenza e la sicurezza per l'accesso al codice forniscono meccanismi espliciti molto efficaci per implementare la sicurezza. Nella maggior parte dei casi, per proteggere il codice delle applicazioni è sufficiente l'infrastruttura implementata da .NET Framework. In alcuni casi è tuttavia necessaria una sicurezza aggiuntiva specifica per l'applicazione, creata mediante l'estensione del sistema di sicurezza o tramite metodi ad hoc.  
  
 L'uso delle autorizzazioni applicate da .NET Framework e di altri tipi di sicurezza imposta nel codice consente di creare barriere che impediscono l'ottenimento di informazioni da parte di malware o l'esecuzione di altre operazioni non desiderate. È inoltre necessario raggiungere un compromesso tra sicurezza e usabilità del codice in tutti gli scenari d'uso di codice attendibile.  
  
 In questa panoramica vengono descritti i diversi metodi di progettazione del codice per l'uso del sistema di sicurezza.  
  
## <a name="securing-resource-access"></a>Protezione dell'accesso alle risorse  
 Durante la progettazione e la scrittura del codice, è necessario proteggere e limitare l'accesso del codice alle risorse, soprattutto quando si usa o chiama codice di origine sconosciuta. Le tecniche seguenti consentono di verificare che il codice sia sicuro:  
  
-   Non usare Sicurezza per l'accesso al codice (CAS, Code Access Security).  
  
-   Non usare codice parzialmente attendibile.  
  
-   Non usare Servizi remoti .NET.  
  
-   Non usare DCOM (Distributed Component Object Model).  
  
-   Non utilizzare formattori binari.  
  
 La sicurezza dall'accesso di codice e il codice SecurityTransparent non saranno supportati come limiti di sicurezza con codice parzialmente attendibile. Non è consigliabile caricare ed eseguire codice di origine sconosciuta in assenza di misure di sicurezza alternative. Le misure di protezione alternative sono:  
  
-   Virtualizzazione  
  
-   AppContainers  
  
-   Utenti e autorizzazioni del sistema operativo (SO)  
  
-   Contenitori Hyper-V  
  
## <a name="security-neutral-code"></a>Codice indipendente dalla sicurezza  
 Il codice indipendente dalla sicurezza non ha elementi espliciti in comune con il sistema di sicurezza e viene eseguito a prescindere dalle autorizzazioni ricevute Anche se le applicazioni che non riescono a intercettare eccezioni associate alle operazioni protette, come l'uso di file o le operazioni in rete, possono avere come effetto eccezioni non gestite, il codice indipendente dalla sicurezza è comunque in grado di sfruttare le tecnologie di sicurezza di .NET Framework.  
  
 Una libreria indipendente dalla sicurezza dispone di caratteristiche speciali che è necessario comprendere. Si supponga che nella libreria siano forniti elementi API che consentano di usare file o chiamare codice non gestito. Se al codice non è associata l'autorizzazione corrispondente, questo non verrà eseguito nel modo descritto. Tuttavia, anche al codice viene concessa l'autorizzazione, il codice delle applicazioni da cui tale codice viene chiamato deve disporre della stessa autorizzazione per funzionare. Se il codice chiamante non dispone dell'autorizzazione appropriata, un <xref:System.Security.SecurityException> viene visualizzato in seguito il percorso stack di protezione accesso di codice.  
  
## <a name="application-code-that-is-not-a-reusable-component"></a>Codice di applicazioni non riutilizzabile  
 Se il codice fa parte di un'applicazione che non verrà richiamata da altro codice, la sicurezza è semplice e potrebbe non essere necessario scrivere codice speciale. Tenere comunque presente che il codice può essere chiamato da codice dannoso. Anche se la sicurezza per l'accesso al codice può impedire a codice dannoso di accedere alle risorse, con questo codice è comunque possibile leggere i valori contenuti nei campi o nelle proprietà che possono rappresentare informazioni sensibili.  
  
 Se inoltre il codice accetta input da Internet o da altre fonti inaffidabili, è opportuno evitare input dannosi.  
  
## <a name="managed-wrapper-to-native-code-implementation"></a>Wrapper gestiti nell'implementazione di codice nativo  
 In genere, in uno scenario di questo tipo, viene implementata una funzionalità utile nel codice nativo da rendere disponibile per il codice gestito. I wrapper gestiti possono essere scritti in modo semplice usando platform invoke o l'interoperabilità COM. Per la riuscita di questa operazione è tuttavia necessario che i chiamanti dei wrapper dispongano di diritti per il codice non gestito. In base ai criteri predefiniti, il codice scaricato da una rete Intranet o da Internet non funzionerà con i wrapper.  
  
 Invece di assegnare a tutte le applicazioni che impiegano i wrapper diritti di codice non gestito, è preferibile fornire questi diritti solo al codice wrapper. Se la funzionalità sottostante non espone alcuna risorsa e l'implementazione è probabilmente sicura, per il wrapper è sufficiente l'asserzione dei diritti, che consente la chiamata tramite codice. Quando sono coinvolte le risorse, il codice della sicurezza deve essere analogo a quello di libreria descritto nella sezione successiva. Poiché il wrapper può esporre i chiamanti a queste risorse, la verifica attenta della sicurezza del codice nativo è necessaria e costituisce uno dei compiti del wrapper.  
  
## <a name="library-code-that-exposes-protected-resources"></a>Codice di libreria che espone risorse protette  
 Si tratta dell'approccio più efficace e potenzialmente pericoloso, se eseguito in modo non corretto, della codifica della sicurezza: la libreria funge da interfaccia per l'accesso tramite codice ad alcune risorse non altrimenti disponibili, così come le classi di .NET Framework impongono le autorizzazioni relative alle risorse che usano. Se si espone una risorsa, è necessario per prima cosa esigere tramite codice l'autorizzazione adeguata alla risorsa (in altre parole, eseguire un controllo di sicurezza) e quindi eseguire un'asserzione dei relativi diritti per eseguire l'operazione vera e propria.  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|-----------|-----------------|  
|[Protezione dei dati di stato](../../../docs/standard/security/securing-state-data.md)|Viene descritto come proteggere membri privati.|  
|[Sicurezza e input dell'utente](../../../docs/standard/security/security-and-user-input.md)|Vengono descritti argomenti relativi alla sicurezza delle applicazioni che accettano input dell'utente.|  
|[Sicurezza e race condition](../../../docs/standard/security/security-and-race-conditions.md)|Viene descritto come evitare race condition nel codice.|  
|[Sicurezza e generazione di codice immediata](../../../docs/standard/security/security-and-on-the-fly-code-generation.md)|Vengono descritti aspetti della sicurezza relativi alle applicazioni che consentono di generare codice dinamico.|  
|[Sicurezza basata sui ruoli](../../../docs/standard/security/role-based-security.md)|Viene descritta in modo dettagliato la sicurezza basata sui ruoli di .NET Framework e viene illustrato come usarla nel codice.|
