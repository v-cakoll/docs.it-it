---
title: Funzionalità dell'ambiente di sviluppo di F#
description: 'Informazioni su quali funzionalità di Visual Studio 2012 sono supportate in F #.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: dd5c3165a73bd4f821a26d183094829dab7eaeae
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="visual-f-development-environment-features"></a>Funzionalità dell'ambiente di sviluppo di Visual F#

> [!NOTE]
In questo articolo non è aggiornato con il più recente di Visual Studio.  Verrà eseguito un aggiornamento.

In questo argomento include informazioni sulle funzionalità di Visual Studio 2012 sono supportate in F #.

## <a name="project-features"></a>Funzionalità del progetto
Nella tabella seguente sono riepilogati i modelli disponibili per l'utilizzo nei progetti F #. Per informazioni sui modelli di progetto e di elemento, vedere [creazione di progetti da modelli](https://msdn.microsoft.com/library/7c36d86a-6b79-4480-8228-0f925f1204b2).

|Tipo di modello|Descrizione|Modelli supportati|
|-------------|-----------|-------------------|
|Modelli di progetto|Tipi di progetto disponibili nel **nuovo progetto** la finestra di dialogo.|<ul><li>Applicazione F #<br /></li><li>Libreria F #<br /></li><li>Esercitazione su F #<br /></li><li>Libreria portabile F #<br /></li><ul/>|
|Modelli di elemento|Tipi di file disponibili nel **Aggiungi nuovo elemento** la finestra di dialogo.|<ul><li>File di origine F # (. FS)<br /></li><li>Script F # (fsx)<br /></li><li>File di firma F # (. fsi)<br /></li><li>File di configurazione (config)<br /></li><li>Connessione al Database SQL (provider di tipi LINQ to SQL)<br /></li><li>Connessione al Database SQL (LINQ to Entities provider di tipi)<br /></li><li>Connessione al servizio OData (provider di tipo LINQ)<br /></li><li>Connessione al servizio WSDL (provider di tipi)<br /></li><li>File XML (con estensione XML)<br /></li><li>File di testo<br /></li><ul/>|
Per creare un'applicazione che può essere eseguito come un file eseguibile autonomo, scegliere il tipo di progetto applicazione F #. Per creare una libreria (vale a dire un assembly gestito o. File DLL) per l'utilizzo della piattaforma desktop di Windows, scegliere la libreria F #. Per creare una libreria portatile che può essere usata in qualsiasi piattaforma supportata, scegliere libreria portabile F #. Progetti libreria portabile F # fare riferimento a una versione di FSharp.Core.dll appropriate creare una libreria F # che può essere utilizzata con le applicazioni eseguite su piattaforme, ad esempio applicazioni Windows Store, .NET Framework 4.5, xamarin. IOS e xamarin.

Per ulteriori informazioni sui modelli di elemento per l'accesso ai dati, vedere [provider di tipi](../tutorials/type-providers/index.md).

Nella tabella seguente sono riepilogate le funzionalità delle proprietà di progetto supportati e non supportate in F #. Per ulteriori informazioni, vedere [configurazione progetti](configuring-projects.md) e [Introduzione a Progettazione progetti](https://msdn.microsoft.com/library/898dd854-c98d-430c-ba1b-a913ce3c73d7).

|Impostazione di progetto|Supportate in F #?|Note|
|---------------|----------------|-----|
|File di risorse|Yes||
|Compilazione, debug e le impostazioni di riferimento|Yes||
|Multitargeting|Yes||
|Icona e manifesto|No|Disponibile tramite le opzioni della riga di comando del compilatore.|
|Servizi Client ASP.NET|No||
|ClickOnce|No|Utilizzare un progetto client in un altro linguaggio .NET Framework, se applicabile.|
|Denominazione sicura|No|Disponibile tramite le opzioni della riga di comando del compilatore.|
|Assembly di pubblicazione e il controllo delle versioni|No||
|Analisi codice|No|Strumenti di analisi codice possono essere eseguiti manualmente o come parte di un comando di post-compilazione.|
|Sicurezza (modificare i livelli di attendibilità)|No||

## <a name="code-and-text-editor-features"></a>Codice e le funzionalità dell'Editor di testo
Le caratteristiche seguenti del Visual Studiocode ed editor di testo sono supportate in F #. Per informazioni generali sulla modifica del codice in Visual Studio e le funzionalità dell'editor di testo, vedere [scrittura di codice nell'Editor di testo e del codice](/visualstudio/ide/writing-code-in-the-code-and-text-editor).

|Funzionalità|Descrizione|Supportate in F #?|
|-------|-----------|----------------|
|Commento automaticamente|Consente di inviare commenti o rimuovere il commento di sezioni di codice.|Sì|
|Formatta automaticamente|Riformatta il codice con rientro e stile standard.|No|
|Segnalibri|Consente di salvare posizioni nell'editor.|Yes|
|Modificare il rientro|Applicare i rientri o riduce il rientro delle righe selezionate.|Yes|
|[Ricerca e sostituzione di testo](/visualstudio/ide/finding-and-replacing-text)|Consente di eseguire la ricerca in un file, un progetto o soluzione e potenzialmente modificare testo.|Yes|
|Passare alla definizione dell'API di .NET Framework|Quando il cursore è posizionato su un'API di .NET Framework, Mostra il codice generato dai metadati di .NET Framework.|No|
|Passare alla definizione dell'API definita dall'utente|Quando il cursore si trova su un'entità di programma che è definito, sposta il cursore nella posizione nel codice in cui l'entità è definita.|Yes|
|Vai alla riga|Consente di passare a una riga specifica in un file, dal numero di riga.|Yes|
|Barre di navigazione nella parte superiore del file|Consente di passare a posizioni nel codice, da, ad esempio, il nome di funzione.|Yes|
|Struttura Vedere [struttura](/visualstudio/ide/outlining).|Consente di comprimere le sezioni del codice per creare una visualizzazione più compatta.|Yes|
|Inserimento di tabulazioni|Converte gli spazi in tabulazioni.|Yes|
|Colorazione dei tipi|Mostra definiti i nomi dei tipi in un colore speciale.|Yes|
|Ricerca veloce. Vedere Ricerca veloce, finestra Trova e sostituisci.|Consente di eseguire ricerche in un file o progetto.|Yes|

## <a name="intellisense-features"></a>Funzionalità di IntelliSense
Nella tabella seguente sono riepilogate le funzionalità di IntelliSense supportate e non supportate in F #. Per informazioni generali su IntelliSense, vedere [utilizzando IntelliSense](/visualstudio/ide/using-intellisense).

|Funzionalità|Descrizione|Supportate in F #?|
|-------|-----------|----------------|
|Implementazione automatica delle interfacce|Genera stub di codice per i metodi di interfaccia.|No|
|Frammenti di codice|Inserisce codice da una libreria di costrutti di codice comuni in argomenti.|No|
|Completa parola|Consente di risparmiare completando le parole e i nomi durante la digitazione.|Yes|
|Modalità di terminazione primo utilizzo|Quando abilitata, consente al completamento della parola di selezionare la prima corrispondenza durante la digitazione, anziché attendere che è possibile selezionare uno o premere **CTRL + BARRA SPAZIATRICE**.|No|
|Generazione di elementi di codice|Consente di generare stub di codice per un'ampia gamma di costrutti.|No|
|Elenca membri|Quando si digita l'operatore di accesso ai membri (.), Visualizza i membri per un tipo.|Yes|
|Organizzare direttive using/Apri|Organizza gli spazi dei nomi a cui fa riferimento **utilizzando** istruzioni in c# o **aprire** direttive in F #.|No|
|Informazioni sul parametro|Mostra informazioni utili sui parametri durante la digitazione di una chiamata di funzione.|Yes|
|Informazioni rapide|Visualizza la dichiarazione completa per qualsiasi identificatore nel codice.|Yes|
Refactoring del codice F # non è supportato in Visual Studio 2012.

## <a name="debugging-features"></a>Funzionalità di debug
Nella tabella seguente vengono riepilogate le funzionalità sono disponibili quando si esegue il debug del codice F #. Per informazioni generali sul debugger di Visual Studio, vedere [debug in Visual Studio](https://msdn.microsoft.com/library/sc65sadd.aspx).

|Funzionalità|Descrizione|Supportate in F #?|
|-------|-----------|----------------|
|Auto (finestra)|Mostra le variabili automatiche o temporanee.|No|
|Punti di interruzione|Consente di sospendere l'esecuzione di codice in punti specifici durante il debug.|Yes|
|Punti di interruzione condizionali|Abilita i punti di interruzione che una condizione che determina se deve interrompere l'esecuzione di test.|Yes|
|Modifica e continuazione|Consente al codice di essere modificato e compilato come si esegue il debug di un programma in esecuzione senza arrestare e riavviare il debugger.|No|
|Analizzatore di espressioni|Valuta e l'esecuzione di codice in fase di esecuzione.|No, ma c# analizzatore di espressioni può essere utilizzato, anche se è necessario utilizzare sintassi di c#.|
|Il debug cronologico|Consente di eseguire codice eseguita in precedenza.|Yes|
|Finestra Variabili locali|Mostra localmente definiti valori e variabili.|Yes|
|Esecuzione fino al cursore|Consente di eseguire il codice fino a quando non viene raggiunta la riga che contiene il cursore.|Yes|
|Esegui istruzione|Consente di spostare l'esecuzione e spostare in qualsiasi chiamata di funzione.|Yes|
|Esegui istruzione/routine|Consente di spostare l'esecuzione nello stack frame corrente e spostarsi oltre qualsiasi chiamata di funzione.|Yes|

## <a name="additional-tools"></a>Strumenti aggiuntivi
Nella tabella seguente viene riepilogato il supporto per F # in strumenti di Visual Studio.

|Strumento|Descrizione|Supportate in F #?|
|----|-----------|----------------|
|Gerarchia di chiamata|Consente di visualizzare la struttura annidata della funzione chiamate nel codice.|No|
|Metrica del codice|Raccoglie informazioni sul codice, ad esempio il numero di righe.|No|
|Visualizzazione classi|Fornisce una visualizzazione basata sul tipo di codice in un progetto.|No|
|[Finestra Elenco errori](/visualstudio/ide/reference/error-list-window)|Mostra un elenco di errori nel codice.|Yes|
|[F# Interactive](../tutorials/fsharp-interactive/index.md)|Consente di digitare (o copiare e incollare) F # del codice e di eseguirlo immediatamente, indipendentemente dalla compilazione del progetto. La finestra di F # Interactive è un Read, Evaluate, Print Loop (REPL).|Yes|
|Visualizzatore oggetti|Consente di visualizzare i tipi in un assembly.|Tipi F # come appaiono in assembly compilati non vengono visualizzati esattamente come si creano. È possibile esplorare la rappresentazione compilata di tipi F #, ma non è possibile visualizzare i tipi di come vengono visualizzati da F #.|
|[Finestra di output](/visualstudio/ide/reference/output-window)|Consente di visualizzare l'output di compilazione.|Yes|
|Analisi delle prestazioni|Fornisce strumenti per misurare le prestazioni del codice.|Yes|
|Finestra Proprietà|Visualizza e consente la modifica di proprietà dell'oggetto nell'ambiente di sviluppo che ha lo stato attivo.|Yes|
|[Esplora server](https://msdn.microsoft.com/library/x603htbk.aspx)|Fornisce metodi per interagire con un'ampia gamma di risorse del server.|Yes|
|Esplora soluzioni|Consente di visualizzare e gestire progetti e file.|Yes|
|Elenco attività|Consente di gestire gli elementi di lavoro relativi al codice.|Yes|
|Progetti di test|Fornisce funzionalità che consentono di testare il codice.|No|
|Casella degli strumenti|Visualizza le schede che contengono oggetti draggable, ad esempio i controlli e sezioni di testo o codice.|Yes|

## <a name="see-also"></a>Vedere anche
 [Introduzione a F # in Visual Studio](../get-started/get-started-visual-studio.md)  
 [Configurazione di progetti](configuring-projects.md)  
