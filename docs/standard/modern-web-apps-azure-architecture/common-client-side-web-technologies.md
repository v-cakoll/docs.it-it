---
title: Tecnologie di web sul lato client comuni
description: Architettura di moderne applicazioni Web con ASP.NET Core e Azure | Tecnologie di web sul lato client comuni
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e8e156552fd4aa733594c01845fb7ed1643b4aef
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="common-client-side-web-technologies"></a>Tecnologie di Web sul lato Client comuni

> "Siti Web necessario visualizzate correttamente dall'interno e out".  
> _-Paul Cookson_

## <a name="summary"></a>Riepilogo

Applicazioni ASP.NET sono applicazioni web e si basano in genere su tecnologie lato client web quali HTML, CSS e JavaScript. Separando il contenuto della pagina (HTML) da un layout e lo stile (CSS) e il relativo comportamento (tramite JavaScript), le applicazioni web complesse possono sfruttare il principio di separazione dei problemi. Le modifiche future alla struttura, struttura o un comportamento dell'applicazione possono essere eseguite più facilmente quando questi problemi non sono strettamente correlati tra loro.

Mentre l'HTML e CSS sono relativamente stabile, JavaScript, tramite il framework di applicazioni e gli sviluppatori di utilità utilizzano per compilare applicazioni basate sul web, è in continua evoluzione breakneck velocità. In questo capitolo verranno JavaScript viene utilizzato dagli sviluppatori web come parte dello sviluppo di applicazioni, come viene fornita una panoramica delle librerie sul lato client angolare e React in vari modi.

## <a name="html"></a>HTML

HTML (HyperText Markup Language) è il linguaggio di markup standard utilizzato per creare pagine web e applicazioni web. Gli elementi formano i blocchi predefiniti di pagine, che rappresenta il testo formattato, immagini, formano l'input e altre strutture. Quando un browser effettua una richiesta a un URL, se il recupero di una pagina o un'applicazione, ovvero in primo luogo restituito è un documento HTML. Questo documento HTML può fare riferimento o includere informazioni aggiuntive sull'aspetto e layout in formato, CSS o comportamento sotto forma di JavaScript.

## <a name="css"></a>CSS

CSS (Cascading Style Sheets) viene utilizzato per controllare l'aspetto e il layout degli elementi HTML. Stili CSS possono essere applicati direttamente a un elemento HTML, definiti separatamente nella stessa pagina, o definiti in un file separato e a cui fa riferimento la pagina. Cascade stili in base a come vengono utilizzati per selezionare un elemento HTML specificato. Uno stile, ad esempio, potrebbe applicarsi all'intero documento, ma potrebbe essere sottoposto a override da uno stile applicato a un particolare elemento. Analogamente, uno stile specifico elemento verrebbe eseguito l'override per uno stile applicato a una classe CSS applicata all'elemento, che a sua volta potrebbe essere sottoposto a override da un tipo di destinazione di un'istanza specifica di tale elemento (tramite il relativo id). Figura 6-1

**Figura 6-1.** Regole CSS specificità, nell'ordine.

![](./media/image6-1.png)

È consigliabile mantenere gli stili nei file di foglio di stile separato e utilizzare basati sulla selezione di propagazione per implementare gli stili riutilizzabili e coerenti all'interno dell'applicazione. Il posizionamento delle regole di stile HTML deve essere evitato e applicazione di stili ai singoli elementi specifici (invece che intere classi di elementi o gli elementi che hanno una determinata classe CSS applicata ad essi) deve essere l'eccezione, non la regola.

### <a name="css-preprocessors"></a>Preprocessori CSS

Fogli di stile CSS mancano del supporto per la logica condizionale, variabili e altre funzionalità del linguaggio di programmazione. Di conseguenza, fogli di stile grandi includono spesso un alto numero di ripetizioni, come lo stesso colore, carattere o altre impostazioni viene applicato a diversi tipi diversi di elementi HTML e le classi CSS. I preprocessori CSS consente i fogli di stile di seguire il [principio secca](http://deviq.com/don-t-repeat-yourself/) aggiungendo il supporto per le variabili e logica.

I preprocessori CSS più diffusi sono Sass e minore. Entrambi estendere CSS e sono compatibili con versioni precedenti, ovvero un file CSS semplice un Sass valido o meno file. Sass è basata su Ruby minore è basata su JavaScript ed entrambi in esecuzione in genere come parte del processo di sviluppo locale. Dispongono di supporto disponibile, nonché predefinito in Visual Studio per l'esecuzione di tali strumenti da riga di comando utilizzando l'attività Gulp o Grunt.

## <a name="javascript"></a>JavaScript

JavaScript è un linguaggio di programmazione dinamico, interpretato standard nella specifica del linguaggio ECMAScript. È il linguaggio di programmazione di web. Ad esempio CSS, JavaScript può essere definita come attributi all'interno degli elementi HTML, come blocchi di script all'interno di una pagina o in file distinti. Analogamente a CSS, è in genere consigliabile per organizzare JavaScript in file distinti, impedendone separati il più possibile il codice HTML a singole pagine web o di viste di applicazione.

Quando si utilizza l'applicazione web con JavaScript, esistono alcune attività che in genere è necessario eseguire:

-   Selezione di un elemento HTML e il recupero e/o aggiornare il relativo valore

-   Esecuzione di query su un'API Web per i dati

-   Inviare un comando a un'API Web (e risponde a un callback con il relativo risultato)

-   Esegue la convalida

È possibile eseguire tutte le attività con JavaScript da solo, ma esistono molte librerie per semplificare queste operazioni. È il primo e più efficace di queste librerie di jQuery, che continua a essere una scelta popolare per semplificare queste operazioni sulle pagine web. Per applicazioni a pagina singola (stabilimenti termali), jQuery non fornisce molte delle funzionalità che offrono angolare e React desiderata.

### <a name="legacy-web-apps-with-jquery"></a>App Web legacy con jQuery

Sebbene la dagli standard framework JavaScript, jQuery continua a essere una libreria comunemente utilizzata per l'utilizzo con HTML/CSS e compilazione di applicazioni che effettuano chiamate AJAX ad API web. Tuttavia, jQuery opera a livello del modello a oggetti documento (DOM) del browser e per impostazione predefinita offre solo un modello imperativo, anziché dichiarativo.

Si supponga, ad esempio, che se il valore della casella di testo superiore a 10, un elemento della pagina deve essere reso visibile. Nel jQuery, questo potrebbe essere in genere implementato scrivendo un gestore eventi con il codice che è necessario esaminare il valore della casella di testo e impostare la visibilità dell'elemento di destinazione in base al valore. Questo è un approccio imperativo, basato sul codice. Per associare la visibilità dell'elemento al valore della casella di testo in modo dichiarativo un altro framework potrebbe utilizzare l'associazione dati. Non richiedono la scrittura di codice, ma invece richiede solo la decorazione di elementi in questione con gli attributi di associazione dati. Comportamenti lato client con l'aumentare più complessi, associazione dati si avvicina spesso risultati nelle soluzioni più semplice con meno codice e complessità condizionale.

### <a name="jquery-vs-a-spa-framework"></a>Visual Studio jQuery un Framework di SPA

| **Fattore** | **jQuery** | **Angular**|
|--------------------------|------------|-------------|
| Estrae il DOM | **Sì** | **Sì** |
| Supporto AJAX | **Sì** | **Sì** |
| Associazione dati dichiarativa | **No** | **Sì** |
| Il Routing MVC stile | **No** | **Sì** |
| Creazione del modello | **No** | **Sì** |
| Routing con collegamento diretto | **No** | **Sì** |

È possibile aggiungere la maggior parte delle funzionalità di per sé non dispone di jQuery con l'aggiunta di altre librerie. Tuttavia, un framework SPA come angolare fornisce queste funzionalità in modo più integrata, poiché è stato progettato con tutti gli elementi presenti dall'inizio. Inoltre, jQuery è una libreria molto imperativa, pertanto è necessario chiamare le funzioni di jQuery per intervenire jQuery. Gran parte del lavoro e delle funzionalità che forniscono il Framework SPA può essere eseguita in modo dichiarativo, senza richiedere alcun codice effettivo da scrivere.

Associazione dati è un ottimo esempio di questo oggetto. In jQuery, in genere richiede soltanto una riga di codice per ottenere il valore di un elemento DOM o impostare il valore dell'elemento. Tuttavia, è necessario scrivere questo codice ogni volta che si desidera modificare il valore dell'elemento e a volte questa situazione si verifica in più funzioni in una pagina. Un altro esempio comune è visibilità dell'elemento. JQuery, potrebbe essere più posizioni differenti, in cui è necessario scrivere codice per controllare se alcuni elementi sono visibili. In ognuno di questi casi, quando si utilizza l'associazione dati, non il codice deve essere scritto. È semplicemente necessario associare il valore o la visibilità degli elementi in questione per un *viewmodel* sulla pagina e a quello viewmodel verrà esteso automaticamente gli elementi associati.

### <a name="angular-spas"></a>Stabilimenti termali Angular

AngularJS è diventato rapidamente uno dei framework JavaScript più diffusi al mondo. Con Angular 2, il team ricompilato il framework di base backup (utilizzando [TypeScript](https://www.typescriptlang.org/)) e re-branding di AngularJS per semplicemente angolare. Attualmente in versione 4, angolare continua a essere un framework potente per la compilazione di applicazioni a pagina singola.

Angolare applicazioni sono costituite da componenti. Componenti combinano modelli HTML con oggetti speciale e controllano una parte della pagina. Un componente semplice da documenti di angolare è illustrato di seguito:

```js
import { Component } from '@angular/core';

@Component({
    selector: 'my-app',
    template: `<h1>Hello {{name}}</h1>`
})

export class AppComponent { name = 'Angular'; }
```

I componenti vengono definiti utilizzando il @Component decorator funzione che accetta i metadati relativi al componente. La proprietà del selettore identifica l'id dell'elemento nella pagina in cui verrà visualizzato questo componente. La proprietà di modello è un semplice modello HTML che include un segnaposto che corrisponde alla proprietà name del componente, definita nell'ultima riga.

Quando si lavora con i componenti e i modelli, anziché gli elementi DOM, App angolare possono operare a un livello superiore di astrazione e con meno codice globale le applicazioni scritte utilizzando solo JavaScript (detto anche "vaniglia JS") o con jQuery. Angolare impone inoltre un ordine nella modalità di organizzazione dei file script sul lato client. Per convenzione, le app angolare usano una struttura di cartelle comune, con i file di script di modulo e il componente che si trova in una cartella di app. Script angolare interessati alla compilazione, distribuzione e test dell'app in genere si trovano in una cartella di livello superiore.

Angolare consente inoltre di elevato utilizzo di strumenti di interfaccia della riga di comando (CLI). Introduzione allo sviluppo angolare in locale (presupponendo che si dispone già di git e npm installato) è costituito da semplicemente la clonazione di un repository da GitHub e in esecuzione \`installare npm\` e \`npm inizio\`. Oltre a ciò, angolare viene fornito il proprio strumento CLI che è possibile creare progetti, aggiungere file e semplificare le attività di test, aggregazione e la distribuzione. CLI tooling altrettanto rende particolarmente compatibile con ASP.NET Core, che offre inoltre supporto CLI ottimale angolare.

Microsoft ha sviluppato un'applicazione di riferimento, [eShopOnContainers](http://aka.ms/MicroservicesArchitecture), che include un'implementazione di SPA angolare. Questa app include i moduli Angular per gestire l'archivio online market basket, carico e la visualizzazione di elementi nel catalogo e la gestione della creazione dell'ordine. È possibile visualizzare e scaricare l'applicazione di esempio da [GitHub](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebSPA).

### <a name="react"></a>rispondere

A differenza di angolare, che offre una procedura completa di implementazione del pattern Model-View-Controller, React riguarda solo le visualizzazioni. Non è un framework di una libreria, quindi per compilare un SPA è necessario utilizzare librerie aggiuntive.

Una delle funzionalità più importanti del React consiste nell'utilizzo di un modello DOM di virtuale. Il DOM virtuale fornisce React con diversi vantaggi, inclusi la testabilità (non è necessario disporre di un browser per testare React e le relative interazioni con il DOM virtuale) e le prestazioni (DOM virtuale può ottimizzare le parti del DOM effettivo dovranno essere aggiornati).

React anche è insolito in come funziona con HTML. Invece di una separazione tra il codice e markup (con riferimenti a JavaScript visualizzati negli attributi HTML, ad esempio), strict reagire aggiunge HTML direttamente all'interno del codice JavaScript come JSX. JSX è una sintassi simile a HTML che è possibile compilare fino a JavaScript pure. Ad esempio:

```js
<ul>
{ authors.map(author =>
    <li key={author.id}>{author.name}</li>
)}
</ul>
```

Se si conosce già JavaScript, l'apprendimento React dovrebbe essere semplice. Non è quasi quantità curva di apprendimento o una sintassi speciale coinvolti come angolare o in altre librerie comuni.

Dal momento React non è un framework completo, in genere è opportuno utilizzare altre librerie per la gestione di operazioni come il routing, le chiamate API e la gestione delle dipendenze web. L'aspetto interessante è, per ognuno di essi, è possibile selezionare la libreria migliore, ma lo svantaggio è che è necessario effettuare tutte queste decisioni e verificare tutte le librerie scelte di funzionino bene insieme al termine. Se si desidera un buon punto di partenza, è possibile utilizzare uno starter kit come reagire Slingshot, quale un set di librerie compatibili con React preconfezionati.

### <a name="choosing-a-spa-framework"></a>Scelta di un Framework SPA

Quando si considera il framework JavaScript risulti più appropriato per supportare l'autenticazione SPA, tenere presenti le considerazioni seguenti:

-   È il team ha familiarità con il framework e le relative dipendenze (TypeScript inclusi in alcuni casi)?

-   Come anteprime è il framework e accettano con la modalità predefinita di eseguire le operazioni?

-   È (o una libreria complementare) include tutte le funzioni che necessarie per l'app?

-   È ben documentati?

-   Attiva la modalità è la community? La creazione di nuovi progetti vengono compilati con esso?

-   Attivo la modalità è il team principale? Vengono forniti regolarmente i problemi da risolvere e la nuova versione?

I framework JavaScript di continuano a sviluppare con velocità breakneck. Usare le considerazioni riportate sopra per ridurre i rischi della scelta di un framework che si sarà in seguito cambia idea viene dipende. Se si rischiano particolarmente rischio, prendere in considerazione un framework che offre un supporto esterno e/o è stato sviluppato da una grande impresa.

> ### <a name="references--client-web-technologies"></a>Riferimenti: tecnologie Web Client
> - **HTML e CSS**  
> <https://www.w3.org/standards/webdesign/htmlcss>
> - **Visual Studio sass. LESS**  
> <https://www.keycdn.com/blog/sass-vs-less/>
> - **Stile carattere straordinario App ASP.NET Core con meno e Sass**  
> <https://docs.microsoft.com/aspnet/core/client-side/less-sass-fa>
> - **Sviluppo sul lato client in ASP.NET Core**  
> <https://docs.microsoft.com/aspnet/core/client-side/>
> - **jQuery**  
> <https://jquery.com/>
> - **jQuery vs AngularJS**  
> <https://www.airpair.com/angularjs/posts/jquery-angularjs-comparison-migration-walkthrough>
> - **Angular**  
> <https://angular.io/>
> - rispondere  
> <https://facebook.github.io/react/>
> - **Slingshot React**  
> <https://github.com/coryhouse/react-slingshot>
> - **Visual Studio React angolare confronto 2**  
> <https://www.codementor.io/codementorteam/react-vs-angular-2-comparison-beginners-guide-lvz5710ha>
> - **5 migliore i framework JavaScript di 2017**  
> <https://hackernoon.com/5-best-javascript-frameworks-in-2017-7a63b3870282>

>[!div class="step-by-step"]
[Precedente] (comuni-web-applicazione-architectures.md) [Avanti] (develop-asp-net-core-mvc-apps.md)
