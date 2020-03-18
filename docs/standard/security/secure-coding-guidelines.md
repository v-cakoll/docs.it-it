---
title: Linee guida per la codifica sicura per .NETSecure coding guidelines for .NET
description: Progettare il codice da utilizzare con . Autorizzazioni applicate net e altre applicazioni per impedire a codice dannoso di accedere ai dati o di eseguire altre azioni.
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
ms.openlocfilehash: 05f7e039ecdc0cd33baa015872924fb9e1f078aa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187719"
---
# <a name="secure-coding-guidelines"></a>Linee guida per la codifica sicura

La sicurezza basata sull'evidenza e la sicurezza per l'accesso al codice forniscono meccanismi espliciti molto efficaci per implementare la sicurezza. La maggior parte del codice dell'applicazione può semplicemente utilizzare l'infrastruttura implementata da .NET. In alcuni casi è tuttavia necessaria una sicurezza aggiuntiva specifica per l'applicazione, creata mediante l'estensione del sistema di sicurezza o tramite metodi ad hoc.

Utilizzando le autorizzazioni applicate .NET e altre applicazioni nel codice, è necessario erigere barriere per impedire al codice dannoso di accedere a informazioni che non si desidera che abbiano o eseguire altre azioni indesiderate. È inoltre necessario raggiungere un compromesso tra sicurezza e usabilità del codice in tutti gli scenari d'uso di codice attendibile.

In questa panoramica vengono descritti i diversi metodi di progettazione del codice per l'uso del sistema di sicurezza.

## <a name="securing-resource-access"></a>Protezione dell'accesso alle risorse

Durante la progettazione e la scrittura del codice, è necessario proteggere e limitare l'accesso del codice alle risorse, soprattutto quando si usa o chiama codice di origine sconosciuta. Le tecniche seguenti consentono di verificare che il codice sia sicuro:

- Non usare Sicurezza per l'accesso al codice (CAS, Code Access Security).

- Non usare codice parzialmente attendibile.

- Non utilizzare l'attributo [AllowPartiallyTrustedCaller](xref:System.Security.AllowPartiallyTrustedCallersAttribute) (APTCA).

- Non usare Servizi remoti .NET.

- Non usare DCOM (Distributed Component Object Model).

- Non utilizzare formattori binari.

La sicurezza dall'accesso di codice e il codice SecurityTransparent non sono supportati come limite di sicurezza con codice parzialmente attendibile. Non è consigliabile caricare ed eseguire codice di origine sconosciuta in assenza di misure di sicurezza alternative. Le misure di protezione alternative sono:

- Virtualizzazione

- AppContainers

- Utenti e autorizzazioni del sistema operativo (SO)

- Contenitori Hyper-V

## <a name="security-neutral-code"></a>Codice indipendente dalla sicurezza

Il codice indipendente dalla sicurezza non ha elementi espliciti in comune con il sistema di sicurezza e viene eseguito a prescindere dalle autorizzazioni ricevute Sebbene le applicazioni che non rilevano le eccezioni di sicurezza associate alle operazioni protette , ad esempio l'utilizzo di file, rete e così via, possono generare un'eccezione non gestita, il codice indipendente dalla sicurezza sfrutta ancora le tecnologie di sicurezza in .NET .

Una libreria indipendente dalla sicurezza dispone di caratteristiche speciali che è necessario comprendere. Si supponga che la libreria fornisca elementi API che utilizzano file o chiamano codice non gestito. Se il codice non dispone dell'autorizzazione corrispondente, non verrà eseguito come descritto. Tuttavia, anche al codice viene concessa l'autorizzazione, il codice delle applicazioni da cui tale codice viene chiamato deve disporre della stessa autorizzazione per funzionare. Se il codice chiamante non dispone <xref:System.Security.SecurityException> dell'autorizzazione corretta, viene visualizzato come risultato del percorso dello stack di sicurezza dall'accesso di codice.

## <a name="application-code-that-isnt-a-reusable-component"></a>Codice dell'applicazione che non è un componente riutilizzabileApplication code that isn't a reusable component

Se il codice fa parte di un'applicazione che non verrà chiamata da altro codice, la sicurezza è semplice e potrebbe non essere necessaria una codifica speciale. Tenere comunque presente che il codice può essere chiamato da codice dannoso. Anche se la sicurezza per l'accesso al codice può impedire a codice dannoso di accedere alle risorse, con questo codice è comunque possibile leggere i valori contenuti nei campi o nelle proprietà che possono rappresentare informazioni sensibili.

Se inoltre il codice accetta input da Internet o da altre fonti inaffidabili, è opportuno evitare input dannosi.

## <a name="managed-wrapper-to-native-code-implementation"></a>Wrapper gestito per l'implementazione del codice nativoManaged wrapper to native code implementation

In genere, in uno scenario di questo tipo, viene implementata una funzionalità utile nel codice nativo da rendere disponibile per il codice gestito. I wrapper gestiti possono essere scritti in modo semplice usando platform invoke o l'interoperabilità COM. Per la riuscita di questa operazione è tuttavia necessario che i chiamanti dei wrapper dispongano di diritti per il codice non gestito. In base ai criteri predefiniti, ciò significa che il codice scaricato da una rete Intranet o da Internet non funzionerà con i wrapper.

Anziché assegnare diritti di codice non gestito a tutte le applicazioni che utilizzano questi wrapper, è preferibile assegnare questi diritti solo al codice wrapper. Se la funzionalità sottostante non espone alcuna risorsa e l'implementazione è probabilmente sicura, per il wrapper è sufficiente l'asserzione dei diritti, che consente la chiamata tramite codice. Quando sono coinvolte le risorse, il codice della sicurezza deve essere analogo a quello di libreria descritto nella sezione successiva. Poiché il wrapper può esporre i chiamanti a queste risorse, la verifica attenta della sicurezza del codice nativo è necessaria e costituisce uno dei compiti del wrapper.

## <a name="library-code-that-exposes-protected-resources"></a>Codice di libreria che espone risorse protette

L'approccio seguente è il più potente e quindi potenzialmente pericoloso (se fatto in modo non corretto) per la codifica di sicurezza: la libreria funge da interfaccia per altro codice per accedere a determinate risorse che non sono altrimenti disponibili, proprio come le classi .NET applicare autorizzazioni per le risorse che utilizzano. Se si espone una risorsa, è necessario per prima cosa esigere tramite codice l'autorizzazione adeguata alla risorsa (in altre parole, eseguire un controllo di sicurezza) e quindi eseguire un'asserzione dei relativi diritti per eseguire l'operazione vera e propria.

## <a name="related-topics"></a>Argomenti correlati

|Titolo|Descrizione|
|-----------|-----------------|
|[Protezione dei dati di stato](securing-state-data.md)|Viene descritto come proteggere membri privati.|
|[Sicurezza e input dell'utente](security-and-user-input.md)|Vengono descritti argomenti relativi alla sicurezza delle applicazioni che accettano input dell'utente.|
|[Sicurezza e race condition](security-and-race-conditions.md)|Viene descritto come evitare race condition nel codice.|
|[Sicurezza e generazione di codice immediata](security-and-on-the-fly-code-generation.md)|Vengono descritti aspetti della sicurezza relativi alle applicazioni che consentono di generare codice dinamico.|
|[Sicurezza basata sui ruoli](role-based-security.md)|Viene descritta in dettaglio la sicurezza basata sui ruoli .NET e vengono fornite istruzioni per l'utilizzo nel codice.|
