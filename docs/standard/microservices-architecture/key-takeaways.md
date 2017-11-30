---
title: materiale chiave
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | materiale chiave
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: b557d0b641bfe95c025cadb13f82c3f8927f4bc8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="key-takeaways"></a>Materiale chiave

Come un riepilogo e materiale chiave, di seguito sono riassunte le conclusioni più importanti in questa Guida.

**Vantaggi dell'utilizzo di contenitori.** Soluzioni basate sul contenitore forniscono il vantaggio importante di riduzione dei costi poiché contenitori sono una soluzione per i problemi di distribuzione ha causato dalla mancanza di dipendenze in ambienti di produzione. Contenitori di migliorare significativamente le operazioni di DevOps e produzione.

**Contenitori sarà universali.** Contenitori basati su docker sono sempre fatto standard nel settore contenitore, è supportato dai fornitori a più significativi in ecosistemi Windows e Linux. Sono inclusi Microsoft, Amazon AWS, Google e IBM. Docker in un prossimo futuro, probabilmente sarà diffuso nei Data Center sia in locale e cloud.

**Contenitori come un'unità di distribuzione.** Un contenitore Docker è sempre l'unità di distribuzione per qualsiasi applicazione basata su server o di servizio standard.

**Microservizi.** L'architettura di microservizi è sempre la scelta migliore per le applicazioni cruciali distribuite e grandi dimensioni o complesse in base a più sottosistemi indipendenti sotto forma di servizi autonomi. In un'architettura basata su microservizio, l'applicazione viene compilata come una raccolta di servizi che possono essere sviluppati, testati, con controllo delle versioni, distribuiti e ridimensionate in modo indipendente; può trattarsi di qualsiasi database autonomi correlati.

**Progettazione basati su dominio e SOA.** I modelli di architettura microservizi derivano da architettura orientata ai servizi (SOA) e progettazione basati su dominio (DDD). Quando si progettano e sviluppano microservizi per gli ambienti con l'evoluzione di regole di business data shaping un particolare dominio, è importante tener conto DDD approcci e i pattern.

**Problematiche di Microservizi.** Microservizi offrono potenti funzionalità, quali distribuzione indipendente, limiti del sottosistema sicuro e diversità di tecnologia. Tuttavia, anche generano molte nuove problematiche correlate allo sviluppo di applicazioni distribuite, ad esempio frammentato e modelli di dati indipendenti, resiliente comunicazione tra microservizi coerenza finale e la complessità operativa risultante dalla aggregazione delle informazioni di registrazione e di monitoraggio da più microservizi. Questi aspetti introducono un livello di complessità superiore rispetto a un'applicazione monolitico tradizionale. Di conseguenza, solo di scenari specifici sono adatti per le applicazioni basate su microservizio. Sono incluse le applicazioni di grandi e complesse con più sottosistemi in continua evoluzione; In questi casi, è importante investire in un'architettura software più complessa, in quanto fornirà a lungo termine migliori flessibilità e la manutenzione dell'applicazione.

**Contenitori per qualsiasi applicazione.** Contenitori sono particolarmente utili per microservizi, ma non sono esclusivi per loro. Contenitori anche utilizzabile con le applicazioni monolitiche, incluse le applicazioni legacy basate su .NET Framework tradizionale e moderno e attraverso i contenitori di Windows. Vantaggi dell'utilizzo di Docker, ad esempio la risoluzione di molti problemi di distribuzione in produzione e di fornire ambienti di sviluppo e Test all'avanguardia, si applicano a molti tipi diversi di applicazioni.

**CLI e IDE.** Con strumenti di Microsoft, è possibile sviluppare applicazioni .NET nei contenitori usando l'approccio consigliato. È possibile sviluppare con CLI e un ambiente basato su editor usando l'interfaccia CLI di Docker e codice di Visual Studio. Oppure è possibile utilizzare un approccio incentrato sull'IDE in Visual Studio e le funzionalità esclusive per Docker, come ad esempio in grado di eseguire il debug di applicazioni multi-contenitore.

**Applicazioni cloud resilienti.** Nei sistemi basati su cloud e i sistemi distribuiti in generale, è sempre il rischio di errori parziali. Poiché i client e servizi sono processi separati (contenitori), un servizio potrebbe non essere in grado di rispondere in modo tempestivo a una richiesta del client. Ad esempio, un servizio potrebbe essere inattivo a causa dell'errore parziale o per la manutenzione; il servizio potrebbe essere in overload e risponde solo molto lentamente a richiesta; o potrebbe semplicemente non essere accessibile per un breve periodo di tempo a causa di problemi di rete. Pertanto, un'applicazione basata su cloud deve adottare questi problemi e disporre di una strategia per rispondere a questi problemi. Tali strategie possono includere criteri di ripetizione (rinvio di messaggi o tentativi di richiesta) e implementazione modelli interruttore per evitare esponenziale carico delle richieste ripetute. In pratica, le applicazioni basate su cloud devono avere resilienti meccanismi, ovvero personalizzato quelle oppure quelle basate sull'infrastruttura di cloud, ad esempio Framework di alto livello da orchestrators o bus di servizio.

**Sicurezza.** Mondo moderno di contenitori e microservizi può esporre nuove vulnerabilità. Sicurezza delle applicazioni di base si basa sull'autenticazione e autorizzazione; diversi modi disponibili per implementare questi elementi. Tuttavia, la sicurezza di contenitore include ulteriori componenti chiave che nelle applicazioni intrinsecamente più sicure. Un elemento critico di creazione di applicazioni più sicure in caso di un metodo sicuro per la comunicazione con altri sistemi e applicazioni, un elemento che spesso richiede le credenziali, i token, password e altri tipi di informazioni riservate, in genere definite come segreti dell'applicazione. Qualsiasi soluzione di protezione necessario seguire procedure ottimali di protezione, ad esempio la crittografia dei segreti in transito; la crittografia dei segreti inattivi; e impedire che i segreti involontariamente perdita quando utilizzati dall'applicazione finale. Segreti devono essere archiviati e protetti in una posizione. Per facilitare la protezione, è possibile usufruire dell'infrastruttura di orchestrator selezionato o dell'infrastruttura cloud come insieme di credenziali chiave di Azure e i modi in cui vengono forniti per il codice dell'applicazione per utilizzarlo.

**Orchestrators.** Sono indispensabili per le applicazioni basate su microservizio di ambiente di produzione e per qualsiasi multi-contenitore orchestrators basate sul contenitore come quelle disponibili in servizio contenitore di Azure (Kubernetes Mesos DC/OS e Docker Swarm) e Azure Service Fabric applicazione con la costante evoluzione, esigenze di scalabilità e rende più complessa. Questa guida è state introdotte orchestrators e il relativo ruolo nelle soluzioni basate sul contenitore e microservizio. Se si stanno spostando verso complesse applicazioni nei contenitori le esigenze dell'applicazione, si verrà risultare utile per cercare risorse aggiuntive per ottenere ulteriori informazioni su orchestrators

>[!div class="step-by-step"]
[Precedente] (secure-net-microservices-web-applications/azure-key-vault-protects-secrets.md)
