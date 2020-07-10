---
title: Tecnologie Web sul lato client comuni
description: Progettare applicazioni Web moderne con ASP.NET Core e Azure | Tecnologie Web lato client comuni
author: ardalis
ms.author: wiwagn
no-loc:
- Blazor
ms.date: 12/04/2019
ms.openlocfilehash: e8ea035c491fad39d2932572255a19c7c1493418
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174354"
---
# <a name="common-client-side-web-technologies"></a>Tecnologie Web sul lato client comuni

> "I siti Web dovrebbero avere sempre un ottimo aspetto, dentro e fuori."  
> _- Paul Cookson_

Le applicazioni ASP.NET Core sono applicazioni Web che in genere si basano su tecnologie Web lato client quali HTML, CSS e JavaScript. Grazie alla separazione del contenuto della pagina (HTML) dal layout e dallo stile (CSS), nonché dal comportamento (tramite JavaScript), le app Web complesse possono sfruttare il principio di separazione delle competenze. Se queste competenze non sono interconnesse, le future modifiche alla struttura, alla progettazione o al comportamento possono essere apportate più facilmente.

Mentre le tecnologie HTML e CSS sono relativamente stabili, la tecnologia JavaScript, attraverso i framework e le utilità delle applicazioni che gli sviluppatori usano per compilare le applicazioni basate sul Web, sta evolvendo molto rapidamente. In questo capitolo vengono esaminati alcuni modi in cui JavaScript viene utilizzato dagli sviluppatori Web e viene fornita una panoramica di alto livello delle librerie lato client angolari e React.

> [!NOTE]
> Blazoroffre un'alternativa ai Framework JavaScript per la creazione di interfacce utente client avanzate e interattive. BlazorIl supporto lato client è ancora in anteprima, quindi per ora non rientra nell'ambito di questo capitolo.

## <a name="html"></a>HTML

HTML è il linguaggio di markup standard utilizzato per creare pagine Web e applicazioni Web. Gli elementi formano i blocchi predefiniti delle pagine, che rappresentano il testo formattato, le immagini, gli input dei moduli, e di altre strutture. Quando un browser invia una richiesta a un URL, ad esempio per recuperare una pagina o un'applicazione, il primo elemento restituito è un documento HTML. Questo documento HTML può fare riferimento a informazioni o includere informazioni aggiuntive sull'aspetto e sul layout sotto forma di CSS o sul comportamento sotto forma di JavaScript.

## <a name="css"></a>CSS

La tecnologia CSS (Cascading Style Sheets) viene usata per controllare l'aspetto e il layout degli elementi HTML. Gli stili CSS possono essere applicati direttamente a un elemento HTML, definiti separatamente nella stessa pagina oppure definiti in un file separato a cui la pagina fa riferimento. Gli stili si propagano in base a come vengono usati per selezionare un determinato elemento HTML. Ad esempio, è possibile che uno stile si applichi a un intero documento, ma che sia sostituito da uno stile applicato a un particolare elemento. Allo stesso modo, lo stile specifico di un elemento verrebbe sostituito da uno stile applicato a una classe CSS applicata all'elemento, che a sua volta verrebbe sottoposto a override da uno stile destinato a un'istanza specifica dell'elemento (tramite il relativo ID). Figura 6-1

![Regole di specificità CSS](./media/image6-1.png)

**Figura 6-1.** Regole di specificità CSS, in ordine.

È consigliabile mantenere gli stili nei rispettivi file dei fogli di stile separati e usare la sovrapposizione basata sulla selezione per implementare stili coerenti e riutilizzabili all'interno dell'applicazione. L'inserimento di regole di stile all'interno del codice HTML va evitato e l'applicazione di stili a singoli elementi specifici (piuttosto che a intere classi di elementi o a elementi ai quali è stata applicata una particolare classe CSS) deve essere l'eccezione, non la regola.

### <a name="css-preprocessors"></a>Preprocessori CSS

Nei fogli di stile CSS non è previsto il supporto per la logica condizionale, le variabili e altre funzionalità del linguaggio di programmazione. Pertanto, i fogli di stile di grandi dimensioni spesso includono un po' di ripetizioni, in quanto lo stesso colore, tipo di carattere o altra impostazione viene applicato a molte varianti diverse di elementi HTML e classi CSS. Grazie ai preprocessori CSS, i fogli di stile possono seguire il [principio DRY](https://deviq.com/don-t-repeat-yourself/) aggiungendo il supporto per le variabili e la logica.

I preprocessori CSS più diffusi sono Sass e LESS. Entrambi estendono CSS e sono compatibili con le versioni precedenti, vale a dire che un file CSS normale è un file Sass o LESS valido. Sass è basato su Ruby e LESS è basato su JavaScript. Entrambi vengono in genere eseguiti nell'ambito del processo di sviluppo locale. Entrambi gli strumenti da riga di comando sono disponibili, nonché il supporto incorporato in Visual Studio per eseguirli usando le attività Gulp o grugnito.

## <a name="javascript"></a>JavaScript

JavaScript è un linguaggio di programmazione dinamico e interpretato che è stato standardizzato nella specifica del linguaggio ECMAScript. È il linguaggio di programmazione del Web. Come CSS, JavaScript può essere definito come attributi all'interno di elementi HTML, come blocchi di script all'interno di una pagina o in file separati. Analogamente a quanto avviene per CSS, è consigliabile organizzare JavaScript in file distinti, tenendolo il più possibile separato dal codice HTML presente in singole pagine Web o visualizzazioni di applicazioni.

Quando si usa la tecnologia JavaScript in un'applicazione Web sarà in genere necessario eseguire alcune attività:

- Selezione di un elemento HTML e recupero e/o aggiornamento del relativo valore.

- Esecuzione di query su un'API Web per ottenere i dati.

- Invio di un comando a un'API Web (e risposta a un callback con il relativo risultato).

- Esecuzione della convalida.

È possibile eseguire tutte queste attività solo con JavaScript, ma esistono molte librerie che semplificano queste operazioni. Una delle prime di queste librerie e tra le più usate è jQuery che continua a essere una scelta piuttosto diffusa per semplificare queste attività nelle pagine Web. Per le applicazioni a pagina singola, jQuery non offre molte delle funzionalità desiderate offerte da Angular e React.

### <a name="legacy-web-apps-with-jquery"></a>App Web legacy con jQuery

Sebbene antico dagli standard di Framework JavaScript, jQuery continua a essere una libreria di uso comune per l'uso di HTML/CSS e la creazione di applicazioni che effettuano chiamate AJAX ad API Web. jQuery opera tuttavia al livello DOM (Document Object Model) del browser e per impostazione predefinita offre solo un modello imperativo, anziché dichiarativo.

Si supponga, ad esempio, che se il valore di una casella di testo è superiore a 10, un elemento della pagina debba essere reso visibile. In jQuery questa funzionalità viene in genere implementata scrivendo un gestore dell'evento con codice che ispeziona il valore della casella di testo e imposta la visibilità dell'elemento di destinazione in base a questo valore. Si tratta di un approccio imperativo basato sul codice. Per associare la visibilità dell'elemento al valore della casella di testo in modo dichiarativo, un altro framework potrebbe invece usare il data binding. Non sarebbe necessario scrivere alcun codice, ma sarebbe invece sufficiente decorare gli elementi interessati con attributi di data binding. Poiché i comportamenti lato client crescono più complessi, data binding approcci spesso generano soluzioni più semplici con meno codice e complessità condizionale.

### <a name="jquery-vs-a-spa-framework"></a>jQuery e un framework per applicazioni a pagina singola

| **Fattore** | **jQuery** | **Angular**|
|--------------------------|------------|-------------|
| Estrae il DOM | **Sì** | **Sì** |
| Supporto AJAX | **Sì** | **Sì** |
| Data binding dichiarativo | **No** | **Sì** |
| Routing in stile MVC | **No** | **Sì** |
| Creazione di modelli | **No** | **Sì** |
| Routing di collegamento diretto | **No** | **Sì** |

È possibile aggiungere la maggior parte delle funzionalità intrinsecamente mancanti in jQuery con l'aggiunta di altre librerie. Un framework per applicazioni a pagina singola come Angular offre tuttavia queste funzionalità in modo più integrato poiché è stato progettato tenendole presenti sin dall'inizio. Inoltre, jQuery è una libreria imperativa, vale a dire che è necessario chiamare le funzioni jQuery per eseguire qualsiasi operazione con jQuery. Gran parte del lavoro e le funzionalità offerte dai framework per applicazioni a pagina singola possono essere eseguiti in modo dichiarativo, senza la scrittura di codice.

Il data binding ne è un ottimo esempio. In jQuery, in genere è necessaria solo una riga di codice per ottenere il valore di un elemento DOM o per impostare il valore di un elemento. Tuttavia, è necessario scrivere questo codice ogni volta che è necessario modificare il valore dell'elemento e in alcuni casi ciò si verifica in più funzioni in una pagina. Un altro esempio comune è la visibilità di un elemento. In jQuery potrebbero essere presenti molte posizioni diverse in cui scrivere il codice per controllare se alcuni elementi fossero visibili. In ognuno di questi casi, quando si usa il data binding, non è necessario scrivere codice. È sufficiente associare il valore o la visibilità degli elementi in questione a un *ViewModel* nella pagina e le modifiche apportate a tale ViewModel verranno automaticamente riflesse negli elementi associati.

### <a name="angular-spas"></a>Applicazioni a pagina singola Angular

Angolare rimane uno dei framework JavaScript più diffusi del mondo. Dal momento che angolare 2, il team ha ricreato il Framework da zero (usando [typescript](https://www.typescriptlang.org/)) ed è stato rinominato dal nome originale di AngularJS a semplicemente angolare. Ora, molti anni fa, l'angolare riprogettato continua a essere un Framework affidabile per la creazione di applicazioni a singola pagina.

Le applicazioni Angular sono costituite da componenti. I componenti combinano i modelli HTML con oggetti speciali e controllano una parte della pagina. Di seguito viene illustrato un semplice componente estratto dalla documentazione di Angular:

```js
import { Component } from '@angular/core';

@Component({
    selector: 'my-app',
    template: `<h1>Hello {{name}}</h1>`
})

export class AppComponent { name = 'Angular'; }
```

I componenti vengono definiti usando la funzione di espressione Decorator @Component che acquisisce i metadati relativi al componente. La proprietà Selector identifica l'ID dell'elemento nella pagina in cui verrà visualizzato il componente. La proprietà "template" è un semplice modello HTML che include un segnaposto che corrisponde alla proprietà del nome del componente, definita nell'ultima riga.

Grazie all'uso di componenti e modelli, anziché di elementi DOM, le app Angular sono in grado di operare a un livello di astrazione superiore e con una minore quantità di codice rispetto alle app scritte usando solo JavaScript (anche noto come "vanilla JS") o con jQuery. Angular impone anche un certo ordine nel modo di organizzare i file di script sul lato client. Per convenzione, le app Angular usano una struttura di cartelle comune con i file di script di moduli e componenti inseriti in una cartella dell'app. Gli script di Angular relativi alla compilazione, alla distribuzione e ai test dell'app si trovano in genere in una cartella di livello superiore.

È possibile sviluppare app angolari usando un'interfaccia della riga di comando. Per iniziare a sviluppare con Angular in locale, presupponendo che git e npm siano già installati, basta semplicemente clonare un repository da GitHub ed eseguire `npm install` e `npm start`. Oltre a questo, angolare fornisce la propria interfaccia della riga di comando, che consente di creare progetti, aggiungere file e supportare attività di test, aggregazione e distribuzione. Questa cordialità dell'interfaccia della riga di comando rende l'angolare particolarmente compatibile con ASP.NET Core, che offre anche il supporto dell'interfaccia

Microsoft ha sviluppato un'applicazione di riferimento, [eShopOnContainers](https://aka.ms/MicroservicesArchitecture), che include l'implementazione di un'applicazione a pagina singola Angular. Questa app include moduli Angular per gestire il carrello acquisti del negozio online, caricare e visualizzare gli articoli dal catalogo e gestire la creazione degli ordini. È possibile visualizzare e scaricare l'applicazione di esempio da [GitHub](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebSPA).

### <a name="react"></a>React

A differenza di Angular, che offre un'implementazione dello schema MVC completo, React si concentra solo sulle visualizzazioni. Non si tratta di un framework, ma solo di una libreria. Per compilare un'applicazione a pagina singola è pertanto necessario usare librerie aggiuntive. Sono disponibili numerose librerie progettate per essere usate con React per produrre applicazioni a singola pagina avanzate.

Una delle funzionalità più importanti di React è l'uso di un DOM virtuale. Il DOM virtuale offre a React diversi vantaggi, tra cui le prestazioni (il DOM virtuale può ottimizzare le parti del DOM reale che è necessario aggiornare) e la testabilità (non è necessario che un browser testi React e le relative interazioni con il DOM virtuale).

Anche la modalità di interazione di React con la tecnologia HTML è insolita. Anziché prevedere una netta separazione tra il codice e il markup, ad esempio con riferimenti a JavaScript visualizzati negli attributi HTML, React aggiunge il codice HTML direttamente all'interno del codice JavaScript come JSX. JSX è una sintassi simile a HTML che consente la compilazione fino al codice JavaScript puro. Ad esempio:

```js
<ul>
{ authors.map(author =>
    <li key={author.id}>{author.name}</li>
)}
</ul>
```

Se si conosce già JavaScript, l'apprendimento di React dovrebbe essere semplice. La curva di apprendimento e la sintassi speciale da apprendere sono decisamente inferiori rispetto ad Angular o altre librerie molto diffuse.

Dal momento che React non è un framework completo, in genere è opportuno usare altre librerie per la gestione di operazioni quali il routing, le chiamate alle API Web e la gestione delle dipendenze. L'aspetto interessante è che per ognuna di queste operazioni è possibile scegliere la libreria migliore. Lo svantaggio sta nel dover prendere tutte queste decisioni e al termine verificare che ci sia una buona interazione tra tutte le librerie scelte. Per avere un buon punto di partenza è possibile usare uno starter kit come React Slingshot nel quale è stato predisposto un set di librerie compatibili insieme a React.

### <a name="vue"></a>Vue

Dalla Guida introduttiva, "Vue è un Framework progressivo per la creazione di interfacce utente. A differenza di altri Framework monolitici, VME è progettato per essere adottato in modo incrementale. La libreria principale è incentrata solo sul livello di visualizzazione ed è facile da prelevare e integrare con altre librerie o progetti esistenti. D'altra parte, Vue è perfettamente in grado di potenziare le sofisticate applicazioni a singola pagina quando vengono usate in combinazione con strumenti moderni e librerie di supporto. "

Per iniziare a usare VME, è sufficiente includere lo script all'interno di un file HTML:

```html
<!-- development version, includes helpful console warnings -->
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
```

Con il framework aggiunto, è quindi possibile eseguire il rendering in modo dichiarativo dei dati nel DOM usando la sintassi semplice per i modelli di VME:

```html
<div id="app">
  {{ message }}
</div>
```

e quindi aggiungere lo script seguente:

```js
var app = new Vue({
  el: '#app',
  data: {
    message: 'Hello Vue!'
  }
})
```

Questa operazione è sufficiente per eseguire il rendering di "Hello Vue!" nella pagina. Si noti, tuttavia, che VME non sta semplicemente eseguendo il rendering del messaggio in div una volta. Supporta l'associazione dati e gli aggiornamenti dinamici in modo tale che, se il valore di `message` cambia, il valore in `<div>` viene immediatamente aggiornato per rifletterlo.

Naturalmente, questa operazione consente di cancellare solo la superficie del supporto di Vue. Si è guadagnato una grande popolarità negli ultimi anni e ha una grande community. È disponibile un [elenco di componenti e librerie di supporto](https://github.com/vuejs/awesome-vue#redux) che funzionano con VME per estenderlo. Se si sta cercando di aggiungere un comportamento sul lato client all'applicazione Web o se si considera la creazione di una SPA completa, è opportuno analizzare il VME.

### <a name="choosing-a-spa-framework"></a>Scelta di un framework per applicazioni a pagina singola

Al momento di valutare il framework JavaScript migliore per supportare un'applicazione a pagina singola, tenere presente le considerazioni seguenti:

- Il team ha familiarità con il framework e le relative dipendenze (incluso TypeScript in alcuni casi)?

- Quanto è vincolante il framework e si è d'accordo con la modalità predefinita di esecuzione delle operazioni?

- Il framework (o una libreria complementare) include tutte le funzionalità necessarie per l'app?

- È ben documentato?

- La community del framework è sufficientemente attiva? Sono stati creati nuovi progetti?

- Quanto è attivo il team di base? I problemi vengono risolti e nuove versioni vengono rese disponibili regolarmente?

I framework JavaScript continuano a evolvere molto rapidamente. Usare le considerazioni elencate sopra per ridurre il rischio di scegliere un framework da cui in seguito ci si pentirà di dover dipendere. Se si è particolarmente contrari a rischiare, prendere in considerazione un framework che offra supporto commerciale e/o che sia sviluppato da una grande azienda.

> ### <a name="references--client-web-technologies"></a>Riferimenti - Tecnologie Web client
>
> - **HTML e CSS**  
> <https://www.w3.org/standards/webdesign/htmlcss>
> - **Sass rispetto a LESS**  
> <https://www.keycdn.com/blog/sass-vs-less/>
> - **Definizione di stili per app ASP.NET Core con LESS, Sass e Font Awesome**  
> <https://docs.microsoft.com/aspnet/core/client-side/less-sass-fa>
> - **Sviluppo sul lato client in ASP.NET Core**  
> <https://docs.microsoft.com/aspnet/core/client-side/>
> - **jQuery**  
> <https://jquery.com/>
> - **jQuery e AngularJS**  
> <https://www.airpair.com/angularjs/posts/jquery-angularjs-comparison-migration-walkthrough>
> - **Angular**  
> <https://angular.io/>
> - **React**  
> <https://reactjs.org/>
> - **Vue**  
> <https://vuejs.org/>
> - **Angolare e React rispetto a VME: quale Framework scegliere in 2020**
> <https://www.codeinwp.com/blog/angular-vs-vue-vs-react/>
> - **I principali framework JavaScript per lo sviluppo front-end in 2020**  
> <https://www.freecodecamp.org/news/complete-guide-for-front-end-developers-javascript-frameworks-2019/>

>[!div class="step-by-step"]
>[Precedente](common-web-application-architectures.md) 
> [Avanti](develop-asp-net-core-mvc-apps.md)
