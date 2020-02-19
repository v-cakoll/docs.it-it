---
title: Scegliere tra app Web tradizionali e a pagina singola
description: Informazioni su come scegliere tra le app Web tradizionali e a pagina singola (SPAs) durante la compilazione di applicazioni Web.
author: ardalis
ms.author: wiwagn
ms.date: 12/04/2019
ms.openlocfilehash: d4ed76455001c1a0b8e2e2f1bb90ce8715dd0052
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77450108"
---
# <a name="choose-between-traditional-web-apps-and-single-page-apps-spas"></a>Scegliere tra app Web tradizionali e a pagina singola

> "Legge di Atwood: qualsiasi applicazione che può essere creata in JavaScript, finirà per essere creata in JavaScript".  
> _\- Jeff Atwood_

Attualmente esistono due approcci generali alla creazione di applicazioni Web: le applicazioni Web tradizionali che eseguono la maggior parte della logica dell'applicazione nel server e le applicazioni a pagina singola (SPA, Single Page Application) che eseguono la maggior parte della logica dell'interfaccia utente in un Web browser, comunicando con il server Web principalmente attraverso API Web. È anche possibile un approccio ibrido, il più semplice che ospita una o più sottoapplicazioni di tipo SPA avanzate all'interno di un'applicazione Web tradizionale più ampia.

Utilizzare le applicazioni Web tradizionali nei casi seguenti:

- I requisiti lato client dell'applicazione sono semplici o di sola lettura.

- L'applicazione deve funzionare in browser che non supportano JavaScript.

- Il team non ha dimestichezza con le tecniche di sviluppo di JavaScript o TypeScript.

Usare una SPA quando:

- L'applicazione deve esporre un'interfaccia utente avanzata con numerose funzionalità.

- Il team ha familiarità con lo sviluppo in JavaScript e/o TypeScript.

- L'applicazione deve già esporre un'API per altri client (interni o pubblici).

I framework delle applicazioni a pagina singola richiedono anche maggiori conoscenze a livello di architettura e sicurezza. Tali framework soggetti a maggior varianza rispetto alle applicazioni Web tradizionali, a causa di aggiornamenti frequenti e nuovi framework. La configurazione di processi di compilazione e distribuzione automatizzati e l'utilizzo di opzioni di distribuzione come i contenitori possono risultare più difficili con le applicazioni SPA rispetto alle app Web tradizionali.

I miglioramenti apportati all'esperienza utente grazie all'approccio SPA devono essere valutati in base a queste considerazioni.

## <a name="blazor"></a>Blazor

ASP.NET Core 3.0 introduce un nuovo modello per la creazione di un'interfaccia utente avanzata, interattiva e componibile, denominata Blazor. Blazer lato server consente agli sviluppatori di compilare l'interfaccia utente con Razor sul server e di recapitare il codice al browser e di eseguire il lato client usando [webassembly](https://webassembly.org/). Il lato server di Blazer è ora disponibile con ASP.NET Core 3,0 o versione successiva. Il lato client di Blazer dovrebbe essere disponibile in 2020.

Blazer offre una nuova, terza opzione da considerare quando si valuta se compilare un'applicazione Web puramente sottoposta a rendering del server o una SPA. Puoi creare comportamenti avanzati sul lato client di tipo SPA usando blazer, senza la necessità di uno sviluppo di JavaScript significativo. Le applicazioni Blazer possono chiamare le API per richiedere dati o eseguire operazioni sul lato server.

Provare a compilare l'applicazione Web con blazer nei casi seguenti:

- L'applicazione deve esporre un'interfaccia utente avanzata

- Il team ha più dimestichezza con lo sviluppo di .NET rispetto allo sviluppo di JavaScript o TypeScript

Per altre informazioni su Blazor, vedere [Get started with Blazor](https://blazor.net/docs/get-started.html) (Introduzione a Blazor).

## <a name="when-to-choose-traditional-web-apps"></a>Quando scegliere le app Web tradizionali

Di seguito vengono descritti in modo più dettagliato i motivi indicati in precedenza per cui scegliere applicazione Web tradizionali.

**L'applicazione ha requisiti lato client semplici o di sola lettura**

Molte applicazioni Web vengono usate principalmente in modalità di sola lettura dalla maggior parte degli utenti. Le applicazioni di sola lettura (o prevalentemente di sola lettura) tendono a essere molto più semplici rispetto a quelle che devono gestire e modificare grandi quantità di codice. Ad esempio un motore di ricerca può essere costituito da un singolo punto di ingresso con una casella di testo e da una seconda pagina per la visualizzazione dei risultati della ricerca. Qualsiasi utente anonimo può formulare richieste e la logica lato client necessaria è minima. In modo analogo, l'applicazione destinata al pubblico di un blog o di un sistema di gestione dei contenuti è in genere costituita soprattutto da contenuto, con funzionalità lato client limitate. Tali applicazioni sono facilmente compilate come applicazioni Web basate su server tradizionali, che eseguono la logica nel server Web ed eseguono il rendering del codice HTML da visualizzare nel browser. Il fatto che ogni pagina univoca del sito disponga di un proprio URL, al quale i motori di ricerca possono applicare un segnalibro e un indice (per impostazione predefinita, senza aggiungere questa operazione come funzionalità separata dell'applicazione) è un altro evidente vantaggio in questi scenari.

**L'applicazione deve funzionare in browser che non supportano JavaScript**

Le applicazioni Web che devono funzionare in browser con supporto limitato o senza supporto per JavaScript devono essere scritte con i flussi di lavoro tradizionali per le app Web (o almeno devono essere in grado di attivare il comportamento corrispondente se necessario). Per il funzionamento delle applicazioni a pagina singola, JavaScript deve essere disponibile sul lato client. In caso contrario, le applicazioni a pagina singola non rappresentano la scelta ottimale.

**Il team non ha dimestichezza con le tecniche di sviluppo di JavaScript o TypeScript**

Se il team non ha dimestichezza con JavaScript o TypeScript, ma ha familiarità con lo sviluppo di applicazioni Web lato server, probabilmente potrà produrre un'app Web tradizionale più rapidamente di un'applicazione a pagina singola. A meno che l'apprendimento della programmazione di applicazioni a pagina singola non sia un obiettivo o che sia necessaria l'esperienza utente offerta da un'applicazione a pagina singola, le app Web tradizionali sono una scelta più produttiva per i team che hanno già familiarità con lo sviluppo di queste app.

## <a name="when-to-choose-spas"></a>Quando scegliere le applicazioni a pagina singola

Di seguito è riportata una spiegazione più dettagliata dei casi in cui è opportuno scegliere l'approccio di sviluppo applicazione a pagina singola per l'app Web.

**L'applicazione deve esporre un'interfaccia utente avanzata con numerose funzionalità**

Le applicazioni a pagina singola supportano funzionalità lato client complete, che non richiedono di ricaricare la pagina quando gli utenti eseguono operazioni o passano da un'area all'altra dell'app. Le applicazioni a pagina singola vengono caricate rapidamente recuperando i dati in background e le singole azioni dell'utente risultano più rapide, perché pagine vengono ricaricate completamente solo in casi sporadici. Le applicazioni a pagina singola supportano gli aggiornamenti incrementali, salvando documenti o moduli completati solo parzialmente senza richiedere all'utente di fare clic su un pulsante per inoltrare un modulo. Le applicazioni a pagina singola supportano comportamenti lato client complessi, quali il trascinamento della selezione, con maggior facilità rispetto alle applicazioni tradizionali. Le applicazioni a pagina singola possono anche essere progettate per l'esecuzione in modalità non connessa mediante aggiornamento di un modello lato client che viene sincronizzato nel server quando viene ristabilita una connessione. Scegliere un'applicazione di tipo SPA se i requisiti dell'app includono funzionalità avanzate che vanno oltre la tipica offerta di moduli HTML.

Spesso, le Spa devono implementare funzionalità integrate in app Web tradizionali, ad esempio la visualizzazione di un URL significativo nella barra degli indirizzi che riflette l'operazione corrente (e consentire agli utenti di aggiungere segnalibri o collegamenti a questo URL per tornare a questo URL). Infine le applicazioni a pagina singola devono consentire agli utenti di usare i pulsanti Indietro e Avanti del browser con risultati prevedibili.

**Il team ha familiarità con lo sviluppo in JavaScript e/o TypeScript**

Per creare applicazioni a pagina singola è necessario avere dimestichezza con JavaScript e/o TypeScript e con le tecniche e le librerie della programmazione lato client. Il team deve essere in grado di creare codice JavaScript moderno tramite un framework per applicazioni a pagina singola come Angular.

> ### <a name="references--spa-frameworks"></a>Riferimenti: framework per applicazioni a pagina singola
>
> - **Angular**  
>   <https://angular.io>
> - 
>   **React** <https://reactjs.org/>
> - **Confronto tra diversi framework JavaScript**  
>   <https://jsreport.io/the-ultimate-guide-to-javascript-frameworks/>

**L'applicazione deve già esporre un'API per altri client (interni o pubblici)**

Se si supporta già un'API Web per l'uso con altri client, può risultare meno oneroso creare un'implementazione di tipo applicazione a pagina singola che si avvale di tale API anziché riprodurre la logica nel formato lato server. Le applicazioni a pagina singola usano sistematicamente le API Web per eseguire query e aggiornare i dati quando gli utenti interagiscono con l'applicazione.

## <a name="when-to-choose-blazor"></a>Quando scegliere il blazer

Di seguito è riportata una spiegazione più dettagliata di quando scegliere blazer per l'app Web.

**L'applicazione deve esporre un'interfaccia utente avanzata**

Come le Spa basate su JavaScript, le applicazioni Blazer possono supportare il comportamento di rich client senza ricaricamenti di pagina. Queste applicazioni sono più reattive agli utenti, recuperando solo i dati (o HTML) necessari per rispondere a una determinata interazione dell'utente. Progettato correttamente, le app Blazer lato server possono essere configurate per l'esecuzione come app Blazer sul lato client con modifiche minime quando questa funzionalità è supportata.

**Il team ha più dimestichezza con lo sviluppo di .NET rispetto allo sviluppo di JavaScript o TypeScript**

Molti sviluppatori sono più produttivi con .NET e Razor rispetto ai linguaggi lato client come JavaScript o TypeScript. Poiché il lato server dell'applicazione è già in fase di sviluppo con .NET, l'uso di Blazer garantisce a tutti gli sviluppatori .NET del team di comprendere e potenzialmente creare il comportamento del front-end dell'applicazione.

## <a name="decision-table"></a>Tabella decisionale

La tabella decisionale seguente riepiloga alcuni dei fattori di base da considerare quando si sceglie tra un'applicazione Web tradizionale, una SPA o un'app blazer.

| **Fattore**                                           | **App Web tradizionale** | **Applicazione a pagina singola** | **App Blazer**  |
| ---------------------------------------------------- | ----------------------- | --------------------------- | --------------- |
| Il team deve conoscere JavaScript o TypeScript | **Minimo**             | **Obbligatorio**                | **Minimo**     |
| Supporto dei browser senza script                   | **Supportato**           | **Non supportato**           | **Supportato**   |
| Comportamento minimo dell'applicazione lato client             | **Adeguato**         | **Eccessivo**                | **Validità**      |
| Esigenza di un'interfaccia utente dettagliata e complessa            | **Limitato**             | **Adeguato**             | **Adeguato** |

>[!div class="step-by-step"]
>[Precedente](modern-web-applications-characteristics.md)
>[Successivo](architectural-principles.md)
