---
title: Caratteristiche di moderne applicazioni web
description: Architettura di moderne applicazioni Web con ASP.NET Core e Azure | caratteristiche di moderne applicazioni web
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: 9ff9380b318457a842dec4e41b9b74dcddcda3d3
ms.sourcegitcommit: 882e02b086d7cb9c75f748494cf7a8d3377c5874
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2017
---
# <a name="characteristics-of-modern-web-applications"></a>Caratteristiche di moderne applicazioni Web

> "… con la progettazione adeguata, le funzionalità disponibili economici. Questo approccio è complicato, ma continua ad avere esito positivo."  
> _\-Dennis Ritchie hanno_

## <a name="summary"></a>Riepilogo

Applicazioni web moderne hanno maggiore aspettative degli utenti e richieste maggiore rispetto al passato. App web attuali devono essere disponibili 24/7 da ovunque nel mondo e utilizzabile da qualsiasi dispositivo o la dimensione dello schermo. Applicazioni Web devono essere protetta, flessibile e scalabile per soddisfare i picchi di richiesta. Sempre più scenari complessi devono essere gestiti esperienze utente complete compilate nel client utilizzando JavaScript e la comunicazione in modo efficiente tramite l'API web.

ASP.NET Core è ottimizzato per scenari di hosting basato su cloud e applicazioni web moderne. Il design modulare consente alle applicazioni da cui dipendere solo le funzionalità che utilizzano direttamente, miglioramento della sicurezza delle applicazioni e le prestazioni riducendo i requisiti di risorse host.

## <a name="reference-application-eshoponweb"></a>Fare riferimento applicazione: eShopOnWeb

Questa guida include un'applicazione di riferimento, *eShopOnWeb*, che illustra alcune dei principi e le indicazioni. L'applicazione è un archivio online semplice, che supporta l'esplorazione tramite un catalogo di shirts tazze caffè e altri elementi di marketing. L'applicazione di riferimento è intenzionalmente semplice per rendere ancora più facile da comprendere.

**Figura 2-1.** eShopOnWeb

![](./media/image2-1.png)

> ### <a name="reference-application"></a>Applicazione di riferimento
> - **eShopOnWeb**  
> <https://github.com/dotnet/eShopOnWeb>

## <a name="cloud-hosted-and-scalable"></a>Ospitato su cloud e scalabile

ASP.NET Core è ottimizzato per il cloud (cloud pubblico, cloud privato, qualsiasi) perché è di poca memoria e velocità effettiva elevata. È possibile ospitare più di esse sullo stesso hardware, e si paga per meno risorse quando tramite l'utilizzo di pagamento capacità di passare i servizi di hosting cloud, significa che il footprint ridotto di applicazioni ASP.NET Core. Maggiore velocità, significa che sarà possibile disporre di più clienti da un'applicazione ha lo stesso hardware, riducendo ulteriormente la necessità di investire in server e infrastruttura di hosting.

## <a name="cross-platform"></a>Multipiattaforma

ASP.NET Core è multipiattaforma ed è possibile eseguire su Linux e MacOS nonché Windows. Verrà visualizzata molte nuove opzioni per lo sviluppo e distribuzione di applicazioni compilate con ASP.NET Core. Contenitori di docker, che in genere eseguito Linux oggi stesso, possono ospitare applicazioni ASP.NET Core, consentendo loro di sfruttare i vantaggi di [contenitori e microservizi](../microservices-architecture).

## <a name="modular-and-loosely-coupled"></a>Modulare e regime di controllo

I pacchetti NuGet sono elementi di primaria importanza in .NET Core e le applicazioni ASP.NET Core sono costituite da molte librerie mediante NuGet. La granularità di funzionalità consente di garantire le app solo dipendono e distribuire effettivamente richiedono, ridurre il footprint e sicurezza vulnerabilità superficie funzionalità.

ASP.NET Core supporta completamente l'inserimento di dipendenze, internamente e a livello di applicazione. Le interfacce possono avere più implementazioni che possono essere scambiate in base alle esigenze. Inserimento di dipendenze consente applicazioni a regime di controllo libero coppia tali interfacce, rendendoli più semplice da estendere, gestire e testare.

## <a name="easily-tested-with-automated-tests"></a>Facilmente testate con test automatizzati

Applicazioni ASP.NET Core supportano gli unit test e i relativi regime di controllo e il supporto per attacchi intrusivi nelle dipendenze semplifica scambiare i problemi di infrastruttura implementazioni fittizio per scopi di test. ASP.NET Core viene inoltre fornito un TestServer che può essere utilizzato per le applicazioni host in memoria. Test funzionali può effettuare richieste al server, in memoria che esercitano lo stack dell'applicazione completo (incluso middleware, routing, l'associazione del modello, i filtri e così via) e la ricezione di una risposta, in una frazione del tempo necessario per ospitare l'applicazione in un server reale e le richieste attraverso il livello di rete. Questi test sono particolarmente facili da scrivere e importanti, per le API che sono sempre più importanti in applicazioni web moderne.

## <a name="traditional-and-spa-behaviors-supported"></a>Tradizionali e i comportamenti SPA supportati

Applicazioni web tradizionali implicato piccolo comportamento sul lato client, ma invece si basavano sul server per la navigazione, query e l'app potrebbe essere necessario apportare aggiornamenti. Ogni nuova operazione effettuata dall'utente potrebbe essere convertito in una nuova richiesta web, con risultato un ricaricamento dell'intera pagina nel browser dell'utente finale. Framework Model-View-Controller (MVC) classico, in genere, seguire questo approccio, con ogni nuova richiesta corrispondente a un'azione del controller diverso, che a sua volta utilizzare un modello e restituire una visualizzazione. Alcune operazioni singole in una determinata pagina potrebbero essere migliorati con funzionalità AJAX (Asynchronous JavaScript and XML), ma l'architettura complessiva dell'applicazione utilizzata in molte visualizzazioni MVC ed endpoint URL.

Applicazioni a pagina singola (stabilimenti termali), comportano invece pochissime generato dinamicamente sul lato server pagina Carica (se presente). Molti stabilimenti termali vengono inizializzati all'interno di un file HTML statico, che consente di caricare le librerie JavaScript necessarie per avviare ed eseguire l'app. Queste App apportare un utilizzo intenso di API web per le esigenze di dati e possono fornire che esperienze utente molto più dettagliato.

Molte applicazioni web comportano una combinazione di comportamento dell'applicazione web tradizionale (in genere per il contenuto) e stabilimenti termali (per l'interattività). ASP.NET Core supporta MVC e web API nella stessa applicazione, utilizzando lo stesso set di strumenti e librerie del framework sottostante.

## <a name="simple-development-and-deployment"></a>Sviluppo semplice e distribuzione

Applicazioni ASP.NET Core possono essere scritte utilizzando l'editor di testo semplice e interfacce della riga di comando o in ambienti di sviluppo completo come Visual Studio. Applicazioni monolitiche vengono in genere distribuite in un singolo endpoint. Le distribuzioni possono facilmente essere automatizzate per si verificano nell'ambito di una pipeline di recapito continuo (CD) e di integrazione continua (CI). Oltre agli strumenti CI/CD tradizionali, Windows Azure dispone del supporto per i repository git integrato e possono distribuire automaticamente gli aggiornamenti non appena vengono eseguite in un ramo git specificato o un tag.

## <a name="traditional-aspnet-and-web-forms"></a>ASP.NET tradizionale e Web Form

Oltre a ASP.NET Core, tradizionale ASP.NET 4. x continua a essere una piattaforma solida e affidabile per la compilazione di applicazioni web. ASP.NET supporta i modelli di sviluppo MVC e Web API, nonché i Web Form, che è ideale per lo sviluppo di applicazioni basate su pagina avanzate e le funzionalità di un ecosistema di componenti di terze parti completo. Molti sviluppatori hanno familiarità con la piattaforma Windows Azure ha supporto consolidato ottimale per le applicazioni ASP.NET 4. x.

> ### <a name="references--modern-web-applications"></a>Riferimenti: moderne applicazioni Web
> - **Introduzione a ASP.NET Core**  
> <https://docs.microsoft.com/ASPNET/core/>
> - **Sei chiave vantaggi di ASP.NET Core che rendono differente e una situazione migliore**  
> <https://blog.trigent.com/Six-Key-Benefits-of-ASP-NET-core-1-0-Which-Make-IT-Different-Better/>
> - **Test in ASP.NET Core**  
> <https://docs.microsoft.com/ASPNET/core/testing/>

>[!div class="step-by-step"]
[Precedente] [Avanti] (choose-between-traditional-web-and-single-page-apps.md) (index.md)
