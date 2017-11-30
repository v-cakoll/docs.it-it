---
title: Principi architetturali
description: Architettura di moderne applicazioni Web con ASP.NET Core e Azure | Principi architetturali
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: 20524c8aa0e64fd40a1a4a6811063557f74074d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
#<a name="architectural-principles"></a>Principi architetturali

> "Se generatori di edifici i programmatori modo scritto programmi quindi il primo woodpecker che è arrivata sarebbe destroy civiltà."  
> _\-Ideatore è Gerald Weinberg_

## <a name="summary"></a>Riepilogo

È necessario progettare e progettare soluzioni di software con manutenibilità presente. I principi indicati in questa sezione possono semplificare verso alcune decisioni architetturali che si tradurrà in applicazioni pulite e gestibile. In genere, tali principi fornirà le istruzioni per la creazione di applicazioni da componenti discreti che non sono strettamente collegate ad altre parti dell'applicazione, ma piuttosto di comunicare tramite interfacce esplicite o sistemi di messaggistica.

## <a name="common-design-principles"></a>Principi di progettazione comuni

### <a name="separation-of-concerns"></a>Separazione dei compiti

È un principio durante lo sviluppo di **la separazione di problemi**. Questo principio asserisce che software deve essere separato in base al tipo di lavoro che eseguita. Ad esempio, si consideri un'applicazione che include la logica per l'identificazione di elementi importanti da visualizzare all'utente e che formatta tali elementi in un modo specifico per renderli più evidenti. Il comportamento è responsabile per la scelta di quali elementi di formato devono essere mantenuti separati dal comportamento responsabile per la formattazione degli elementi, poiché si tratta di separare le problematiche che riguardano solo coincidenza uno a altro.

L'architettura applicazioni possono essere compilate in modo logico per seguire questo principio separando il comportamento di business principale da logica dell'interfaccia utente e infrastruttura. In teoria, le regole di business e logica deve trovarsi in un progetto separato, non deve dipendere da altri progetti nell'applicazione. Ciò garantisce che il modello di business è facile da testare e possono evolvere senza essere strettamente collegati ai dettagli di implementazione di basso livello. La separazione dei compiti è un fattore chiave dietro l'utilizzo dei livelli nelle architetture di applicazioni.

### <a name="encapsulation"></a>Incapsulamento

Parti diverse di un'applicazione devono utilizzare **incapsulamento** per isolare i loro da altre parti dell'applicazione. Livelli e i componenti dell'applicazione devono essere in grado di regolare riguarda l'implementazione interna senza interrompere i collaboratori fino a quando non vengono violati contratti esterni. Utilizzo appropriato di incapsulamento consente di ottenere regime di controllo e modularità per progettazioni di applicazioni, poiché gli oggetti e i pacchetti possono essere sostituiti con implementazioni alternative, purché la stessa interfaccia viene mantenuta.

Nelle classi, incapsulamento avviene tramite la limitazione all'esterno di accesso allo stato interno della classe. Se un attore esterno desidera modificare lo stato dell'oggetto, deve farlo tramite una funzione ben definito (o setter di proprietà), anziché avere accesso diretto per lo stato privato dell'oggetto. Analogamente, i componenti dell'applicazione e le applicazioni stesse devono esporre interfacce ben definite per i collaboratori di utilizzare, invece di lasciare che lo stato su cui è possibile modificare direttamente. In questo modo la progettazione dell'applicazione interna a evolversi nel tempo senza doversi preoccupare che in tal modo verrà interrotto collaboratori, purché i contratti pubblici vengono mantenuti.

### <a name="dependency-inversion"></a>Inversione di dipendenza

La direzione di dipendenza all'interno dell'applicazione deve essere nella direzione di astrazione, non i dettagli di implementazione. La maggior parte delle applicazioni vengono scritti in modo che in fase di compilazione dipendenza scorre nella direzione dell'esecuzione di runtime. Ciò produce un grafico di dipendenze dirette. Ovvero, se le chiamate di modulo A una funzione nel modulo B, che chiama una funzione nel modulo C, quindi quando è necessario un tempo di compilazione dipendono da B dipenderà C, come illustrato nella figura 4-1.

![](./media/image4-1.png)

**Figura 4-1.** Grafico delle dipendenze dirette.

Applicazione del principio di inversione di dipendenza consente A chiamare metodi sul astrazione che implementa B, rendendo possibili per una chiamata di B in fase di esecuzione, ma per B che dipendono da un'interfaccia controllata da una fase di compilazione (in questo modo, *inversione* la dipendenza della fase di compilazione tipico). In fase di esecuzione, il flusso dell'esecuzione del programma rimane invariato, ma l'introduzione di interfacce significa che le implementazioni diverse di queste interfacce facilmente possono essere collegate.

![](./media/image4-2.png)

**Figura 4-2.** Grafico delle dipendenze invertito.

**Inversione di dipendenza** costituisce una parte fondamentale della compilazione di applicazioni ad accoppiamento debole, poiché i dettagli di implementazione possono essere scritta dipendono e implementare astrazioni di livello superiore piuttosto che nel caso opposto. Le applicazioni che sono di conseguenza più testabili modulare e gestibile. La pratica di *inserimento di dipendenze* è reso possibile seguendo il principio di inversione della dipendenza.

### <a name="explicit-dependencies"></a>Dipendenze esplicite

**Classi e metodi devono richiedere in modo esplicito gli oggetti in collaborazione che necessarie per il corretto funzionamento.** Costruttori di classi forniscono un'opportunità per le classi identificare le operazioni che necessarie per poter essere in uno stato valido e funzioni correttamente. Se si definiscono le classi che può essere creato e chiamato, ma che funzionerà correttamente solo se vengono implementati alcuni componenti di infrastruttura o globale, queste classi vengono *disonesti* con i relativi client. Indica il contratto di costruttore client che richiede solo le operazioni specificate (possibilmente nothing se la classe è solo tramite un costruttore predefinito), ma in realtà l'oggetto runtime necessita qualcos'altro.

Seguendo il principio di dipendenze esplicite, le classi e i metodi vengono accurati con i client su cui hanno bisogno per funzionare. Questo rende il codice autodocumentato più e l'attività di codifica di contratti più intuitiva, poiché gli utenti accedono per considerare attendibile che, a condizione che forniscono a quello che richiede la forma del metodo o i parametri del costruttore, gli oggetti che stanno con comportamento correttamente in fase di esecuzione.

### <a name="single-responsibility"></a>Unica responsabilità

Il principio di responsabilità singola si applica a progettazione orientata agli oggetti, ma può anche essere considerato un principio dell'architettura simile per la separazione dei compiti. Indicante che gli oggetti deve essere di sola responsabilità e che hanno solo uno dei motivi per modificare. In particolare, l'unico caso in cui è necessario modificare l'oggetto è se è necessario aggiornare il modo in cui esegue la responsabilità di uno. Consente di produrre più regime questo principio e sistemi modulari, poiché molti tipi di nuovo comportamento possono essere implementati come nuove classi, anziché tramite l'aggiunta di ulteriori responsabilità alle classi esistenti. Aggiunta di nuove classi è sempre più sicuro rispetto alla modifica classi esistenti, dal codice non ancora dipende le nuove classi.

In un'applicazione monolitica, è possibile applicare il principio di responsabilità singolo a un livello elevato per i livelli dell'applicazione. Responsabilità di presentazione deve rimanere nel progetto dell'interfaccia utente, mentre l'accesso ai dati responsabilità deve rimanere all'interno di un progetto di infrastruttura. Logica di business deve essere incluso nel progetto di base dell'applicazione, in cui possono essere facilmente testata e possono evolvere in modo indipendente da altre responsabilità.

Quando questo principio viene applicato all'architettura delle applicazioni e impiegato per l'endpoint logico, si ottengono microservizi. Un microservizio specificato deve avere un'unica responsabilità. Se è necessario estendere il comportamento di un sistema, è preferibile eseguire questa operazione aggiungendo ulteriori microservizi, anziché tramite l'aggiunta di responsabilità per uno esistente.

[Ulteriori informazioni sull'architettura di microservizi](http://aka.ms/MicroservicesEbook)

### <a name="dont-repeat-yourself-dry"></a>Non ripetere manualmente (sorgente)

L'applicazione deve evitare di specifica del comportamento relative a un particolare concetto in più posizioni poiché si tratta di un'origine frequente di errori. A un certo punto, una modifica nei requisiti sarà necessario modificare questo comportamento e la probabilità che almeno un'istanza del comportamento non verrà aggiornato determineranno un comportamento coerente del sistema.

Anziché la duplicazione di logica, incapsularlo in un costrutto di programmazione. Imposta come costruire l'unica autorità su questo comportamento, in modo che qualsiasi altra parte dell'applicazione che richiede il problema, utilizzare il costrutto di nuovo.

> [!NOTE]
> Evitare l'associazione insieme il comportamento che è solo coincidenza ricorrenti. Ad esempio, solo perché due costanti diverse entrambi hanno lo stesso valore, non implica che si deve avere solo una costante, se concettualmente si intendono diversi significati.

### <a name="persistence-ignorance"></a>Mancato riconoscimento della persistenza

**Mancato riconoscimento della persistenza** (PI) fa riferimento a tipi che devono essere mantenute, ma il cui codice è influenzato dalla scelta della tecnologia di persistenza. Tali tipi in .NET sono dette Plain Old CLR Object (POCOs), in quanto non devono ereditare da una determinata classe di base o implementare un'interfaccia specifica. Mancato riconoscimento della persistenza è utile perché consente lo stesso modello di business che deve essere mantenuta in più modi, che offre una maggiore flessibilità per l'applicazione. Opzioni di persistenza potrebbero cambiare nel tempo, dalla tecnologia di un database a un altro, o ulteriori forme di persistenza potrebbero essere necessari oltre a qualunque avviata con l'applicazione (ad esempio, utilizzando una cache Redis di Azure DocumentDb, oltre a un database relazionale).

Alcuni esempi di violazioni di questo principio:

-   Una classe di base necessaria

-   Un'implementazione di interfaccia necessaria

-   Classi responsabile per il loro salvataggio (ad esempio, il modello attivo)

-   Costruttore predefinito obbligatorio

-   Proprietà che richiedono virtual (parola chiave)

-   Attributi obbligatori di persistenza specifico

Il requisito che presentano le funzionalità o i comportamenti precedente aggiunge l'accoppiamento tra i tipi devono essere rese persistenti e la scelta della tecnologia di persistenza, rende più difficoltoso di adottare strategie di accesso nuovi dati in futuro.

### <a name="bounded-contexts"></a>Contesti limitati

**Delimitata contesti** sono un criterio centrale nella progettazione. Forniscono un modo di complessità di gestione in organizzazioni o applicazioni di grandi dimensioni da suddividerlo in moduli concettuali separati. Ogni modulo concettuale rappresenta quindi un contesto separato da altri contesti (pertanto limitato) e possono evolvere in modo indipendente. Ogni contesto delimitata dovrebbe essere idealmente libero di scegliere i relativi nomi concetti all'interno di esso e dovrebbe avere accesso esclusivo a un proprio archivio di persistenza.

Come minimo, singole applicazioni web devono essere quanto più possibile i propri contesto delimitata, con un proprio archivio di persistenza per i modelli di business, piuttosto che condividono un database con altre applicazioni. Ha luogo la comunicazione tra contesti delimitati tramite interfacce di programmazione, anziché tramite un database condiviso che consente la logica di business e inserire gli eventi da eseguire in risposta alle modifiche che si verificano. Limitato strettamente mappa contesti di microservizi, anche in teoria implementati come proprio singoli contesti limitati.

> ### <a name="references--modern-web-applications"></a>Riferimenti: moderne applicazioni Web
> - **Separazione dei compiti**  
> <http://deviq.com/Separation-of-concerns/>
> - **Incapsulamento** <http://deviq.com/encapsulation/>
> - **Principio di inversione di dipendenza**  
> <http://deviq.com/Dependency-Inversion-Principle/>
> - **Principio dipendenze esplicite**  
> <http://deviq.com/Explicit-Dependencies-Principle/>
> - **Non ripetere manualmente**  
> <http://deviq.com/Don-t-Repeat-Yourself/>
> - **Mancato riconoscimento della persistenza**  
> <http://deviq.com/Persistence-Ignorance/>
> - **Contesto associato**  
> <https://martinfowler.com/bliki/BoundedContext.HTML>

> [!div class="step-by-step"]
[Precedente] [Avanti] (comuni-web-applicazione-architectures.md) (choose-between-traditional-web-and-single-page-apps.md)
