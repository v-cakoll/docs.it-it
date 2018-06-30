---
title: Proteggere indicazioni per .NET
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
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106736"
---
# <a name="secure-coding-guidelines"></a>Indicazioni per la codifica sicura

La sicurezza basata sull'evidenza e la sicurezza per l'accesso al codice forniscono meccanismi espliciti molto efficaci per implementare la sicurezza. Gran parte del codice dell'applicazione è possibile utilizzare semplicemente l'infrastruttura implementata da .NET. In alcuni casi è tuttavia necessaria una sicurezza aggiuntiva specifica per l'applicazione, creata mediante l'estensione del sistema di sicurezza o tramite metodi ad hoc.

Usando .NET imposti le autorizzazioni e altri tipi di sicurezza nel codice, si consentono barriere che impediscono l'accesso alle informazioni che non si desidera che siano o eseguire altre operazioni di codice dannoso. È inoltre necessario raggiungere un compromesso tra sicurezza e usabilità del codice in tutti gli scenari d'uso di codice attendibile.

In questa panoramica vengono descritti i diversi metodi di progettazione del codice per l'uso del sistema di sicurezza.

## <a name="securing-resource-access"></a>Proteggere l'accesso alle risorse

Durante la progettazione e la scrittura del codice, è necessario proteggere e limitare l'accesso del codice alle risorse, soprattutto quando si usa o chiama codice di origine sconosciuta. Le tecniche seguenti consentono di verificare che il codice sia sicuro:

- Non usare Sicurezza per l'accesso al codice (CAS, Code Access Security).

- Non usare codice parzialmente attendibile.

- Non usare la [AllowPartiallyTrustedCaller](xref:System.Security.AllowPartiallyTrustedCallersAttribute) attributo (APTCA).

- Non usare Servizi remoti .NET.

- Non usare DCOM (Distributed Component Object Model).

- Non utilizzare formattori binari.

Sicurezza dall'accesso di codice e codice SecurityTransparent non sono supportati come limite di sicurezza con codice parzialmente attendibile. Non è consigliabile caricare ed eseguire codice di origine sconosciuta in assenza di misure di sicurezza alternative. Le misure di protezione alternative sono:

- Virtualizzazione

- AppContainers

- Utenti e autorizzazioni del sistema operativo (SO)

- Contenitori Hyper-V

## <a name="security-neutral-code"></a>Codice indipendente dalla sicurezza

Il codice indipendente dalla sicurezza non ha elementi espliciti in comune con il sistema di sicurezza e viene eseguito a prescindere dalle autorizzazioni ricevute Sebbene le applicazioni che non riescono a intercettare eccezioni associate alle operazioni protette (ad esempio usando i file, rete e così via) possono generare un'eccezione non gestita, il codice indipendente dalla sicurezza ancora sfrutta le tecnologie di sicurezza in .NET .

Una libreria indipendente dalla sicurezza dispone di caratteristiche speciali che è necessario comprendere. Si supponga che nella libreria siano forniti elementi API che utilizzano i file o chiamare codice non gestito. Se il codice non dispone dell'autorizzazione corrispondente, non verrà eseguito come descritto. Tuttavia, anche al codice viene concessa l'autorizzazione, il codice delle applicazioni da cui tale codice viene chiamato deve disporre della stessa autorizzazione per funzionare. Se il codice chiamante non dispone dell'autorizzazione appropriata, un <xref:System.Security.SecurityException> viene visualizzato a seguito di stack il codice di sicurezza l'accesso.

## <a name="application-code-that-isnt-a-reusable-component"></a>Codice dell'applicazione che non è un componente riutilizzabile

Se il codice è parte di un'applicazione che non verrà richiamata da altro codice, la sicurezza è semplice e potrebbe non essere necessario scrivere codice speciale. Tenere comunque presente che il codice può essere chiamato da codice dannoso. Anche se la sicurezza per l'accesso al codice può impedire a codice dannoso di accedere alle risorse, con questo codice è comunque possibile leggere i valori contenuti nei campi o nelle proprietà che possono rappresentare informazioni sensibili.

Se inoltre il codice accetta input da Internet o da altre fonti inaffidabili, è opportuno evitare input dannosi.

## <a name="managed-wrapper-to-native-code-implementation"></a>Wrapper gestiti nell'implementazione di codice nativo

In genere, in uno scenario di questo tipo, viene implementata una funzionalità utile nel codice nativo da rendere disponibile per il codice gestito. I wrapper gestiti possono essere scritti in modo semplice usando platform invoke o l'interoperabilità COM. Per la riuscita di questa operazione è tuttavia necessario che i chiamanti dei wrapper dispongano di diritti per il codice non gestito. In base ai criteri predefiniti, ciò significa che il codice scaricato da una rete intranet o Internet non funzionerà con i wrapper.

Anziché concedere diritti di codice non gestito per tutte le applicazioni che utilizzano questi wrapper, è preferibile fornire questi diritti solo al codice wrapper. Se la funzionalità sottostante non espone alcuna risorsa e l'implementazione è probabilmente sicura, per il wrapper è sufficiente l'asserzione dei diritti, che consente la chiamata tramite codice. Quando sono coinvolte le risorse, il codice della sicurezza deve essere analogo a quello di libreria descritto nella sezione successiva. Poiché il wrapper può esporre i chiamanti a queste risorse, la verifica attenta della sicurezza del codice nativo è necessaria e costituisce uno dei compiti del wrapper.

## <a name="library-code-that-exposes-protected-resources"></a>Codice di libreria che espone risorse protette

L'approccio seguente è più efficace e potenzialmente pericoloso, se eseguito in modo non corretto, codifica della sicurezza: la libreria funge da interfaccia per altro codice accedere ad alcune risorse non altrimenti disponibili, così come le classi .NET impongono autorizzazioni per le risorse che usano. Se si espone una risorsa, è necessario per prima cosa esigere tramite codice l'autorizzazione adeguata alla risorsa (in altre parole, eseguire un controllo di sicurezza) e quindi eseguire un'asserzione dei relativi diritti per eseguire l'operazione vera e propria.

## <a name="related-topics"></a>Argomenti correlati

|Titolo|Descrizione|
|-----------|-----------------|
|[Protezione dei dati di stato](securing-state-data.md)|Viene descritto come proteggere membri privati.|
|[Sicurezza e input dell'utente](security-and-user-input.md)|Vengono descritti argomenti relativi alla sicurezza delle applicazioni che accettano input dell'utente.|
|[Sicurezza e race condition](security-and-race-conditions.md)|Viene descritto come evitare race condition nel codice.|
|[Sicurezza e generazione di codice immediata](security-and-on-the-fly-code-generation.md)|Vengono descritti aspetti della sicurezza relativi alle applicazioni che consentono di generare codice dinamico.|
|[Sicurezza basata sui ruoli](role-based-security.md)|Viene descritta la sicurezza basata sui ruoli .NET in modo dettagliato e vengono fornite istruzioni per l'utilizzo nel codice.|
