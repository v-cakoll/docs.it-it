---
title: Considerazioni principali
description: Considerazioni principali nella guida/ebook Architettura di microservizi .NET per applicazioni .NET in contenitori, che consentono un esame rapido degli aspetti principali dell'uso di un'architettura di microservizi, quali vantaggi e svantaggi, modelli DDD per la progettazione e lo sviluppo, nonché resilienza, sicurezza e uso di agenti di orchestrazione.
ms.date: 10/19/2018
ms.openlocfilehash: 0e793a76fa59d6c131422480071d85ab3f18102c
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988778"
---
# <a name="key-takeaways"></a>Risultati principali

Di seguito sono riportate le considerazioni principali e le conclusioni più importanti e le considerazioni principali da questa guida.

**Vantaggi dell'uso dei contenitori.** Le soluzioni basate su contenitori offrono importanti risparmi sui costi, perché contribuiscono a ridurre i problemi di distribuzione causati da errori delle dipendenze negli ambienti di produzione. I processi DevOps e le operazioni di produzione risultano quindi notevolmente migliorati.

**I contenitori saranno ovunque.** I contenitori basati su Docker stanno diventando lo standard di fatto nel settore e sono supportati dai principali fornitori negli ecosistemi Windows e Linux, quali Microsoft, Amazon AWS, Google e IBM. In un futuro prossimo è probabile che Docker sia presente in qualsiasi data center nel cloud o in locale.

**Contenitori come unità di distribuzione.** Il contenitore Docker sta diventando l'unità di distribuzione standard per qualsiasi applicazione o servizio basato su server.

**Microservizi.** L'architettura di microservizi sta diventando l'approccio preferito per le applicazioni strategiche distribuite, di grandi dimensioni o complesse basate su più sottosistemi indipendenti sotto forma di servizi autonomi. In un'architettura basata sui microservizi, l'applicazione viene creata come raccolta di servizi che vengono sviluppati, testati, sottoposti a controllo della versione, distribuiti e scalati in modo indipendente. Ogni servizio può includere qualsiasi database autonomo correlato.

**Progettazione basata su dominio e architettura orientata ai servizi.** Gli schemi di architetture di microservizi derivano dall'architettura orientata ai servizi (SOA, Service-Oriented Architecture) e dalla progettazione basata su dominio (DDD, Domain-Driven Design). Quando si progettano e si sviluppano microservizi per ambienti con esigenze e regole di business in evoluzione, è importante tenere conto degli approcci e degli schemi della progettazione DDD.

**Problematiche relative ai microservizi.** I microservizi offrono molte funzionalità utili, ad esempio la distribuzione indipendente, confini rigidi per i sottosistemi ed eterogeneità di tecnologie. Tuttavia, generano anche numerose problematiche relative allo sviluppo di applicazioni distribuite, ad esempio modelli di dati indipendenti e frammentati, comunicazione resiliente tra microservizi, coerenza finale e complessità operativa derivanti dall'aggregazione di informazioni di registrazione e monitoraggio da più microservizi. Questi aspetti introducono un livello di complessità molto più elevato rispetto a quello di un'applicazione monolitica tradizionale. Di conseguenza, solo scenari specifici sono adatti alle applicazioni basate su microservizi, come le applicazioni di grandi dimensioni e complesse con più sottosistemi in evoluzione. In questi casi è opportuno investire in un'architettura software più complessa, perché offrirà una migliore agilità e garantirà una gestione dell'applicazione ottimale a lungo termine.

**Contenitori per tutte le applicazioni.** I contenitori sono vantaggiosi per i microservizi, ma possono anche essere utili per le applicazioni monolitiche basate su .NET Framework tradizionale quando si usano i contenitori Windows. I vantaggi offerti da Docker, quali la risoluzione di numerosi problemi dalla fase di distribuzione alla fase di produzione e ambienti di sviluppo e test all'avanguardia, si applicano a vari tipi di applicazioni.

**Interfaccia della riga di comando e ambiente di sviluppo integrato (IDE).** Con gli strumenti Microsoft è possibile sviluppare applicazioni .NET in contenitori usando l'approccio preferito. È possibile usare l'interfaccia della riga di comando e un ambiente basato su editor con l'interfaccia della riga di comando di Docker e Visual Studio Code. In alternativa è possibile scegliere un approccio incentrato sull'ambiente di sviluppo integrato con Visual Studio e le esclusive funzionalità per Docker disponibili, ad esempio il debug di applicazioni multicontenitore.

**Applicazioni cloud resilienti.** Nei sistemi basati sul cloud e nei sistemi distribuiti in generale, esiste sempre il rischio di errori parziali. Poiché i client e i servizi sono processi separati (contenitori), un servizio potrebbe non essere in grado di rispondere in modo tempestivo alla richiesta di un client. Ad esempio un servizio potrebbe essere inattivo a causa di un errore parziale o per attività di manutenzione, oppure potrebbe essere sovraccarico e rispondere lentamente alle richieste o non essere accessibile per un breve periodo di tempo a causa di problemi di rete. Di conseguenza, un'applicazione basata sul cloud deve tenere conto di questi errori e prevedere una strategia per rispondervi tempestivamente. Queste strategie possono includere criteri per i tentativi (inviare di nuovo i messaggi o ripetere le richieste) e l'implementazione di schemi di interruzione di circuito per evitare il carico esponenziale di richieste ripetute. In pratica, le applicazioni basate sul cloud devono prevedere meccanismi resilienti (basati sull'infrastruttura cloud o personalizzati), come quelli di alto livello forniti da agenti di orchestrazione o bus di servizio.

**Sicurezza.** Questo mondo moderno con contenitori e microservizi può esporre nuove vulnerabilità. Esistono varie modalità per l'implementazione della sicurezza delle applicazioni di base, tramite l'autenticazione e l'autorizzazione. La sicurezza dei contenitori deve tuttavia tenere conto di altri componenti principali che generano applicazioni intrinsecamente più sicure. Un elemento strategico della creazione di app più sicure è la previsione di un modo sicuro per comunicare con altre app e sistemi, e questo spesso richiede credenziali, token, password ed elementi simili, noti come segreti dell'applicazione. Qualsiasi soluzione sicura deve osservare le procedure consigliate per la sicurezza, ad esempio la crittografia dei segreti in transito e a riposo e il blocco della perdita accidentale dei segreti quando sono usati dall'applicazione finale. Questi segreti dover essere archiviati e mantenuti in modo sicuro, ad esempio con l'uso di Azure Key Vault.

**Orchestratori.** Gli agenti di orchestrazione basati su container, come il servizio Azure Kubernetes e Azure Service Fabric, sono una parte essenziale di qualsiasi applicazione importante di microservizi basata sui contenitori. Queste applicazioni supportano una complessità elevata, si adattano alle esigenze di scalabilità e si evolvono in continuazione. Questa guida ha illustrato gli agenti di orchestrazione e il ruolo che hanno nelle soluzioni basate su microservizi e su contenitori. Se le esigenze a livello di applicazioni indirizzano verso le applicazioni in contenitori complesse, è possibile vedere risorse aggiuntive per acquisire maggiori informazioni sugli agenti di orchestrazione.

>[!div class="step-by-step"]
>[Indietro](secure-net-microservices-web-applications/azure-key-vault-protects-secrets.md)
