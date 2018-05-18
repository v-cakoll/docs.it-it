---
title: considerazioni principali
description: Architettura di microservizi .NET per applicazioni .NET contenitori | considerazioni principali
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 880f99228dbfe7374878b497582ccf540658fc12
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="key-takeaways"></a>Considerazioni principali

Di seguito sono riportate le considerazioni principali e le conclusioni più importanti e le considerazioni principali da questa guida.

**Vantaggi dell'uso dei contenitori.** Le soluzioni basate su contenitori offrono vantaggi significativi in termini di risparmio sui costi perché i contenitori rappresentano una soluzione ai problemi di distribuzione causati dalla mancanza di dipendenze negli ambienti di produzione. I processi DevOps e le operazioni di produzione risultano quindi notevolmente migliorati.

**I contenitori saranno ovunque.** I contenitori basati su Docker stanno diventando lo standard di fatto nel settore dei contenitori e sono supportati dai principali fornitori negli ecosistemi Windows e Linux, inclusi Microsoft, Amazon AWS, Google e IBM. In un prossimo futuro, probabilmente Docker sarà presente in qualsiasi data center nel cloud o in locale.

**Contenitori come unità di distribuzione.** Il contenitore Docker sta diventando l'unità di distribuzione standard per qualsiasi applicazione o servizio basato su server.

**Microservizi.** L'architettura di microservizi sta diventando l'approccio preferito per le applicazioni strategiche distribuite, di grandi dimensioni o complesse basate su più sottosistemi indipendenti sotto forma di servizi autonomi. In un'architettura basata su microservizi, l'applicazione viene creata come una raccolta di servizi che possono essere sviluppati, testati, sottoposti a controllo delle versioni, distribuiti e ridimensionati in modo indipendente. Questo si applica anche a qualsiasi database autonomo correlato.

**Progettazione basata su dominio e architettura orientata ai servizi.** Gli schemi di architetture di microservizi derivano dall'architettura orientata ai servizi (SOA, Service-Oriented Architecture) e dalla progettazione basata su dominio (DDD, Domain-Driven Design). Quando si progettano e si sviluppano microservizi per ambienti con regole di business in evoluzione che formano un dominio specifico, è importante tenere conto degli approcci e degli schemi della progettazione DDD.

**Problematiche relative ai microservizi.** I microservizi offrono molte funzionalità utili, ad esempio la distribuzione indipendente, confini rigidi per i sottosistemi ed eterogeneità di tecnologie. Tuttavia, generano anche numerose problematiche relative allo sviluppo di applicazioni distribuite, ad esempio modelli di dati indipendenti e frammentati, comunicazione resiliente tra microservizi, coerenza finale e complessità operativa derivanti dall'aggregazione di informazioni di registrazione e monitoraggio da più microservizi. Questi aspetti introducono un livello di complessità più elevato rispetto a quello di un'applicazione monolitica tradizionale. Di conseguenza, solo scenari specifici sono adatti alle applicazioni basate su microservizi, come le applicazioni di grandi dimensioni e complesse con più sottosistemi in evoluzione. In questi casi, è più opportuno investire in un'architettura software più complessa perché fornirà una migliore agilità e garantirà una gestione dell'applicazione ottimale a lungo termine.

**Contenitori per tutte le applicazioni.** I contenitori sono utili per i microservizi, ma non solo. Possono essere usati per applicazioni monolitiche, incluse le applicazioni legacy basate su .NET Framework tradizionale e modernizzate tramite contenitori Windows. I vantaggi offerti da Docker, ad esempio la risoluzione di numerosi problemi dalla fase di distribuzione alla fase di produzione e ambienti di sviluppo e test all'avanguardia, si applicano a vari tipi di applicazioni.

**Interfaccia della riga di comando e ambiente di sviluppo integrato (IDE).** Con gli strumenti Microsoft è possibile sviluppare applicazioni .NET in contenitori usando l'approccio preferito. È possibile usare l'interfaccia della riga di comando e un ambiente basato su editor con l'interfaccia della riga di comando di Docker e Visual Studio Code. In alternativa, è possibile scegliere un approccio incentrato sull'ambiente di sviluppo integrato con Visual Studio e le esclusive funzionalità per Docker disponibili, ad esempio il debug di applicazioni multicontenitore.

**Applicazioni cloud resilienti.** Nei sistemi basati sul cloud e nei sistemi distribuiti in generale, esiste sempre il rischio di errori parziali. Poiché i client e i servizi sono processi separati (contenitori), un servizio potrebbe non riuscire a rispondere tempestivamente a una richiesta del client. Ad esempio, un servizio potrebbe essere inattivo a causa di un errore parziale o per attività di manutenzione, oppure potrebbe essere sovraccarico e rispondere molto lentamente alle richieste o semplicemente non essere accessibile per un breve periodo di tempo a causa di problemi di rete. Di conseguenza, un'applicazione basata sul cloud deve tenere conto di questi errori e prevedere una strategia per rispondervi tempestivamente. Queste strategie possono includere criteri per i tentativi (inviare di nuovo i messaggi o ripetere le richieste) e l'implementazione di schemi di interruzione di circuito per evitare il carico esponenziale di richieste ripetute. In pratica, le applicazioni basate sul cloud devono prevedere meccanismi resilienti, personalizzati o basati sull'infrastruttura cloud, ad esempio framework di alto livello, da agenti di orchestrazione o bus di servizio.

**Sicurezza.** Questo mondo moderno con contenitori e microservizi può esporre nuove vulnerabilità. La sicurezza delle applicazioni di base si fonda su autenticazione e autorizzazione e sono disponibili vari modi per implementarle. La sicurezza dei contenitori include tuttavia altri componenti principali che generano applicazioni intrinsecamente più sicure. Un elemento strategico della creazione di app più sicure è prevedere un modo sicuro per comunicare con altre app e sistemi e questo spesso richiede credenziali, token, password e altri tipi di informazioni riservate, note come segreti dell'applicazione. Qualsiasi soluzione sicura deve seguire le procedure consigliate per la sicurezza, ad esempio la crittografia dei segreti in transito, la crittografia dei segreti a riposo e la perdita accidentale dei segreti quando sono utilizzati dall'applicazione finale. I segreti devono essere archiviati e conservati al sicuro da qualche parte. Per garantire la sicurezza, è possibile sfruttare l'infrastruttura dell'agente di orchestrazione scelta o dell'infrastruttura cloud, ad esempio Azure Key Vault e delle funzionalità che offre per il codice dell'applicazione.

**Agenti di orchestrazione.** Gli agenti di orchestrazione basati su contenitori, come quelli forniti nel servizio contenitore di Azure (Kubernetes, Mesosphere DC/OS e Docker Swarm) e in Azure Service Fabric sono indispensabili per qualsiasi applicazione multicontenitore o basata su microservizi per ambienti di produzione con esigenze elevate in termini di complessità scalabilità in continua evoluzione. Questa guida ha illustrato gli agenti di orchestrazione e il ruolo che hanno nelle soluzioni basate su microservizi e su contenitori. Se le esigenze dell'applicazione indirizzano verso le applicazioni in contenitori complesse, è possibile consultare risorse aggiuntive per acquisire maggiori informazioni sugli agenti di orchestrazione

>[!div class="step-by-step"]
[Indietro] (secure-net-microservices-web-applications/azure-key-vault-protects-secrets.md)
