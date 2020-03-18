---
title: Tecnologie Web comuni sul lato client
description: Progetta applicazioni Web moderne con ASP.NET Core e Azure . Tecnologie Web comuni sul lato client
author: ardalis
ms.author: wiwagn
ms.date: 12/04/2019
ms.openlocfilehash: 2809c8539b42e8e2250039dceed1389b3cbdcd8a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77449374"
---
# <a name="common-client-side-web-technologies"></a>Tecnologie Web comuni sul lato client

> "I siti Web dovrebbero avere sempre un ottimo aspetto, dentro e fuori."  
> _- Paul Cookson_

Le applicazioni ASP.NET Core sono applicazioni Web che in genere si basano su tecnologie Web lato client quali HTML, CSS e JavaScript. Grazie alla separazione del contenuto della pagina (HTML) dal layout e dallo stile (CSS), nonché dal comportamento (tramite JavaScript), le app Web complesse possono sfruttare il principio di separazione delle competenze. Se queste competenze non sono interconnesse, le future modifiche alla struttura, alla progettazione o al comportamento possono essere apportate più facilmente.

Mentre le tecnologie HTML e CSS sono relativamente stabili, la tecnologia JavaScript, attraverso i framework e le utilità delle applicazioni che gli sviluppatori usano per compilare le applicazioni basate sul Web, sta evolvendo molto rapidamente. Questo capitolo illustra alcuni modi in cui JavaScript viene utilizzato dagli sviluppatori Web e fornisce una panoramica generale delle librerie lato client Angular e React.

> [!NOTE]
> Blazor fornisce un'alternativa ai framework JavaScript per la creazione di interfacce utente client interattive e avanzate. Il supporto Blazor lato client è ancora in anteprima, quindi per ora è fuori ambito per questo capitolo.

## <a name="html"></a>HTML

HTML è il linguaggio di markup standard utilizzato per creare pagine web e applicazioni web. Gli elementi formano i blocchi predefiniti delle pagine, che rappresentano il testo formattato, le immagini, gli input dei moduli, e di altre strutture. Quando un browser invia una richiesta a un URL, ad esempio per recuperare una pagina o un'applicazione, il primo elemento restituito è un documento HTML. Questo documento HTML può fare riferimento a informazioni o includere informazioni aggiuntive sull'aspetto e sul layout sotto forma di CSS o sul comportamento sotto forma di JavaScript.

## <a name="css"></a>CSS

La tecnologia CSS (Cascading Style Sheets) viene usata per controllare l'aspetto e il layout degli elementi HTML. Gli stili CSS possono essere applicati direttamente a un elemento HTML, definiti separatamente nella stessa pagina oppure definiti in un file separato a cui la pagina fa riferimento. Gli stili si propagano in base a come vengono usati per selezionare un determinato elemento HTML. Ad esempio, è possibile che uno stile si applichi a un intero documento, ma che sia sostituito da uno stile applicato a un particolare elemento. Analogamente, uno stile specifico dell'elemento verrebbe sottoposto a override da uno stile applicato a una classe CSS applicata all'elemento, che a sua volta verrebbe sostituito da uno stile destinato a un'istanza specifica di tale elemento (tramite il relativo ID). Figura 6-1

![Regole di specificità CSS](./media/image6-1.png)

**Figura 6-1.** Regole di specificità CSS, in ordine.

È consigliabile mantenere gli stili nei rispettivi file dei fogli di stile separati e usare la sovrapposizione basata sulla selezione per implementare stili coerenti e riutilizzabili all'interno dell'applicazione. L'inserimento di regole di stile all'interno del codice HTML va evitato e l'applicazione di stili a singoli elementi specifici (piuttosto che a intere classi di elementi o a elementi ai quali è stata applicata una particolare classe CSS) deve essere l'eccezione, non la regola.

### <a name="css-preprocessors"></a>Preprocessori CSS

Nei fogli di stile CSS non è previsto il supporto per la logica condizionale, le variabili e altre funzionalità del linguaggio di programmazione. Pertanto, i fogli di stile di grandi dimensioni spesso includono un po 'di ripetizione, poiché lo stesso colore, carattere o altra impostazione viene applicata a molte varianti diverse di elementi HTML e classi CSS. Grazie ai preprocessori CSS, i fogli di stile possono seguire il [principio DRY](https://deviq.com/don-t-repeat-yourself/) aggiungendo il supporto per le variabili e la logica.

I preprocessori CSS più diffusi sono Sass e LESS. Entrambi estendono CSS e sono compatibili con le versioni precedenti, vale a dire che un file CSS normale è un file Sass o LESS valido. Sass è basato su Ruby e LESS è basato su JavaScript. Entrambi vengono in genere eseguiti nell'ambito del processo di sviluppo locale. Entrambi dispongono di strumenti da riga di comando disponibili, nonché il supporto incorporato in Visual Studio per l'esecuzione di essi tramite attività Gulp o Grunt.

## <a name="javascript"></a>JavaScript

JavaScript è un linguaggio di programmazione dinamico e interpretato che è stato standardizzato nella specifica del linguaggio ECMAScript. È il linguaggio di programmazione del Web. Come CSS, JavaScript può essere definito come attributi all'interno di elementi HTML, come blocchi di script all'interno di una pagina o in file separati. Proprio come CSS, si consiglia di organizzare JavaScript in file separati, mantenendolo separato il più possibile dal codice HTML trovato su singole pagine web o visualizzazioni dell'applicazione.

Quando si usa la tecnologia JavaScript in un'applicazione Web sarà in genere necessario eseguire alcune attività:

- Selezione di un elemento HTML e recupero e/o aggiornamento del relativo valore.

- Esecuzione di query su un'API Web per ottenere i dati.

- Invio di un comando a un'API Web (e risposta a un callback con il relativo risultato).

- Esecuzione della convalida.

È possibile eseguire tutte queste attività solo con JavaScript, ma esistono molte librerie che semplificano queste operazioni. Una delle prime di queste librerie e tra le più usate è jQuery che continua a essere una scelta piuttosto diffusa per semplificare queste attività nelle pagine Web. Per le applicazioni a pagina singola, jQuery non offre molte delle funzionalità desiderate offerte da Angular e React.

### <a name="legacy-web-apps-with-jquery"></a>App Web legacy con jQuery

Anche se antica per gli standard del framework JavaScript, jQuery continua ad essere una libreria di uso comune per l'utilizzo di HTML/CSS e la creazione di applicazioni che effettuano chiamate AJAX alle API Web. jQuery opera tuttavia al livello DOM (Document Object Model) del browser e per impostazione predefinita offre solo un modello imperativo, anziché dichiarativo.

Si supponga, ad esempio, che se il valore di una casella di testo è superiore a 10, un elemento della pagina debba essere reso visibile. In jQuery questa funzionalità viene in genere implementata scrivendo un gestore dell'evento con codice che ispeziona il valore della casella di testo e imposta la visibilità dell'elemento di destinazione in base a questo valore. Si tratta di un approccio imperativo basato sul codice. Per associare la visibilità dell'elemento al valore della casella di testo in modo dichiarativo, un altro framework potrebbe invece usare il data binding. Non sarebbe necessario scrivere alcun codice, ma sarebbe invece sufficiente decorare gli elementi interessati con attributi di data binding. Man mano che i comportamenti lato client diventano più complessi, gli approcci di associazione dati spesso generano soluzioni più semplici con meno codice e complessità condizionale.

### <a name="jquery-vs-a-spa-framework"></a>jQuery e un framework per applicazioni a pagina singola

| **Fattore** | **Jquery** | **Angular**|
|--------------------------|------------|-------------|
| Estrae il DOM | **Sì** | **Sì** |
| Supporto AJAX | **Sì** | **Sì** |
| Data binding dichiarativo | **No** | **Sì** |
| Routing in stile MVC | **No** | **Sì** |
| Modelli | **No** | **Sì** |
| Routing di collegamento diretto | **No** | **Sì** |

È possibile aggiungere la maggior parte delle funzionalità intrinsecamente mancanti in jQuery con l'aggiunta di altre librerie. Un framework per applicazioni a pagina singola come Angular offre tuttavia queste funzionalità in modo più integrato poiché è stato progettato tenendole presenti sin dall'inizio. Inoltre, jQuery è una libreria imperativa, il che significa che è necessario chiamare le funzioni jQuery per eseguire qualsiasi operazione con jQuery. Gran parte del lavoro e le funzionalità offerte dai framework per applicazioni a pagina singola possono essere eseguiti in modo dichiarativo, senza la scrittura di codice.

Il data binding ne è un ottimo esempio. In jQuery, in genere richiede solo una riga di codice per ottenere il valore di un elemento DOM o per impostare il valore di un elemento. Tuttavia, è necessario scrivere questo codice ogni volta che è necessario modificare il valore dell'elemento e talvolta ciò si verifica in più funzioni in una pagina. Un altro esempio comune è la visibilità di un elemento. In jQuery, ci potrebbero essere molte posizioni diverse in cui è possibile scrivere codice per controllare se alcuni elementi erano visibili. In ognuno di questi casi, quando si usa il data binding, non è necessario scrivere codice. È sufficiente associare il valore o la visibilità degli elementi in questione a un modello di *visualizzazione* nella pagina e le modifiche apportate a tale modello di visualizzazione si rifletterebbero automaticamente negli elementi associati.

### <a name="angular-spas"></a>Applicazioni a pagina singola Angular

Angolare rimane uno dei framework JavaScript più popolari al mondo. A partire da Angular 2, il team ha ricostruito il framework da zero (utilizzando [TypeScript](https://www.typescriptlang.org/)) e rinominato dal nome AngularJS originale in modo semplicemente angolare. Ora diversi anni, il riprogettato Angular continua ad essere un solido quadro per la creazione di applicazioni a pagina singola.

Le applicazioni Angular sono costituite da componenti. I componenti combinano i modelli HTML con oggetti speciali e controllano una parte della pagina. Di seguito viene illustrato un semplice componente estratto dalla documentazione di Angular:

```js
import { Component } from '@angular/core';

@Component({
    selector: 'my-app',
    template: `<h1>Hello {{name}}</h1>`
})

export class AppComponent { name = 'Angular'; }
```

I componenti vengono definiti usando la funzione di espressione Decorator @Component che acquisisce i metadati relativi al componente. La proprietà selector identifica l'ID dell'elemento nella pagina in cui verrà visualizzato il componente. La proprietà "template" è un semplice modello HTML che include un segnaposto che corrisponde alla proprietà del nome del componente, definita nell'ultima riga.

Grazie all'uso di componenti e modelli, anziché di elementi DOM, le app Angular sono in grado di operare a un livello di astrazione superiore e con una minore quantità di codice rispetto alle app scritte usando solo JavaScript (anche noto come "vanilla JS") o con jQuery. Angular impone anche un certo ordine nel modo di organizzare i file di script sul lato client. Per convenzione, le app Angular usano una struttura di cartelle comune con i file di script di moduli e componenti inseriti in una cartella dell'app. Gli script di Angular relativi alla compilazione, alla distribuzione e ai test dell'app si trovano in genere in una cartella di livello superiore.

È possibile sviluppare app angolari usando una riga di comando. Per iniziare a sviluppare con Angular in locale, presupponendo che git e npm siano già installati, basta semplicemente clonare un repository da GitHub ed eseguire `npm install` e `npm start`. Oltre a questo, Angular fornisce la propria CLI, che può creare progetti, aggiungere file e assistere con attività di test, raggruppamento e distribuzione. Questa compatibilità CLI rende Angular particolarmente compatibile con ASP.NET Core, che dispone anche di grande supporto CLI.

Microsoft ha sviluppato un'applicazione di riferimento, [eShopOnContainers](https://aka.ms/MicroservicesArchitecture), che include l'implementazione di un'applicazione a pagina singola Angular. Questa app include moduli Angular per gestire il carrello acquisti del negozio online, caricare e visualizzare gli articoli dal catalogo e gestire la creazione degli ordini. È possibile visualizzare e scaricare l'applicazione di esempio da [GitHub](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebSPA).

### <a name="react"></a>React

A differenza di Angular, che offre un'implementazione dello schema MVC completo, React si concentra solo sulle visualizzazioni. Non si tratta di un framework, ma solo di una libreria. Per compilare un'applicazione a pagina singola è pertanto necessario usare librerie aggiuntive. Esistono diverse librerie progettate per essere utilizzate con React per produrre applicazioni avanzate a pagina singola.

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

Dalla sua guida introduttiva, "Vue è un framework progressivo per la creazione di interfacce utente. A differenza di altri quadri monolitici, Vue è progettato da zero per essere adottabile in modo incrementale. La libreria principale è focalizzata solo sul livello di visualizzazione ed è facile da raccogliere e integrare con altre librerie o progetti esistenti. D'altra parte, Vue è perfettamente in grado di alimentare sofisticate applicazioni a pagina singola se utilizzato in combinazione con strumenti moderni e librerie di supporto."

Per iniziare con Vue è sufficiente includere il suo script all'interno di un file HTML:

```html
<!-- development version, includes helpful console warnings -->
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
```

Con il framework aggiunto, è quindi possibile eseguire il rendering dichiarativo dei dati nel DOM usando la sintassi dei modelli semplice di Vue:

```html
<div id="app">
  {{ message }}
</div>
```

e quindi aggiungendo il seguente script:

```js
var app = new Vue({
  el: '#app',
  data: {
    message: 'Hello Vue!'
  }
})
```

Questo è sufficiente per rendere "Ciao Vue!" nella pagina. Si noti, tuttavia, che Vue non sta semplicemente eseguendo il rendering del messaggio al div una volta. Supporta l'associazione dati e gli aggiornamenti `message` dinamici in `<div>` modo che se il valore delle modifiche, il valore in viene immediatamente aggiornato per rifletterlo.

Naturalmente, questo graffia solo la superficie di ciò di cui Vue è capace. Ha guadagnato una grande popolarità negli ultimi anni e ha una grande comunità. C'è un [enorme e crescente elenco di componenti di supporto e librerie](https://github.com/vuejs/awesome-vue#redux) che lavorano con Vue anche per estenderlo. Se stai cercando di aggiungere un comportamento lato client alla tua applicazione web o stai valutando la creazione di una SPA completa, Vue vale la pena indagare.

### <a name="choosing-a-spa-framework"></a>Scelta di un framework per applicazioni a pagina singola

Al momento di valutare il framework JavaScript migliore per supportare un'applicazione a pagina singola, tenere presente le considerazioni seguenti:

- Il team ha familiarità con il framework e le relative dipendenze (incluso TypeScript in alcuni casi)?

- Quanto è vincolante il framework e si è d'accordo con la modalità predefinita di esecuzione delle operazioni?

- Il framework (o una libreria complementare) include tutte le funzionalità necessarie per l'app?

- È ben documentato?

- La community del framework è sufficientemente attiva? Vengono costruiti nuovi progetti?

- Quanto è attivo il team di base? I problemi vengono risolti e nuove versioni vengono rese disponibili regolarmente?

I framework JavaScript continuano a evolvere molto rapidamente. Usare le considerazioni elencate sopra per ridurre il rischio di scegliere un framework da cui in seguito ci si pentirà di dover dipendere. Se si è particolarmente contrari a rischiare, prendere in considerazione un framework che offra supporto commerciale e/o che sia sviluppato da una grande azienda.

> ### <a name="references--client-web-technologies"></a>Riferimenti - Tecnologie Web client
>
> - **HTML e CSS**  
> <https://www.w3.org/standards/webdesign/htmlcss>
> - **Sass vs. LESS**  
> <https://www.keycdn.com/blog/sass-vs-less/>
> - **Definizione di stili per app ASP.NET Core con LESS, Sass e Font Awesome**  
> <https://docs.microsoft.com/aspnet/core/client-side/less-sass-fa>
> - **Sviluppo lato client nel ASP.NET CoreClient-Side Development in ASP.NET Core**  
> <https://docs.microsoft.com/aspnet/core/client-side/>
> - **Jquery**  
> <https://jquery.com/>
> - **jQuery e AngularJS**  
> <https://www.airpair.com/angularjs/posts/jquery-angularjs-comparison-migration-walkthrough>
> - **Angular**  
> <https://angular.io/>
> - **React**  
> <https://reactjs.org/>
> - **Vue**  
> <https://vuejs.org/>
> - **Angolare vs React vs Vue: quale framework scegliere nel 2020**
> <https://www.codeinwp.com/blog/angular-vs-vue-vs-react/>
> - **I migliori framework JavaScript per lo sviluppo front-end nel 2020**  
> <https://www.freecodecamp.org/news/complete-guide-for-front-end-developers-javascript-frameworks-2019/>

>[!div class="step-by-step"]
>[Successivo](common-web-application-architectures.md)
>[precedente](develop-asp-net-core-mvc-apps.md)
