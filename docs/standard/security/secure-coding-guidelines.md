---
title: Linee guida codice sicuro per .NET
ms.date: 06/28/2018
helpviewer_keywords:
- managed wrapper to native code implementation
- secure coding
- reusable components
- library code that exposes protected resources
- code, security
- code security
- secure coding, options
- components [.NET], security
- code security, options
- security-neutral code
- security [.NET], coding guidelines
ms.assetid: 4f882d94-262b-4494-b0a6-ba9ba1f5f177
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b3a8f0dfc1a2b5e09722876b73281ed1d8b6334e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62018645"
---
# <a name="secure-coding-guidelines"></a>Linee guida per la scrittura di codice sicuro

La sicurezza basata sull'evidenza e la sicurezza per l'accesso al codice forniscono meccanismi espliciti molto efficaci per implementare la sicurezza. Gran parte del codice dell'applicazione possono semplicemente usare l'infrastruttura implementata da .NET. In alcuni casi è tuttavia necessaria una sicurezza aggiuntiva specifica per l'applicazione, creata mediante l'estensione del sistema di sicurezza o tramite metodi ad hoc.

Con .NET applicate le autorizzazioni e altri tipi nel codice, si erigere barriere per impedire che il codice dannoso l'accesso alle informazioni che non si desidera che siano o eseguire altre azioni indesiderati. È inoltre necessario raggiungere un compromesso tra sicurezza e usabilità del codice in tutti gli scenari d'uso di codice attendibile.

In questa panoramica vengono descritti i diversi metodi di progettazione del codice per l'uso del sistema di sicurezza.

## <a name="securing-resource-access"></a>Protezione dell'accesso alle risorse

Durante la progettazione e la scrittura del codice, è necessario proteggere e limitare l'accesso del codice alle risorse, soprattutto quando si usa o chiama codice di origine sconosciuta. Le tecniche seguenti consentono di verificare che il codice sia sicuro:

- Non usare Sicurezza per l'accesso al codice (CAS, Code Access Security).

- Non usare codice parzialmente attendibile.

- Non usare la [AllowPartiallyTrustedCaller](xref:System.Security.AllowPartiallyTrustedCallersAttribute) attributo (APTCA).

- Non usare Servizi remoti .NET.

- Non usare DCOM (Distributed Component Object Model).

- Non utilizzare formattori binari.

Sicurezza dall'accesso di codice e il codice SecurityTransparent non sono supportati come limiti di sicurezza con codice parzialmente attendibile. Non è consigliabile caricare ed eseguire codice di origine sconosciuta in assenza di misure di sicurezza alternative. Le misure di protezione alternative sono:

- Virtualizzazione

- AppContainers

- Utenti e autorizzazioni del sistema operativo (SO)

- Contenitori Hyper-V

## <a name="security-neutral-code"></a>Codice indipendente dalla sicurezza

Il codice indipendente dalla sicurezza non ha elementi espliciti in comune con il sistema di sicurezza e viene eseguito a prescindere dalle autorizzazioni ricevute Anche se le applicazioni che non riescono a intercettare eccezioni associate alle operazioni protette (ad esempio usando i file, rete e così via) possono provocare un'eccezione non gestita, il codice indipendente dalla sicurezza ancora sfrutta i vantaggi delle tecnologie di sicurezza in .NET .

Una libreria indipendente dalla sicurezza dispone di caratteristiche speciali che è necessario comprendere. Si supponga che nella libreria siano forniti elementi API che usano i file o chiamare codice non gestito. Se il codice non dispone dell'autorizzazione corrispondente, non verrà eseguito come descritto. Tuttavia, anche al codice viene concessa l'autorizzazione, il codice delle applicazioni da cui tale codice viene chiamato deve disporre della stessa autorizzazione per funzionare. Se il codice chiamante non dispone dell'autorizzazione appropriata, un <xref:System.Security.SecurityException> viene visualizzato a seguito di stack il codice di sicurezza l'accesso.

## <a name="application-code-that-isnt-a-reusable-component"></a>Codice dell'applicazione che non è un componente riutilizzabile

Se il codice è parte di un'applicazione che non verrà chiamata da un altro codice, la protezione è semplice e potrebbe non essere necessario scrivere codice speciale. Tenere comunque presente che il codice può essere chiamato da codice dannoso. Anche se la sicurezza per l'accesso al codice può impedire a codice dannoso di accedere alle risorse, con questo codice è comunque possibile leggere i valori contenuti nei campi o nelle proprietà che possono rappresentare informazioni sensibili.

Se inoltre il codice accetta input da Internet o da altre fonti inaffidabili, è opportuno evitare input dannosi.

## <a name="managed-wrapper-to-native-code-implementation"></a>Wrapper gestiti nell'implementazione di codice nativo

In genere, in uno scenario di questo tipo, viene implementata una funzionalità utile nel codice nativo da rendere disponibile per il codice gestito. I wrapper gestiti possono essere scritti in modo semplice usando platform invoke o l'interoperabilità COM. Per la riuscita di questa operazione è tuttavia necessario che i chiamanti dei wrapper dispongano di diritti per il codice non gestito. In base ai criteri predefiniti, ciò significa che il codice scaricato da una rete intranet o Internet non funzionerà con i wrapper.

Invece di concedere diritti di codice non gestito per tutte le applicazioni che usano questi wrapper, è preferibile fornire questi diritti solo al codice wrapper. Se la funzionalità sottostante non espone alcuna risorsa e l'implementazione è probabilmente sicura, per il wrapper è sufficiente l'asserzione dei diritti, che consente la chiamata tramite codice. Quando sono coinvolte le risorse, il codice della sicurezza deve essere analogo a quello di libreria descritto nella sezione successiva. Poiché il wrapper può esporre i chiamanti a queste risorse, la verifica attenta della sicurezza del codice nativo è necessaria e costituisce uno dei compiti del wrapper.

## <a name="library-code-that-exposes-protected-resources"></a>Codice di libreria che espone risorse protette

L'approccio seguente è più efficace e potenzialmente pericoloso (se eseguita in modo non corretto) per la codifica della sicurezza: la libreria funge da interfaccia per altro codice accedere ad alcune risorse non disponibili, in caso contrario, così come le classi .NET impongono autorizzazioni per le risorse da usare. Se si espone una risorsa, è necessario per prima cosa esigere tramite codice l'autorizzazione adeguata alla risorsa (in altre parole, eseguire un controllo di sicurezza) e quindi eseguire un'asserzione dei relativi diritti per eseguire l'operazione vera e propria.

## <a name="related-topics"></a>Argomenti correlati

|Titolo|Descrizione|
|-----------|-----------------|
|[Protezione dei dati di stato](securing-state-data.md)|Viene descritto come proteggere membri privati.|
|[Sicurezza e input dell'utente](security-and-user-input.md)|Vengono descritti argomenti relativi alla sicurezza delle applicazioni che accettano input dell'utente.|
|[Sicurezza e race condition](security-and-race-conditions.md)|Viene descritto come evitare race condition nel codice.|
|[Sicurezza e generazione di codice immediata](security-and-on-the-fly-code-generation.md)|Vengono descritti aspetti della sicurezza relativi alle applicazioni che consentono di generare codice dinamico.|
|[Sicurezza basata sui ruoli](role-based-security.md)|Viene descritta la sicurezza basata sui ruoli di .NET in modo dettagliato e vengono fornite istruzioni per l'uso nel codice.|
