---
title: Problemi e soluzioni per la gestione dei dati distribuiti
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Problemi e soluzioni per la gestione dei dati distribuiti
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f961475b40c74bf448cff1aeae04ae4866360e52
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="challenges-and-solutions-for-distributed-data-management"></a>Problemi e soluzioni per la gestione dei dati distribuiti

## <a name="challenge-1-how-to-define-the-boundaries-of-each-microservice"></a>Richiesta di verifica \#1: come definire i limiti di ogni microservizio

Definizione dei limiti microservizio è probabilmente il primo problema che rileva tutti gli utenti. Ogni microservizio deve essere una parte dell'applicazione e ogni microservizio deve essere autonomo con tutti i vantaggi e i problemi che fornisce. Ma come identificare tali limiti?

In primo luogo, è necessario concentrarsi sui modelli di logica del dominio dell'applicazione e i dati correlati. È necessario tentare di individuare disaccoppiate isole di dati e i contesti diversi all'interno della stessa applicazione. Ogni contesto potrebbe avere una lingua diverse business (condizioni aziendali diversi). I contesti di devono essere definiti e gestiti in modo indipendente. I termini e le entità utilizzate in tali contesti diversi potrebbero sembrare simili, ma è possibile individuare in un contesto specifico, viene utilizzato un concetto aziendale con uno per uno scopo diverso in un altro contesto e potrebbe anche essere un nome diverso. Ad esempio, un utente può fare riferimento come utente nel contesto di identità o l'appartenenza, come un cliente in un contesto CRM, come un acquirente in un contesto di ordinamento e così via.

Il modo in cui si identificano i limiti tra più contesti dell'applicazione con un dominio diverso per ogni contesto è esattamente come è possibile identificare i limiti per ogni microservizio business e il relativo correlati modello di dominio e i dati. Si tenta sempre di ridurre al minimo l'accoppiamento tra tali microservizi. Questa guida fornisce informazioni più dettagliate su questa progettazione modello di identificazione e il dominio nella sezione [che identifica i limiti di modello di dominio per ogni microservizio](#identifying-domain-model-boundaries-for-each-microservice) in un secondo momento.

## <a name="challenge-2-how-to-create-queries-that-retrieve-data-from-several-microservices"></a>Richiesta di verifica \#2: come creare query che recuperano dati da diversi microservizi

Una sfida secondo viene illustrato come implementare le query che recuperano dati da diversi microservizi, evitando comunicazioni "frammentate" per il microservizi dalle applicazioni client remoto. Un esempio potrebbe essere una singola schermata da un'app per dispositivi mobili che è necessario visualizzare informazioni sull'utente che appartiene a carrello, catalogo e microservizi identità utente. Un altro esempio sarebbe un che include molte tabelle che si trova in microservizi più complessi del report. La soluzione dipende dalla complessità delle query. Ma in ogni caso, è necessario un modo per aggregare informazioni se si desidera migliorare l'efficienza di comunicazione del sistema. Le soluzioni più comuni sono i seguenti.

**Gateway API**. Per l'aggregazione di dati semplice da microservizi più proprietari di database diversi, l'approccio consigliato è microservizio un'aggregazione definita un API Gateway. Tuttavia, è necessario prestare attenzione nell'implementazione di questo modello, poiché può trattarsi di un punto di riduzione nel sistema e può violare il principio di autonomia microservizio. Per limitare questo problema, è possibile avere più gateway API specifico ogni uno con particolare attenzione ad un verticale "sezione" o l'area di attività del sistema. Il modello API Gateway è illustrato più dettagliatamente nella sezione in uso un Gateway di API in un secondo momento.

**CQRS con le tabelle di query/letture**. Un'altra soluzione per aggregare i dati da più microservizi è il [modello vista materializzata](https://docs.microsoft.com/azure/architecture/patterns/materialized-view). In questo approccio, si genera, in anticipo (preparazione dati denormalizzati prima si verifichino le query effettive), una tabella di sola lettura con i dati che appartiene a più microservizi. La tabella ha un formato adatto alle esigenze dell'applicazione client.

Prendere in considerazione simile nella schermata per un'app per dispositivi mobili. Se si dispone di un singolo database, è possibile raccogliere i dati per tale schermata utilizzando una query SQL che esegue un join complesso che interessa più tabelle. Tuttavia, quando si dispone di più database, e ogni database è di proprietà di un microservizio diversi, non è possibile eseguire una query sui database e creare un join SQL. La query complessa diventa un problema. È possibile indirizzare il requisito di utilizzo di un approccio CQRS, si crea una tabella denormalizzata in un database diverso che viene utilizzato solo per le query. Nella tabella può essere progettata in modo specifico per i dati che necessari per la query complessa, con una relazione uno a uno tra i campi necessari per la schermata dell'applicazione e le colonne nella tabella della query. Può anche essere utilizzato ai fini dei report.

Questo approccio non solo consente di risolvere il problema originale (come query e creare un join tra microservizi); anche migliora le prestazioni notevolmente quando vengono confrontati con un join complesso, poiché hai già i dati necessari per l'applicazione nella tabella della query. Naturalmente, l'uso di comandi e Query Responsibility Segregation (CQRS) con le tabelle di query/letture significa ulteriore lavoro di sviluppo e sarà necessario adottare la coerenza finale. Ciononostante, i requisiti di prestazioni e scalabilità elevate in [scenari di collaborazione](http://udidahan.com/2011/10/02/why-you-should-be-using-cqrs-almost-everywhere/) (o gli scenari di concorrenza, in base al punto di vista) è in cui è necessario applicare CQRS con più database.

**"Dati ad accesso sporadico" in un database centrale**. Per i report complessi e le query che non siano richiesti dei dati in tempo reale, un approccio comune consiste nell'esportare i "dati sensibili" (dati transazionali di microservizi) come "dati ad accesso sporadico" nel database di grandi dimensioni che vengono utilizzati solo per i report. Tale sistema database centrale può essere un sistema basato su dati di grandi dimensioni, ad esempio Hadoop, un data warehouse come basato su Azure SQL Data Warehouse, o anche un singolo database SQL utilizzato solo per i report (se dimensione non è un problema).

Tenere presente che questo database centralizzato potrebbe essere utilizzato solo per le query e report che non richiedono dati in tempo reale. Le transazioni, come origine di dati reali, originale devono essere nei dati microservizi. Il modo in cui si sincronizzeranno i dati sarebbe tramite comunicazione basata su eventi (descritta nelle sezioni successive) o tramite altri strumenti di importazione/esportazione di infrastruttura di database. Se si usa la comunicazione basata sugli eventi, il processo di integrazione sarà simile al modo in cui che distribuire i dati come descritto in precedenza per le tabelle CQRS query.

Tuttavia, se la progettazione dell'applicazione implica costantemente l'aggregazione di informazioni da più microservizi per le query complesse, potrebbe essere un sintomo di un progetto non valido, ovvero un microservizio deve essere al massimo da altri microservizi isolata. (Esclusi i report/analitica che è necessario utilizzare sempre i database centrali di dati a freddo). Spesso questo problema potrebbe essere necessario microservizi di tipo merge. È necessario bilanciare l'autonomia evoluzione e la distribuzione di ogni microservizio con dipendenze complesse, coesione e aggregazione dei dati.

## <a name="challenge-3-how-to-achieve-consistency-across-multiple-microservices"></a>Richiesta di verifica \#3: come ottenere la coerenza tra più microservizi

Come indicato in precedenza, i dati di proprietà di ogni microservizio sono privati per tale microservizio e accessibile solo tramite la API microservizio. Pertanto, una richiesta presentata viene illustrato come implementare i processi di business-to-end, mantenendo la coerenza tra più microservizi.

Per analizzare il problema, esaminiamo un esempio dal [eShopOnContainers riferimento applicazione](http://aka.ms/eshoponcontainers). Il catalogo di microservizio mantiene le informazioni relative a tutti i prodotti, tra cui il livello di scorte. Microservizio l'ordinamento gestisce gli ordini e deve verificare che un nuovo ordine non superi il codice di prodotto di catalogo disponibili. In alternativa, lo scenario può implicare la logica che gestisce inevasa prodotti. In un'ipotetica monolitica versione dell'applicazione, è possibile che il sottosistema di ordinamento utilizzare semplicemente una transazione ACID per controllare la disponibilità in magazzino, creare l'ordine nella tabella Orders e aggiornare le azioni disponibili nella tabella Products.

Tuttavia, in un'applicazione microservizi basati su tabelle Order e prodotto appartengono i rispettivi microservizi. Nessun microservizio deve sempre includere i database di proprietà da un altro microservizio nella propria transazioni o di una query, come illustrato nella figura 4-9.

![](./media/image9.PNG)

**Figura 4-9**. Un microservizio non è possibile accedere direttamente a una tabella in un altro microservizio

Microservizio l'ordinamento deve aggiornare la tabella Products direttamente, la tabella Products appartiene microservizio il catalogo. Per rendere un aggiornamento per il catalogo di microservizio, microservizio l'ordinamento deve utilizzare esclusivamente la comunicazione asincrona, ad esempio eventi di integrazione (messaggio e la comunicazione basata su evento). Questo è il modo in [eShopOnContainers](http://aka.ms/eshoponcontainers) riferimento applicazione consente di eseguire questo tipo di aggiornamento.

Come indicato dal [teorema di CAP](https://en.wikipedia.org/wiki/CAP_theorem), è necessario scegliere tra la disponibilità e la coerenza assoluta ACID. La maggior parte degli scenari basati su microservizio richiedono scalabilità e disponibilità elevate anziché la coerenza assoluta. Applicazioni mission-critical devono rimanere attivo e in esecuzione e gli sviluppatori possono aggirare coerenza assoluta utilizzando le tecniche per l'utilizzo con la coerenza eventuale o debole. Si tratta dell'approccio adottato per la maggior parte delle architetture basate su microservizio.

Inoltre, ACID stile o le transazioni di commit in due fasi non sono solo con i principi di microservizi; la maggior parte dei database NoSQL (ad esempio Azure Cosmos DB, MongoDB, e così via) non supportano le transazioni di commit in due fasi. Tuttavia, la gestione dei dati è essenziale garantire l'uniformità tra servizi e database. Questo problema è correlato alla domanda come propagare le modifiche tra più microservizi quando devono essere ridondante determinati dati, ad esempio, quando è necessario disporre di nome o descrizione microservizio il catalogo e gli acquisti del prodotto microservizio.

Una buona soluzione per questo problema consiste nell'utilizzare la coerenza eventuale tra microservizi articolati tramite comunicazione basata sugli eventi e un sistema di pubblicazione e sottoscrizione. Questi argomenti vengono trattati nella sezione [comunicazione asincrona basata sugli eventi](#async_event_driven_communication) più avanti in questa Guida.

## <a name="challenge-4-how-to-design-communication-across-microservice-boundaries"></a>Richiesta di verifica \#4: modalità di progettazione di comunicazione attraverso i limiti di microservizio

Le comunicazioni tra microservizio limiti è una vera sfida. In questo contesto, la comunicazione non fa riferimento a del protocollo è necessario utilizzare (HTTP e REST, AMQP, messaggistica e così via). Indirizza, invece, è necessario utilizzare lo stile di comunicazione e soprattutto come al microservizi devono essere. A seconda del livello di controllo libero, quando si verifica un errore, l'impatto dell'errore del sistema varia in modo significativo.

In un sistema distribuito, ad esempio un'applicazione basata su microservizi, con molti elementi spostamento e i servizi distribuiti in numerosi server o host, componenti infine non riuscirà. Errore parziale e interruzioni anche maggiori verificherà, pertanto è necessario progettare il microservizi e la comunicazione tra di loro tenendo conto dei rischi comuni in questo tipo di sistema distribuito.

Un approccio comune consiste nell'implementare HTTP (REST)-base microservizi, a causa delle loro semplicità. Un approccio basato su HTTP è perfettamente accettabile. In questo caso il problema è correlato a modalità di utilizzo. Se si utilizza richieste e risposte HTTP per interagire con i microservizi dalle applicazioni client o dal gateway API, è corretto. Ma se si crea lunghe catene di chiamate HTTP sincrone tra microservizi, le comunicazioni tra i loro limiti, come se i microservizi erano oggetti in un'applicazione monolitico, l'applicazione verrà infine eseguita problemi.

Ad esempio, si supponga che l'applicazione client esegue una chiamata di API HTTP per un singolo microservizio come microservizio l'ordinamento. Se microservizio l'ordinamento, a sua volta chiama aggiuntiva del ciclo di microservizi tramite HTTP all'interno della stessa richiesta/risposta, si sta creando una catena di chiamate HTTP. Potrebbe sembrare ragionevole inizialmente. Tuttavia, esistono aspetti importanti da considerare quando si passa questo percorso:

-   Prestazioni di blocco e bassa. A causa della natura sincrona di HTTP, la richiesta originale non riceverà una risposta fino al termine di tutte le chiamate HTTP interne. Si supponga se il numero delle chiamate aumenta in modo significativo e allo stesso tempo un HTTP intermedia chiamate a un microservizio è bloccato. Il risultato è che ha un impatto sulle prestazioni e la scalabilità complessiva sarà interessata in modo esponenziale come aumento di richieste HTTP aggiuntiva.

-   Accoppiamento microservizi con HTTP. Business microservizi non devono essere abbinato altri microservizi di business. In teoria, dovrebbe non "sappiano" l'esistenza di altri microservizi. Se l'applicazione si basa su accoppiamento microservizi come illustrato nell'esempio, sarà possibile praticamente ottenere l'autonomia per microservizio.

-   Errore di qualsiasi un microservizio. Se è stata implementata una catena di microservizi collegata tramite chiamate HTTP, quando l'intera catena di microservizi di microservizi non riesce (e infine hanno esito negativo) avrà esito negativo. Un sistema basato su microservizio deve essere progettato per continuare a lavorare migliori prestazioni possibili durante gli errori parziali. Anche se si implementa la logica di client che utilizza i tentativi con backoff esponenziale o interruttore meccanismi, le catene di chiamate più complesso HTTP sono, più è complessa è è implementare una strategia di un errore basata su HTTP.

Infatti, se l'interni microservizi comunicano mediante la creazione di catene di richieste HTTP, come descritto, potrebbe sembrare che si dispone di un'applicazione monolitica, ma una basata su HTTP tra processi anziché meccanismi di comunicazione intraprocess.

Pertanto, per imporre l'autonomia microservizio e dispone di resilienza migliore, è necessario ridurre l'utilizzo delle catene di comunicazione richiesta/risposta tra microservizi. È consigliabile utilizzare l'interazione asincrona solo per la comunicazione tra reti-microservizio, tramite la comunicazione asincrona ed evento-basata su messaggi o tramite polling HTTP in modo indipendente dal ciclo di richiesta/risposta HTTP originale.

Viene illustrato l'utilizzo di comunicazione asincrona con dettagli aggiuntivi, più avanti in questa Guida nelle sezioni [integration microservizio asincrona consente di applicare l'autonomia del microservizio](#asynchronous-microservice-integration-enforce-microservices-autonomy) e [asincrono comunicazione basata su messaggi](#asynchronous-message-based-communication).

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Teorema di CAP**
    [*https://en.wikipedia.org/wiki/CAP\_teorema*](https://en.wikipedia.org/wiki/CAP_theorem)

-   **La coerenza eventuale**
    [*https://en.wikipedia.org/wiki/Eventual\_coerenza*](https://en.wikipedia.org/wiki/Eventual_consistency)

-   **Nozioni di base della coerenza dei dati**
    [*https://msdn.microsoft.com/library/dn589800.aspx*](https://msdn.microsoft.com/library/dn589800.aspx)

-   **Martin Fowler. CQRS (comando e la separazione delle responsabilità Query)**
    [*http://martinfowler.com/bliki/CQRS.html*](http://martinfowler.com/bliki/CQRS.html)

-   **Vista materializzata**
    [*https://docs.microsoft.com/azure/architecture/patterns/materialized-view*](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)

-   **Charles riga. Visual Studio ACID. BASE: Il Shifting pH l'elaborazione delle transazioni di Database**
    [*http://www.dataversity.net/acid-vs-base-the-shifting-ph-of-database-transaction-processing/*](http://www.dataversity.net/acid-vs-base-the-shifting-ph-of-database-transaction-processing/)

-   **Transazioni di compensazione**
    [*https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction*](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

-   **udi Dahan. Composizione orientato ai servizi**
    [*http://udidahan.com/2014/07/30/service-oriented-composition-with-video/*](http://udidahan.com/2014/07/30/service-oriented-composition-with-video/)


>[!div class="step-by-step"]
[Precedente] (logico-e-fisica-architecture.md) [Avanti] (identificare-microservizio-dominio-modello-boundaries.md)
