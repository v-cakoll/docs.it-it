---
title: Principi architetturali
description: Progettare applicazioni Web moderne con ASP.NET Core e Azure | Principi architetturali
author: ardalis
ms.author: wiwagn
ms.date: 12/04/2019
ms.openlocfilehash: a3444071abae89780304a9687e486f3842283a33
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396239"
---
# <a name="architectural-principles"></a>Principi architetturali

> "Se i costruttori costruissero edifici come i programmatori scrivono i programmi, il primo picchio che passa distruggerebbe la civiltà."  
> _\-Gerald Weinberg_

È necessario ideare e progettare soluzioni software tenendo presente l'aspetto della loro gestione. I principi indicati in questa sezione possono favorire scelte architetturali che daranno vita ad applicazioni pulite e gestibili. Generalmente, questi principi orientano verso la creazione di applicazioni contenenti componenti discreti che non sono strettamente accoppiati ad altre parti dell'applicazione, ma che comunicano tramite interfacce esplicite o sistemi di messaggistica.

## <a name="common-design-principles"></a>Principi di progettazione comuni

### <a name="separation-of-concerns"></a>Separazione delle problematiche

Un principio guida per lo sviluppo di applicazioni è **la separazione dei concetti**. In base a questo principio, deve esistere una separazione a livello di software in funzione delle operazioni eseguite. Ad esempio, si consideri un'applicazione che include la logica per l'identificazione di elementi importanti da visualizzare all'utente e la formattazione specifica di tali elementi per renderli più evidenti. Il comportamento responsabile della scelta degli elementi da formattare deve essere mantenuto separato dal comportamento responsabile della formattazione degli elementi, poiché questi comportamenti sono problemi distinti che sono strettamente correlati tra loro.

A livello di architettura, le applicazioni possono essere compilate logicamente per seguire questo principio separando il comportamento aziendale principale dall'infrastruttura e dalla logica dell'interfaccia utente. Idealmente, le regole e la logica di business dovrebbero risiedere in un progetto separato e autonomo rispetto agli altri progetti dell'applicazione. Questa separazione garantisce che il modello aziendale sia facile da testare e possa evolvere senza essere strettamente associato a dettagli di implementazione di basso livello. La separazione dei compiti è un fattore chiave nella scelta di utilizzare i livelli nelle architetture delle applicazioni.

### <a name="encapsulation"></a>Incapsulamento

Parti diverse di un'applicazione devono essere isolate da altre mediante l'**incapsulamento**. I componenti e i livelli dell'applicazione devono essere in grado di regolare la loro implementazione interna senza interrompere i collaboratori, a patto che i contratti esterni non vengano violati. Un utilizzo corretto dell'incapsulamento consente di progettare le applicazioni con modularità e un tipo di accoppiamento debole poiché gli oggetti e i pacchetti possono essere sostituiti con implementazioni alternative, purché la stessa interfaccia venga mantenuta.

L'incapsulamento delle classi avviene limitando l'accesso esterno allo stato interno della classe. Se un attore esterno vuole modificare lo stato dell'oggetto, dovrà farlo tramite una funzione ben definita o un setter di proprietà anziché accedendo direttamente allo stato privato dell'oggetto. Analogamente, i componenti dell'applicazione e le applicazioni stesse non devono consentire la modifica diretta del loro stato bensì esporre interfacce ben definite a uso dei collaboratori. Questo accorgimento consente alla struttura interna dell'applicazione di evolversi nel tempo senza comportare l'interruzione dei collaboratori, purché i contratti pubblici vengano mantenuti.

### <a name="dependency-inversion"></a>Inversione delle dipendenze

La direzione delle dipendenza all'interno dell'applicazione deve puntare verso l'astrazione, non verso i dettagli di implementazione. La maggior parte delle applicazioni viene scritta in modo che le dipendenze in fase di compilazione scorrano nella direzione dell'esecuzione del runtime, producendo un grafico delle dipendenze dirette. Ovvero, se il modulo A chiama una funzione nel modulo B, che chiama una funzione nel modulo C, in fase di compilazione a dipenderà da B, che dipenderà da C, come illustrato nella figura 4-1.

![Grafico dipendenze dirette](./media/image4-1.png)

**Figura 4-1.** Grafico delle dipendenze dirette.

L'applicazione del principio di inversione delle dipendenze consente ad A di chiamare metodi su un'astrazione implementata da B, consentendo ad A di chiamare B in fase di esecuzione, ma a B di dipendere da un'interfaccia controllata da A in fase di compilazione pertanto *invertendo* le dipendenze tipiche della fase di compilazione. In fase di esecuzione, il flusso di esecuzione del programma rimane invariato, ma l'introduzione di interfacce significa che sarà possibile collegare facilmente diverse implementazioni di tali interfacce.

![Grafico dipendenze invertite](./media/image4-2.png)

**Figura 4-2.** Grafico delle dipendenze inverse.

L' **inversione delle dipendenze** è una parte essenziale della creazione di applicazioni a regime di controllo libero, poiché i dettagli di implementazione possono essere scritti in modo da dipendere da e implementare astrazioni di livello superiore, anziché viceversa. Le applicazioni così ottenute sono più testabili, modulari e gestibili. La pratica dell'*inserimento di dipendenze* è resa possibile dall'applicazione del principio di inversione delle dipendenze.

### <a name="explicit-dependencies"></a>Dipendenze esplicite

**Le classi e i metodi devono richiedere in modo esplicito gli oggetti in collaborazione di cui necessitano per funzionare correttamente.** I costruttori di classi forniscono alle classi l'opportunità di individuare gli elementi necessari per essere in uno stato valido e per funzionare correttamente. Se si definiscono classi che possono essere costruite e chiamate, ma che funzioneranno correttamente solo se sono presenti determinati componenti globali o dell'infrastruttura, queste classi sono *disoneste* con i client. Il contratto del costruttore indica al client che necessita solo degli elementi specificati, o addirittura di nessun elemento se la classe usa semplicemente un costruttore senza parametri, ma in realtà in fase di esecuzione necessita di qualcos'altro.

Se ci si attiene al principio delle dipendenze esplicite, le classi e i metodi comunicano esattamente ai relativi client ciò di cui hanno bisogno per funzionare. Seguendo il principio, il codice è più autodocumentato e i contratti di codifica sono più semplici da usare, poiché gli utenti considereranno attendibile che, purché forniscano gli elementi necessari sotto forma di parametri del metodo o del costruttore, gli oggetti che stanno utilizzando si comporteranno correttamente in fase di esecuzione.

### <a name="single-responsibility"></a>Singola responsabilità

Il principio di singola responsabilità si applica alla programmazione orientata agli oggetti, ma può anche essere considerato un principio architetturale simile alla separazione dei concetti. Afferma che gli oggetti devono avere una sola responsabilità e un solo motivo per cambiare. Nello specifico, l'unica situazione in cui l'oggetto può cambiare è se il modo in cui svolge la sua unica responsabilità richiede di essere aggiornato. Questo principio contribuisce a produrre sistemi modulari e a regime di controllo libero, poiché molti tipi di nuovo comportamento possono essere implementati come nuove classi, anziché aggiungendo responsabilità aggiuntiva alle classi esistenti. L'aggiunta di nuove classi è sempre una pratica più sicura rispetto alla modifica delle classi esistenti, dal momento che da queste nuove classi non dipende alcun codice.

In un'applicazione monolitica, è possibile applicare il principio di singola responsabilità ad alto livello e trasferirlo agli altri livelli dell'applicazione. La responsabilità della presentazione deve rimanere nel progetto dell'interfaccia utente, mentre la responsabilità dell'accesso ai dati deve essere mantenuta all'interno di un progetto di infrastruttura. La logica di business deve essere inclusa nel progetto principale dell'applicazione, dove può essere facilmente testata ed evolvere in modo indipendente da altre responsabilità.

Quando questo principio viene applicato all'architettura dell'applicazione e viene portato al relativo endpoint logico, si ottengono microservizi. Ogni microservizio deve avere una singola responsabilità. Se si presenta la necessità di estendere il comportamento di un sistema, è preferibile farlo aggiungendo ulteriori microservizi, anziché aggiungendo responsabilità a un microservizio esistente.

[Altre informazioni sull'architettura dei microservizi](https://aka.ms/MicroservicesEbook)

### <a name="dont-repeat-yourself-dry"></a>Don't Repeat Yourself (DRY)

L'applicazione deve evitare di specificare un comportamento correlato a un particolare concetto in più posizioni, perché questa pratica è una fonte frequente di errori. A un certo punto, una modifica dei requisiti richiederà la modifica di questo comportamento. È probabile che almeno un'istanza del comportamento non venga aggiornata e che il sistema si comporti in modo incoerente.

Anziché duplicare la logica, è preferibile incapsularla in un costrutto di programmazione. Rendere il costrutto l'unica autorità su questo comportamento e fare in modo che qualsiasi altra parte dell'applicazione che richiede questo comportamento utilizzi il nuovo costrutto.

> [!NOTE]
> Evitare di associare tra loro comportamenti che sono solo casualmente ripetitivi. Ad esempio, il fatto che due costanti diverse hanno entrambe lo stesso valore non implica che dovrebbe essercene solo una, se concettualmente si riferiscono ad elementi diversi.

### <a name="persistence-ignorance"></a>Mancato riconoscimento della persistenza

Il **mancato riconoscimento della persistenza** riguarda i tipi che devono essere resi persistenti ma il cui codice non è influenzato dalla scelta della tecnologia di persistenza. In .NET tali tipi sono a volte definiti Plain Old CLR Object (POCO), in quanto non sono gravati dalla necessità di ereditare da una determinata classe base o di implementare un'interfaccia specifica. Il mancato riconoscimento della persistenza è utile perché consente allo stesso modello di business di essere reso permanente in più modi migliorando la flessibilità dell'applicazione. È possibile che le opzioni di persistenza cambino nel tempo, da una tecnologia di database a un'altra o da ulteriori forme di persistenza, oltre a qualsiasi altra operazione avviata dall'applicazione, ad esempio l'uso di una cache Redis o Azure Cosmos DB in aggiunta a un database relazionale.

Alcuni esempi di violazioni di questo principio:

- Una classe base obbligatoria.

- Un'implementazione dell'interfaccia obbligatoria.

- Classi responsabili del proprio salvataggio ad esempio, il criterio del record attivo.

- Costruttore senza parametri obbligatorio.

- Proprietà che richiedono una parola chiave virtuale.

- Attributi di persistenza obbligatori.

Il requisito che le classi presentino una o più funzionalità o uno o più comportamenti precedenti rende permanente l'accoppiamento tra i tipi e aggiunge la scelta della tecnologia di persistenza, rendendo più difficoltoso adottare nuove strategie di accesso ai dati in futuro.

### <a name="bounded-contexts"></a>Contesti limitati

I **contesti limitati** sono un criterio centrale nell'approccio Domain-driven design. Rappresentano un modo per gestire la complessità in organizzazioni o applicazioni di grandi dimensioni tramite la suddivisione in moduli concettuali separati. Ogni modulo concettuale rappresenta quindi un contesto separato da altri contesti (di conseguenza, delimitato) e può evolvere in modo indipendente. Ogni contesto limitato dovrebbe essere idealmente libero di scegliere i nomi per i concetti al suo interno e dovrebbe avere accesso esclusivo al proprio archivio di persistenza.

Come minimo, ogni singola applicazione web deve puntare ad essere il proprio contesto limitato, con un archivio di persistenza per il proprio modello di business, piuttosto che condividere un database con altre applicazioni. La comunicazione tra contesti limitati non avviene tramite un database condiviso bensì tramite interfacce di programmazione che consentono la generazione di eventi e logica di business in risposta alle modifiche che si verificano. I contesti limitati sono strettamente mappati a microservizi, anch'essi idealmente implementati come singoli contesti limitati.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Modelli di progettazione JAVA: principi](https://java-design-patterns.com/principles/)
- [Contesti limitati](https://martinfowler.com/bliki/BoundedContext.html)

>[!div class="step-by-step"]
>[Precedente](choose-between-traditional-web-and-single-page-apps.md) 
> [Avanti](common-web-application-architectures.md)
