---
title: Caratteristiche delle applicazioni Web moderne
description: Progettare applicazioni Web moderne con ASP.NET Core e Azure | Caratteristiche delle applicazioni Web moderne
author: ardalis
ms.author: wiwagn
no-loc:
- Blazor
- WebAssembly
ms.date: 12/04/2019
ms.openlocfilehash: fd6658a6143e132d488660d1aa4a35e427ba2d84
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174796"
---
# <a name="characteristics-of-modern-web-applications"></a>Caratteristiche delle applicazioni Web moderne

> "… con la progettazione adeguata, i costi delle funzionalità risultano competitivi. Questo approccio è complesso, ma continua a dare risultati positivi".  
> _\-Dennis Ritchie_

Le applicazioni Web moderne devono soddisfare esigenze e aspettative degli utenti sempre più importanti. Oggi le app Web devono essere disponibili 24 ore al giorno, ogni giorno e in qualsiasi parte del mondo e devono poter essere usate su qualsiasi dispositivo o su uno schermo di qualsiasi dimensione. Le applicazioni Web devono essere sicure, flessibili e scalabili, per soddisfare i picchi di richiesta. Scenari sempre più complessi devono essere gestiti con esperienze utente complete, app compilate nel client con JavaScript e in grado di comunicare adeguatamente tramite le API Web.

ASP.NET Core è ottimizzato per le applicazioni Web moderne e gli scenari di hosting nel cloud. Grazie al design modulare della soluzione, le applicazioni dipendono solo dalle funzionalità che effettivamente usano, migliorando la sicurezza e le prestazioni e riducendo i requisiti per la risorsa host.

## <a name="reference-application-eshoponweb"></a>Applicazione di riferimento: eShopOnWeb

Questa guida include un'applicazione di riferimento, _eShopOnWeb_, che dimostra alcune idee e suggerimenti. L'applicazione è un semplice negozio online, nel quale gli utenti possono consultare un catalogo di T-shirt, tazze da caffè e altri articoli di marketing. L'applicazione di riferimento è volutamente semplice, perché sia facile comprenderne il funzionamento.

![eShopOnWeb](./media/image2-1.png)

**Figura 2-1.** eShopOnWeb

> ### <a name="reference-application"></a>Applicazione di riferimento
>
> - **eShopOnWeb**  
>   <https://github.com/dotnet/eShopOnWeb>

## <a name="cloud-hosted-and-scalable"></a>Ospitato nel cloud e scalabile

Il framework ASP.NET Core è ottimizzato per il cloud (sia pubblico che privato) perché fa un uso ridotto della memoria e garantisce velocità effettive elevate. Il footprint ridotto delle applicazioni ASP.NET Core significa che è possibile ospitarne di più nello stesso componente hardware e ridurre i costi quando si usano servizi di hosting su cloud con il modello di pagamento a consumo. La velocità effettiva superiore consente di raggiungere più clienti da un'applicazione residente in un determinato componente hardware, riducendo ulteriormente gli investimenti in server e infrastrutture di hosting.

## <a name="cross-platform"></a>Multipiattaforma

ASP.NET Core è multipiattaforma e può essere eseguito in Linux, macOS e Windows. Ciò apre molte nuove opzioni per lo sviluppo e la distribuzione di app compilate con ASP.NET Core. I contenitori Docker sia Linux che Windows possono ospitare applicazioni ASP.NET Core e avvalersi così dei vantaggi offerti da [contenitori e microservizi](../microservices/index.md).

## <a name="modular-and-loosely-coupled"></a>Modulare e loosely coupled

I pacchetti NuGet sono perfettamente compatibili in .NET Core e la struttura con molte librerie delle app ASP.NET Core dipende da NuGet. La granularità delle funzionalità garantisce che le app eseguano e distribuiscano solo le funzionalità necessarie, riducendo la superficie di attacco per le vulnerabilità di sicurezza.

ASP.NET Core inoltre supporta completamente l' [inserimento delle dipendenze](https://deviq.com/dependency-injection/), sia internamente che a livello di applicazione. Le interfacce possono avere più implementazioni, intercambiabili in base alle esigenze. L'inserimento delle dipendenze consente l'accoppiamento debole delle app a tali interfacce, anziché a implementazioni specifiche, semplificandone l'estensione, la gestione e il test.

## <a name="easily-tested-with-automated-tests"></a>Test automatizzati

Le applicazioni ASP.NET Core supportano gli unit test, l'accoppiamento libero e l'inserimento delle dipendenze, pertanto risulta facile sostituire le sezioni dell'infrastruttura che causano problemi con implementazioni fittizie per l'esecuzione di test. ASP.NET Core viene fornito anche con un TestServer che può essere usato per ospitare le app in memoria. I test funzionali possono quindi inoltrare richieste a questo server in memoria, usando l'intero stack dell'applicazione (middleware, routing, binding dei modelli, filtri e così via) e ricevendo una risposta, il tutto in una frazione del tempo che sarebbe necessario per impostare l'hosting dell'app in un server reale e inoltrare richieste attraverso il layer di rete. Questi test sono facili da scrivere e particolarmente utili per le API, che sono sempre più importanti nelle applicazioni Web moderne.

## <a name="traditional-and-spa-behaviors-supported"></a>Supporto di comportamenti tradizionali e delle applicazioni a pagina singola

Le applicazioni Web tradizionali includono comportamenti lato client limitati, ma si basano sul server per tutte le attività di navigazione, query e aggiornamento. Ogni nuova operazione eseguita dall'utente diventa una nuova richiesta Web e richiede un nuovo caricamento completo della pagina nel browser dell'utente finale. I framework Model-View-Controller (MVC , Modello-Visualizzazione-Controller) classici seguono in genere questo approccio, in cui ogni nuova richiesta corrisponde a un'azione del controller diversa che a sua volta interagisce con un modello e restituisce una visualizzazione. Alcune operazioni singole su una determinata pagina possono essere migliorate con la funzionalità AJAX (Asynchronous JavaScript and XML), ma l'architettura complessiva dell'app usa molte visualizzazioni MVC e molti endpoint URL diversi. ASP.NET Core MVC supporta anche Razor Pages, un modo più semplice per organizzare le pagine in stile MVC.

Le applicazioni a pagina singola, al contrario, richiedono un numero molto limitato di caricamenti pagina generati dinamicamente sul lato server. Molte applicazioni a pagina singola vengono inizializzate all'interno di un file HTML statico, che carica le librerie JavaScript necessarie per avviare ed eseguire l'app. Queste app usano in modo intensivo le API Web per ottenere i dati necessari e possono offrire esperienze utente molto più complete.

Molte applicazioni Web presentano una combinazione di comportamenti dell'applicazione Web tradizionale (in genere per il contenuto) e applicazioni a pagina singola (per l'interattività). ASP.NET Core supporta sia MVC (Viste e Pagine) sia le API Web nella stessa applicazione, usando lo stesso set di strumenti e librerie del framework sottostanti.

## <a name="simple-development-and-deployment"></a>Sviluppo e distribuzione facili

ASP.NET Core applicazioni possono essere scritte usando semplici editor di testo e interfacce della riga di comando o ambienti di sviluppo completi come Visual Studio. In genere le applicazioni monolitiche vengono distribuite a un singolo endpoint. Le distribuzioni possono essere facilmente automatizzate e incluse in una pipeline di integrazione continua (CI, Continuous Integration) e recapito continuo (CD, Continuous Delivery). Oltre agli strumenti di integrazione continua/distribuzione continua tradizionale, Microsoft Azure ha integrato il supporto per i repository git e può distribuire automaticamente gli aggiornamenti man mano che vengono apportati a un ramo o un tag git specificato. Azure DevOps offre una pipeline di compilazione e distribuzione di integrazione continua e distribuzione continua con funzionalità complete e le azioni di GitHub forniscono un'altra opzione per i progetti ospitati.

## <a name="traditional-aspnet-and-web-forms"></a>ASP.NET tradizionale e Web Form

Oltre ad ASP.NET Core, anche ASP.NET 4.x continua a rappresentare una piattaforma solida e affidabile per la compilazione di applicazioni Web. ASP.NET supporta i modelli di sviluppo dell'API Web e MVC, oltre a Web Form, ideale per lo sviluppo di applicazioni avanzate basate su pagine e che offre un ricco ecosistema di componenti di terze parti. Microsoft Azure offre un notevole supporto di lunga durata per le applicazioni ASP.NET 4. x e molti sviluppatori hanno familiarità con questa piattaforma.

## Blazor

Blazorè incluso in ASP.NET Core 3,0 e versioni successive. Fornisce un nuovo meccanismo per la creazione di applicazioni client Web interattive avanzate con Razor, C# e ASP.NET Core. Offre un'altra soluzione da considerare durante lo sviluppo di applicazioni Web moderne. Esistono due versioni di Blazor da considerare: lato server e lato client.

Il lato server Blazor è stato rilasciato in 2019 con ASP.NET Core 3,0. Come suggerisce il nome, viene eseguito sul server, il rendering delle modifiche apportate al documento client nel browser tramite la rete. Lato server Blazor offre un'esperienza client avanzata senza richiedere JavaScript sul lato client e senza richiedere carichi di pagina separati per ogni interazione tra le pagine client. Le modifiche apportate alla pagina caricata vengono richieste ed elaborate dal server e quindi inviate nuovamente al client tramite SignalR.

Il lato client Blazor verrà rilasciato in 2020 e eliminerà la necessità di eseguire il rendering delle modifiche nel server. Ma utilizzerà WebAssembly per eseguire il codice .NET all'interno del client. Il client può comunque effettuare chiamate API al server, se necessario, per richiedere i dati, ma tutto il comportamento sul lato client viene eseguito nel client tramite WebAssembly , che è già supportato da tutti i browser principali ed è semplicemente una libreria JavaScript.

> ### <a name="references--modern-web-applications"></a>Riferimenti: applicazioni Web moderne
>
> - **Introduzione ad ASP.NET Core**  
>   <https://docs.microsoft.com/aspnet/core/>
> - **Test e debug in ASP.NET Core**  
>   <https://docs.microsoft.com/aspnet/core/testing/>
> - **Blazor-Iniziare**  
>   <https://blazor.net/docs/get-started.html>

>[!div class="step-by-step"]
>[Precedente](index.md) 
> [Avanti](choose-between-traditional-web-and-single-page-apps.md)
