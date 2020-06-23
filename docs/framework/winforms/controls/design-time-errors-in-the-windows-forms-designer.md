---
title: Errori della fase di progettazione nel Progettazione Windows Form
titleSuffix: ''
description: Informazioni sugli errori che si verificano quando non è possibile caricare il Progettazione Windows Form a causa di un errore nel codice, in un componente di terze parti o in un'altra posizione.
ms.date: 09/09/2019
f1_keywords:
- DTELErrorList
- WhyDTELPage
helpviewer_keywords:
- errors [Windows Forms Designer]
- design-time errors [Windows Forms Designer]
ms.assetid: ad408380-825a-46d8-9a4a-531b130b88ce
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: d9c3993dfce9312c3271c499b6c0cd0c11253ca8
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904390"
---
# <a name="windows-forms-designer-error-page"></a>Pagina di errore Progettazione Windows Form

Se il Progettazione Windows Form non viene caricato a causa di un errore nel codice, in un componente di terze parti o altrove, viene visualizzata una pagina di errore anziché la finestra di progettazione. Questa pagina di errore non indica necessariamente un bug nella finestra di progettazione. Il bug potrebbe trovarsi in un punto qualsiasi della pagina code-behind denominata \<your-form-name> . Designer.cs. Gli errori vengono visualizzati nelle barre gialle comprimibili con un collegamento per passare alla posizione dell'errore nella tabella codici.

![Pagina di errore Progettazione Windows Form](media/windows-forms-designer-error-page-collapsed.png)

È possibile scegliere di ignorare gli errori e continuare a caricare la finestra di progettazione facendo clic su **Ignora e continua**. Questa azione può causare un comportamento imprevisto, ad esempio, i controlli potrebbero non essere visualizzati nell'area di progettazione.

## <a name="instances-of-this-error"></a>Istanze dell'errore

Quando la barra di errore gialla viene espansa, viene elencata ogni istanza dell'errore. Molti tipi di errore includono un percorso esatto nel formato seguente: *[nome progetto]* *[nome modulo]* riga:*[numero riga]* colonna:*[numero colonna]*. Se allo stack di chiamate è associato un errore, è possibile fare clic sul collegamento **Mostra stack di chiamate** per visualizzarlo. Esaminare lo stack di chiamate può essere utile per risolvere l'errore.

![Errore Progettazione Windows Form espanso](media/windows-forms-designer-error-page-expanded.png)

> [!NOTE]
>
> - Per Visual Basic App, nella pagina di errore della fase di progettazione non viene visualizzato più di un errore, ma è possibile che vengano visualizzate più istanze dello stesso errore.
> - Per le app C++, gli errori non hanno collegamenti per la posizione del codice.

## <a name="help-with-this-error"></a>Supporto per l'errore

Se è disponibile un argomento della Guida per l'errore, fare clic sul collegamento alla **Guida MSDN** per passare direttamente alla pagina della guida in docs.Microsoft.com.

## <a name="forum-posts-about-this-error"></a>Post dei forum sull'errore

Fare clic sul collegamento **Cerca nei forum MSDN per i post correlati a questo errore** per accedere ai forum di Microsoft Developer Network. Si consiglia di cercare in modo specifico i forum [Progettazione Windows Form](https://social.msdn.microsoft.com/Forums/windows/home?forum=winformsdesigner) o [Windows Forms](https://social.msdn.microsoft.com/Forums/windows/home?category=windowsforms) .

## <a name="design-time-errors"></a>Errori in fase di progettazione

In questa sezione vengono elencati alcuni degli errori che possono verificarsi.

### <a name="identifier-name-is-not-a-valid-identifier"></a>' \<identifier name> ' non è un identificatore valido

Questo errore indica che un campo, un metodo, un evento o un oggetto non è stato denominato correttamente.

### <a name="name-already-exists-in-project-name"></a>' \<name> ' esiste già in ' \<project name> '

Messaggio di errore: "'' \<name> esiste già in ' \<project name> '. Immettere un nome univoco. "

È stato specificato un nome per un form ereditato già esistente nel progetto. Per correggere l'errore, assegnare al form ereditato un nome univoco.

### <a name="toolbox-tab-name-is-not-a-toolbox-category"></a>' \<Toolbox tab name> ' non è una categoria di casella degli strumenti

Un progettista di terze parti ha tentato di accedere a una scheda della casella degli strumenti che non esiste. Contattare il fornitore del componente.

### <a name="a-requested-language-parser-is-not-installed"></a>Uno dei parser di linguaggio necessari non è installato

Messaggio di errore: "un parser di linguaggio richiesto non è installato. Il nome del parser del linguaggio è' {0} '.

Visual Studio ha tentato di caricare una finestra di progettazione registrata per il tipo di file. Probabilmente a causa di un errore che si è verificato durante l'installazione. Contattare il fornitore della lingua utilizzata per una correzione.

### <a name="a-service-required-for-generating-and-parsing-source-code-is-missing"></a>Un servizio necessario per la generazione e l'analisi del codice sorgente risulta mancante

Si tratta di un problema con un componente di terze parti. Contattare il fornitore del componente.

### <a name="an-exception-occurred-while-trying-to-create-an-instance-of-object-name"></a>Si è verificata un'eccezione durante il tentativo di creare un'istanza di ' \<object name> '

Messaggio di errore: "si è verificata un'eccezione durante il tentativo di creare un'istanza di ' \<object name> '. L'eccezione è " \<exception string\> ".

Un progettista di terze parti ha richiesto che Visual Studio crei un oggetto, ma l'oggetto ha generato un errore. Contattare il fornitore del componente.

### <a name="another-editor-has-document-name-open-in-an-incompatible-mode"></a>Il '' è \<document name> aperto in un altro editor in una modalità incompatibile

Messaggio di errore: "un altro editor ha ' \<document name> ' aperto in una modalità incompatibile. Chiudere l'editor, quindi ripetere l'operazione ".

Questo errore si verifica se si tenta di aprire un file già aperto in un altro editor. Viene visualizzato l'editor che ha già aperto il file. Per correggere l'errore, chiudere l'editor in cui è aperto il file e riprovare.

### <a name="another-editor-has-made-changes-to-document-name"></a>In un altro editor sono state apportate modifiche a' \<document name> '

Chiudere e riaprire la finestra di progettazione per rendere effettive le modifiche. In genere, Visual Studio ricarica automaticamente una finestra di progettazione dopo aver apportato le modifiche. Tuttavia, altre finestre di progettazione, ad esempio le finestre di progettazione dei componenti di terze parti, potrebbero non supportare il comportamento di ricaricamento. In questo caso, Visual Studio richiede la chiusura e la riapertura manuale della finestra di progettazione.

### <a name="another-editor-has-the-file-open-in-an-incompatible-mode"></a>Il file è aperto in un altro editor in una modalità incompatibile

Messaggio di errore: "un altro editor ha il file aperto in una modalità incompatibile. Chiudere l'editor, quindi ripetere l'operazione ".

Questo messaggio è simile a "un altro editor è \<document name> aperto in una modalità incompatibile", ma Visual Studio non è in grado di determinare il nome del file. Per correggere l'errore, chiudere l'editor in cui è aperto il file e riprovare.

### <a name="array-rank-rank-in-array-is-too-high"></a>La classificazione della matrice ' \<rank in array> ' è troppo alta

Visual Studio supporta solo matrici unidimensionali nel blocco di codice analizzato dalla finestra di progettazione. Le matrici multidimensionali sono valide all'esterno di questa area.

### <a name="assembly-assembly-name-could-not-be-opened"></a>\<assembly name>Non è stato possibile aprire l'assembly ''

Messaggio di errore: Impossibile aprire l'assembly ' \<assembly name> '. Verificare che il file esista ancora ".

Questo messaggio di errore si verifica quando si tenta di aprire un file che non può essere aperto. Verificare che il file esista e che sia un assembly valido.

### <a name="bad-element-type-this-serializer-expects-an-element-of-type-type-name"></a>Tipo di elemento non valido. Questo serializzatore prevede un elemento di tipo ' \<type name> '

Si tratta di un problema con un componente di terze parti. Contattare il fornitore del componente.

### <a name="cannot-access-the-visual-studio-toolbox-at-this-time"></a>Impossibile accedere ora alla Casella degli strumenti di Visual Studio

Visual Studio ha effettuato una chiamata alla casella degli strumenti, che non era disponibile. Se viene visualizzato questo errore, se viene visualizzato questo errore, registrare un problema usando [segnala un problema](/visualstudio/ide/how-to-report-a-problem-with-visual-studio).

### <a name="cannot-bind-an-event-handler-to-the-event-name-event-because-it-is-read-only"></a>Impossibile associare un gestore eventi all'evento ' \<event name> ' perché è di sola lettura

Questo errore si verifica più spesso quando si tenta di connettere un evento a un controllo ereditato da una classe base. Se la variabile membro del controllo è privata, Visual Studio non è in grado di connettere l'evento al metodo. I controlli ereditati privatamente non possono avere eventi aggiuntivi associati.

### <a name="cannot-create-a-method-name-for-the-requested-component-because-it-is-not-a-member-of-the-design-container"></a>Impossibile creare un nome di metodo per il componente richiesto perché non è un membro del contenitore di progettazione

Visual Studio ha tentato di aggiungere un gestore eventi a un componente che non ha una variabile membro nella finestra di progettazione. Contattare il fornitore del componente.

### <a name="cannot-name-the-object-name-because-it-is-already-named-name"></a>Non è possibile assegnare un nome all'oggetto ' \<name> ' perché è già denominato ' \<name> '

Si tratta di un errore interno del serializzatore di Visual Studio. Indica che il serializzatore ha tentato di assegnare un nome a un oggetto due volte, che non è supportato. Se viene visualizzato questo errore, registrare un problema usando [segnala un problema](/visualstudio/ide/how-to-report-a-problem-with-visual-studio).

### <a name="cannot-remove-or-destroy-inherited-component-component-name"></a>Impossibile rimuovere o eliminare definitivamente il componente ereditato ' \<component name> '

I controlli ereditati sono sottoposti alla proprietà della relativa classe ereditata. Le modifiche al controllo ereditato devono essere apportate nella classe da cui ha origine il controllo. Pertanto, non è possibile rinominarlo o eliminarlo definitivamente.

### <a name="category-toolbox-tab-name-does-not-have-a-tool-for-class-class-name"></a>La categoria ' \<Toolbox tab name> ' non dispone di uno strumento per la classe ' \<class name> '

La finestra di progettazione ha tentato di fare riferimento a una classe in una particolare scheda della casella degli strumenti, ma la classe non esiste. Contattare il fornitore del componente.

### <a name="class-class-name-has-no-matching-constructor"></a>La classe ' \<class name> ' non ha un costruttore corrispondente

Un progettista di terze parti ha chiesto a Visual Studio di creare un oggetto con determinati parametri nel costruttore che non esiste. Contattare il fornitore del componente.

### <a name="code-generation-for-property-property-name-failed"></a>Generazione del codice per la proprietà' \<property name> ' non riuscita

Si tratta di un wrapper generico per un errore. La stringa di errore che accompagna questo messaggio fornirà ulteriori dettagli sul messaggio di errore e avrà un collegamento a un argomento della guida più specifico. Per correggere l'errore, risolvere l'errore specificato nel messaggio di errore accodato all'errore.

### <a name="component-component-name-did-not-call-containeradd-in-its-constructor"></a>Il componente ' \<component name> ' non ha chiamato container. Add () nel relativo costruttore

Si tratta di un errore nel componente appena caricato o inserito nel form. Indica che il componente non è stato aggiunto al relativo controllo contenitore (se si tratta di un altro controllo o di un modulo). La finestra di progettazione continuerà a funzionare, ma potrebbero verificarsi problemi con il componente in fase di esecuzione.

Per correggere l'errore, contattare il fornitore del componente. In alternativa, se si tratta di un componente creato, chiamare il `IContainer.Add` metodo nel costruttore del componente.

### <a name="component-name-cannot-be-empty"></a>Il nome di un componente non può essere vuoto

Questo errore si verifica quando si tenta di rinominare un componente in un valore vuoto.

### <a name="could-not-access-the-variable-variable-name-because-it-has-not-been-initialized-yet"></a>Non è stato possibile accedere alla variabile ' \<variable name> ' perché non è ancora stata inizializzata

Questo errore può verificarsi a causa di due scenari. Un fornitore di componenti di terze parti presenta un problema con un controllo o un componente che ha distribuito oppure il codice scritto presenta dipendenze ricorsive tra i componenti.

Per correggere l'errore, verificare che il codice non disponga di una dipendenza ricorsiva. Se questi problemi non sono disponibili, prendere nota del testo esatto del messaggio di errore e contattare il fornitore del componente.

### <a name="could-not-find-type-type-name"></a>Il tipo '' non è stato trovato \<type name>

Messaggio di errore: "Impossibile trovare il tipo ' \<type name> '. Assicurarsi che venga fatto riferimento all'assembly che contiene il tipo. Se questo tipo è una parte del progetto di sviluppo, verificare che il progetto sia stato compilato correttamente. "

Questo errore si è verificato perché non è stato trovato un riferimento. Assicurarsi che venga fatto riferimento al tipo indicato nel messaggio di errore e che venga fatto riferimento anche agli assembly richiesti dal tipo. Spesso, il problema è che un controllo nella soluzione non è stato compilato. Per compilare, scegliere **Compila soluzione** dal menu **Compila** . In caso contrario, se il controllo è già stato compilato, aggiungere manualmente un riferimento dal menu di scelta rapida della cartella **riferimenti** o **dipendenze** in Esplora soluzioni.

### <a name="could-not-load-type-type-name"></a>Non è stato possibile caricare il tipo ' \<type name> '

Messaggio di errore: "Impossibile caricare il tipo ' \<type name> '. Assicurarsi che l'assembly contenente questo tipo venga aggiunto ai riferimenti del progetto ".

Visual Studio ha tentato di collegare un metodo di gestione degli eventi e non è stato possibile trovare uno o più tipi di parametro per il metodo. Questo problema è in genere causato da un riferimento mancante. Per correggere l'errore, aggiungere al progetto il riferimento contenente il tipo e riprovare.

### <a name="could-not-locate-the-project-item-templates-for-inherited-components"></a>Impossibile trovare i modelli degli elementi del progetto per i componenti ereditati

I modelli per i moduli ereditati in Visual Studio non sono disponibili. Se viene visualizzato questo errore, registrare un problema usando [segnala un problema](/visualstudio/ide/how-to-report-a-problem-with-visual-studio).

### <a name="delegate-class-class-name-has-no-invoke-method-is-this-class-a-delegate"></a>La classe delegata ' \<class name> ' non ha un metodo Invoke. Questa classe è un delegato?

Visual Studio ha tentato di creare un gestore eventi, ma si è verificato un errore nel tipo di evento. Questo problema può verificarsi se l'evento è stato creato da un linguaggio non conforme a CLS. Contattare il fornitore del componente.

### <a name="duplicate-declaration-of-member-member-name"></a>Dichiarazione duplicata del membro ' \<member name> '

Questo errore si verifica perché una variabile membro è stata dichiarata due volte, ad esempio due controlli denominati `Button1` sono dichiarati nel codice. I nomi devono essere univoci tra i form ereditati. Inoltre, i nomi non possono differire solo per maiuscole/minuscole.

### <a name="error-reading-resources-from-the-resource-file-for-the-culture-culture-name"></a>Errore durante la lettura delle risorse dal file di risorse per le impostazioni cultura ' \<culture name> '

Questo errore può verificarsi se nel progetto è presente un file con estensione resx non valido.

Per correggere questo errore:

1. Fare clic sul pulsante **Mostra tutti i file** in Esplora soluzioni per visualizzare i file con estensione resx associati alla soluzione.
2. Caricare il file con estensione resx nell'editor XML facendo clic con il pulsante destro del mouse sul file con estensione resx e scegliendo **Apri**.
3. Modificare il file con estensione resx manualmente per risolvere gli errori.

### <a name="error-reading-resources-from-the-resource-file-for-the-default-culture-culture-name"></a>Errore durante la lettura delle risorse dal file di risorse per le impostazioni cultura predefinite ' \<culture name> '

Questo errore può verificarsi se nel progetto è presente un file con estensione resx non valido per le impostazioni cultura predefinite.

Per correggere questo errore:

1. Fare clic sul pulsante **Mostra tutti i file** in Esplora soluzioni per visualizzare i file con estensione resx associati alla soluzione.
2. Caricare il file con estensione resx nell'editor XML facendo clic con il pulsante destro del mouse sul file con estensione resx e scegliendo **Apri**.
3. Modificare il file con estensione resx manualmente per risolvere gli errori.

### <a name="failed-to-parse-method-method-name"></a>Non è stato possibile analizzare il metodo ' \<method name> '

Messaggio di errore: "non è stato possibile analizzare il metodo ' \<method name> '. Il parser ha segnalato l'errore seguente:' \<error string> '. Esaminare la Elenco attività per individuare eventuali errori. "

Si tratta di un messaggio di errore generale per i problemi che si verificano durante l'analisi. Questi errori sono spesso causati da errori di sintassi. Per i messaggi specifici correlati all'errore, vedere la Elenco attività.

### <a name="invalid-component-name-component-name"></a>Nome componente non valido:' \<component name> '

Si è provato a rinominare un componente in un valore non valido per tale lingua. Per correggere l'errore, denominare il componente in modo che sia conforme alle regole di denominazione per tale lingua.

### <a name="the-type-class-name-is-made-of-several-partial-classes-in-the-same-file"></a>Il tipo ' \<class name> ' è costituito da diverse classi parziali nello stesso file

Quando si definisce una classe in più file usando la parola chiave [partial](../../../csharp/language-reference/keywords/partial-type.md) , è possibile avere una sola definizione parziale in ogni file.

Per correggere l'errore, rimuovere tutte le definizioni parziali della classe tranne una per il file.

### <a name="the-assembly-assembly-name-could-not-be-found"></a>Impossibile trovare l'assembly ' \<assembly name> '

Messaggio di errore: "l'assembly ' \<assembly name> ' non è stato trovato. Verificare che venga fatto riferimento all'assembly. Se l'assembly fa parte del progetto di sviluppo corrente, verificare che il progetto sia stato compilato ".

Questo errore è simile a "il tipo ' \<type name> ' non è stato trovato", ma questo errore si verifica in genere a causa di un attributo di metadati. Per correggere l'errore, verificare che venga fatto riferimento a tutti gli assembly utilizzati dagli attributi.

### <a name="the-assembly-name-assembly-name-is-invalid"></a>Il nome dell'assembly ' \<assembly name> ' non è valido

Un componente ha richiesto un assembly specifico, ma il nome fornito dal componente non è un nome di assembly valido. Contattare il fornitore del componente.

### <a name="the-base-class-class-name-cannot-be-designed"></a>\<class name>Non è possibile progettare la classe base ''

Visual Studio ha caricato la classe, ma la classe non può essere progettata perché l'implementatore della classe non ha fornito una finestra di progettazione. Se la classe supporta una finestra di progettazione, assicurarsi che non vi siano problemi che potrebbero causare problemi di visualizzazione in una finestra di progettazione, ad esempio errori del compilatore. Assicurarsi inoltre che tutti i riferimenti alla classe siano corretti e che tutti i nomi delle classi siano stati digitati correttamente. In caso contrario, se la classe non è progettabile, modificarla nella visualizzazione codice.

### <a name="the-base-class-class-name-could-not-be-loaded"></a>\<class name>Non è stato possibile caricare la classe di base ''

Non è possibile fare riferimento alla classe nel progetto, quindi Visual Studio non è in grado di caricarla. Per correggere l'errore, aggiungere un riferimento alla classe nel progetto, quindi chiudere e riaprire la finestra di Progettazione Windows Form.

### <a name="the-class-class-name-cannot-be-designed-in-this-version-of-visual-studio"></a>\<class name>Non è possibile progettare la classe '' in questa versione di Visual Studio

La finestra di progettazione per questo controllo o componente non supporta gli stessi tipi di Visual Studio. Contattare il fornitore del componente.

### <a name="the-class-name-is-not-a-valid-identifier-for-this-language"></a>Il nome della classe non è un identificatore valido per questo linguaggio

Il codice sorgente creato dall'utente ha un nome di classe non valido per il linguaggio in uso. Per correggere l'errore, denominare la classe in modo che sia conforme ai requisiti della lingua.

### <a name="the-component-cannot-be-added-because-it-contains-a-circular-reference-to-reference-name"></a>Impossibile aggiungere il componente perché contiene un riferimento circolare a' \<reference name> '

Non è possibile aggiungere un controllo o un componente a se stesso. Un'altra situazione in cui questo potrebbe verificarsi è la presenza di codice nel metodo InitializeComponent di un form, ad esempio Form1, per la creazione di un'altra istanza di Form1.

### <a name="the-designer-cannot-be-modified-at-this-time"></a>Impossibile modificare ora la finestra di progettazione

Questo errore si verifica quando il file nell'editor è contrassegnato come di sola lettura. Verificare che il file non sia contrassegnato come di sola lettura e che l'applicazione non sia in esecuzione.

### <a name="the-designer-could-not-be-shown-for-this-file-because-none-of-the-classes-within-it-can-be-designed"></a>Impossibile visualizzare la finestra di progettazione per il file, perché nessuna delle classi contenute può essere progettata

Questo errore si verifica quando Visual Studio non è in grado di trovare una classe di base che soddisfi i requisiti di progettazione. I form e i controlli devono derivare da una classe base che supporta le finestre di progettazione. Se si esegue la derivazione da un form o un controllo ereditato, verificare che il progetto sia stato compilato.

### <a name="the-designer-for-base-class-class-name-is-not-installed"></a>La finestra di progettazione per la classe base ' \<class name> ' non è installata

Visual Studio non è riuscito a caricare la finestra di progettazione per la classe. Se viene visualizzato questo errore, registrare un problema usando [segnala un problema](/visualstudio/ide/how-to-report-a-problem-with-visual-studio).

### <a name="the-designer-must-create-an-instance-of-type-type-name-but-it-cant-because-the-type-is-declared-as-abstract"></a>La finestra di progettazione deve creare un'istanza di tipo ' \<type name> ', ma non può perché il tipo è dichiarato come abstract

Questo errore si è verificato perché la classe di base dell'oggetto passato alla finestra di progettazione è [astratta](../../../csharp/language-reference/keywords/abstract.md), che non è consentita.

### <a name="the-file-could-not-be-loaded-in-the-designer"></a>Impossibile caricare il file nella finestra di progettazione

La classe base di questo file non supporta le finestre di progettazione. Come soluzione alternativa, usare la visualizzazione codice per lavorare sul file. Fare clic con il pulsante destro del mouse sul file in Esplora soluzioni e scegliere **Visualizza codice**.

### <a name="the-language-for-this-file-does-not-support-the-necessary-code-parsing-and-generation-services"></a>Il linguaggio del file non supporta i servizi di analisi e generazione del codice necessari

Messaggio di errore: "la lingua del file non supporta i servizi di analisi e generazione del codice necessari. Verificare che il file che si sta aprendo sia un membro di un progetto, quindi riprovare ad aprire il file ".

Questo errore ha probabilmente causato l'apertura di un file che si trova in un progetto che non supporta le finestre di progettazione.

### <a name="the-language-parser-class-class-name-is-not-implemented-properly"></a>La classe '' del parser del linguaggio \<class name> non è implementata correttamente

Messaggio di errore: "la classe del parser del linguaggio ' \<class name> ' non è implementata correttamente. Contattare il fornitore per un modulo parser aggiornato ".

La lingua in uso ha registrato una classe della finestra di progettazione che non deriva dalla classe di base corretta. Contattare il fornitore del linguaggio in uso.

### <a name="the-name-name-is-already-used-by-another-object"></a>Il nome ' \<name> ' è già usato da un altro oggetto

Si tratta di un errore interno del serializzatore di Visual Studio. Se viene visualizzato questo errore, registrare un problema usando [segnala un problema](/visualstudio/ide/how-to-report-a-problem-with-visual-studio).

### <a name="the-object-object-name-does-not-implement-the-icomponent-interface"></a>L'oggetto ' \<object name> ' non implementa l'interfaccia IComponent

Visual Studio ha tentato di creare un componente, ma l'oggetto creato non implementa l' <xref:System.ComponentModel.IComponent> interfaccia. Contattare il fornitore del componente per una correzione.

### <a name="the-object-object-name-returned-null-for-the-property-property-name-but-this-is-not-allowed"></a>L'oggetto ' \<object name> ' ha restituito null per la proprietà' \<property name> ', ma questa operazione non è consentita

Sono disponibili alcune proprietà .NET che devono sempre restituire un oggetto. Ad esempio, la raccolta di **controlli** di un form deve sempre restituire un oggetto, anche quando non sono presenti controlli.

Per correggere l'errore, verificare che la proprietà specificata nell'errore non sia null.

### <a name="the-serialization-data-object-is-not-of-the-proper-type"></a>Il tipo dell'oggetto dati di serializzazione non è corretto

Un oggetto dati offerto dal serializzatore non è un'istanza di un tipo che corrisponde al serializzatore corrente in uso. Contattare il fornitore del componente.

### <a name="the-service-service-name-is-required-but-could-not-be-located"></a>Il servizio ' \<service name> ' è obbligatorio, ma non è stato possibile individuarlo

Messaggio di errore: "il servizio ' \<service name> ' è obbligatorio, ma non è stato trovato. Potrebbe essersi verificato un problema con l'installazione di Visual Studio. "

Un servizio richiesto da Visual Studio non è disponibile. Se si sta provando a caricare un progetto che non supporta tale finestra di progettazione, usare l'editor di codice per apportare le modifiche necessarie. In caso contrario, se viene visualizzato questo errore, registrare un problema usando [segnala un problema](/visualstudio/ide/how-to-report-a-problem-with-visual-studio).

### <a name="the-service-instance-must-derive-from-or-implement-interface-name"></a>L'istanza del servizio deve derivare da o implementare ' \<interface name> '

Questo errore indica che la finestra di progettazione di un componente o di un componente ha chiamato il metodo **AddService** , che richiede un'interfaccia e un oggetto, ma l'oggetto specificato non implementa l'interfaccia specificata. Contattare il fornitore del componente.

### <a name="the-text-in-the-code-window-could-not-be-modified"></a>Impossibile modificare il testo nella finestra del codice

Messaggio di errore: "Impossibile modificare il testo nella finestra del codice. Verificare che il file non sia di sola lettura e che lo spazio su disco sia sufficiente. "

Questo errore si verifica quando Visual Studio non è in grado di modificare un file a causa di problemi di memoria o di spazio su disco oppure il file è contrassegnato come di sola lettura.

### <a name="the-toolbox-enumerator-object-only-supports-retrieving-one-item-at-a-time"></a>L'oggetto enumeratore della Casella degli strumenti supporta solo il recupero di un elemento alla volta

Se viene visualizzato questo errore, se viene visualizzato questo errore, registrare un problema usando [segnala un problema](/visualstudio/ide/how-to-report-a-problem-with-visual-studio).

### <a name="the-toolbox-item-for-component-name-could-not-be-retrieved-from-the-toolbox"></a>Impossibile recuperare l'elemento della casella degli strumenti per ' \<component name> ' dalla casella degli strumenti

Messaggio di errore: "Impossibile recuperare l'elemento della casella degli strumenti per ' \<component name> ' dalla casella degli strumenti. Verificare che l'assembly che contiene l'elemento della casella degli strumenti sia installato correttamente. L'elemento della casella degli strumenti ha generato il seguente errore: \<error string> . "

Il componente in questione ha generato un'eccezione durante l'accesso a Visual Studio. Contattare il fornitore del componente.

### <a name="the-toolbox-item-for-toolbox-item-name-could-not-be-retrieved-from-the-toolbox"></a>Impossibile recuperare l'elemento della casella degli strumenti per ' \<Toolbox item name> ' dalla casella degli strumenti

Messaggio di errore: "Impossibile recuperare l'elemento della casella degli strumenti per ' \<Toolbox item name> ' dalla casella degli strumenti. Provare a rimuovere l'elemento dalla casella degli strumenti e aggiungerlo di nuovo. "

Questo errore si verifica se i dati all'interno dell'elemento della casella degli strumenti risultano danneggiati o la versione del componente è stata modificata. Provare a rimuovere l'elemento dalla casella degli strumenti e aggiungerlo di nuovo.

### <a name="the-type-type-name-could-not-be-found"></a>Il tipo ' \<type name> ' non è stato trovato

Messaggio di errore: "Impossibile trovare il tipo ' \<type name> '. Verificare che venga fatto riferimento all'assembly contenente il tipo. Se l'assembly fa parte del progetto di sviluppo corrente, verificare che il progetto sia stato compilato ".

Durante il caricamento della finestra di progettazione, Visual Studio non è riuscito a trovare un tipo. Verificare che venga fatto riferimento all'assembly contenente il tipo. Se l'assembly fa parte del progetto di sviluppo corrente, verificare che il progetto sia stato compilato.

### <a name="the-type-resolution-service-may-only-be-called-from-the-main-application-thread"></a>Il servizio di risoluzione del tipo può essere chiamato solo dal thread dell'applicazione principale

Visual Studio ha tentato di accedere alle risorse necessarie dal thread errato. Questo errore viene visualizzato quando il codice usato per creare la finestra di progettazione ha chiamato il servizio di risoluzione del tipo da un thread diverso dal thread dell'applicazione principale. Per correggere l'errore, chiamare il servizio dal thread corretto o contattare il fornitore del componente.

### <a name="the-variable-variable-name-is-either-undeclared-or-was-never-assigned"></a>La variabile ' \<variable name> ' non è dichiarata o non è mai stata assegnata

Il codice sorgente contiene un riferimento a una variabile, ad esempio **Button1**, che non è dichiarata o assegnata. Se la variabile non è stata assegnata, questo messaggio appare come un avviso, non come un errore.

### <a name="there-is-already-a-command-handler-for-the-menu-command-menu-command-name"></a>Esiste già un gestore comando per il comando di menu ' \<menu command name> '

Questo errore si verifica se un progettista di terze parti aggiunge un comando che dispone già di un gestore alla tabella dei comandi. Contattare il fornitore del componente.

### <a name="there-is-already-a-component-named-component-name"></a>Esiste già un componente denominato ' \<component name> '

Messaggio di errore: "è già presente un componente denominato ' \<component name> '. I componenti devono avere nomi univoci e i nomi non devono fare distinzione tra maiuscole e minuscole. Un nome non può inoltre entrare in conflitto con il nome di un componente in una classe ereditata ".

Questo messaggio di errore si verifica quando è stata apportata una modifica al nome di un componente nella Finestra Proprietà. Per correggere l'errore, verificare che tutti i nomi dei componenti siano univoci, che non siano con distinzione tra maiuscole e minuscole e che non siano in conflitto con i nomi di tutti i componenti nelle classi ereditate.

### <a name="there-is-already-a-toolbox-item-creator-registered-for-the-format-format-name"></a>Esiste già un creatore di elementi della casella degli strumenti registrato per il formato ' \<format name> '

Un componente di terze parti ha eseguito un callback a un elemento in una scheda della casella degli strumenti, ma l'elemento contiene già un callback. Contattare il fornitore del componente.

### <a name="this-language-engine-does-not-support-a-codemodel-with-which-to-load-a-designer"></a>Questo motore del linguaggio non supporta alcun CodeModel con cui caricare la finestra di progettazione

Questo messaggio è simile a "la lingua del file non supporta i servizi di analisi e generazione del codice necessari", ma questo messaggio comporta un problema di registrazione interno. Se viene visualizzato questo errore, se viene visualizzato questo errore, registrare un problema usando [segnala un problema](/visualstudio/ide/how-to-report-a-problem-with-visual-studio).

### <a name="type-type-name-does-not-have-a-constructor-with-parameters-of-types-parameter-type-names"></a>Il tipo ' \<type name\> ' non contiene un costruttore con parametri di tipo ' \<parameter type names> '

Visual Studio non è riuscito a trovare un [Costruttore](../../../csharp/programming-guide/classes-and-structs/constructors.md) con parametri corrispondenti. Questo potrebbe essere il risultato della fornitura di un costruttore con tipi diversi da quelli necessari. Un costruttore di **punti** può ad esempio richiedere due Integer. Se è stato specificato float, viene generato questo errore.

Per correggere l'errore, utilizzare un costruttore diverso o eseguire il cast esplicito dei tipi di parametro in modo che corrispondano a quelli forniti dal costruttore.

### <a name="unable-to-add-reference-reference-name-to-the-current-application"></a>Non è possibile aggiungere il riferimento ' \<reference name> ' all'applicazione corrente

Messaggio di errore: "Impossibile aggiungere il riferimento ' \<reference name> ' all'applicazione corrente. Verificare che non sia già stato fatto riferimento a una versione diversa di ' \<reference name> '.

Visual Studio non è in grado di aggiungere un riferimento. Per correggere l'errore, verificare che non sia già stato fatto riferimento a una versione diversa del riferimento.

### <a name="unable-to-check-out-the-current-file"></a>Impossibile estrarre il file corrente

Messaggio di errore: "Impossibile estrarre il file corrente. Il file potrebbe essere bloccato o potrebbe essere necessario estrarlo manualmente ".

Questo errore si verifica quando si modifica un file attualmente archiviato nel controllo del codice sorgente. In genere, Visual Studio Visualizza la finestra di dialogo checkout file in modo che l'utente possa estrarre il file. Questa volta, il file non è stato estratto, probabilmente a causa di un conflitto di merge durante il checkout. Per correggere l'errore, verificare che il file non sia bloccato, quindi provare a estrarlo manualmente.

### <a name="unable-to-find-page-named-options-dialog-box-tab-name"></a>Impossibile trovare la pagina denominata ' \<Options dialog box tab name> '

Questo errore si verifica quando una finestra di progettazione di componenti richiede l'accesso a una pagina dalla finestra di dialogo Opzioni utilizzando un nome che non esiste. Contattare il fornitore del componente.

### <a name="unable-to-find-property-property-name-on-page-options-dialog-box-tab-name"></a>Impossibile trovare la proprietà' \<property name> ' nella pagina ' \<Options dialog box tab name> '

Questo errore si verifica quando una finestra di progettazione di componenti richiede l'accesso a un determinato valore in una pagina della finestra di dialogo Opzioni, ma tale valore non esiste. Contattare il fornitore del componente.

### <a name="visual-studio-cannot-open-a-designer-for-the-file-because-the-class-within-it-does-not-inherit-from-a-class-that-can-be-visually-designed"></a>Impossibile aprire una finestra di progettazione per il file perché contiene una classe non ereditata da una classe che possa essere progettata in modo visivo

La classe è stata caricata in Visual Studio, ma non è stato possibile caricare la finestra di progettazione per quella classe. Visual Studio richiede che le finestre di progettazione usino la prima classe in un file. Per correggere l'errore, spostare il codice della classe in modo che sia la prima classe nel file, quindi caricare nuovamente la finestra di progettazione.

### <a name="visual-studio-cannot-save-or-load-instances-of-the-type-type-name"></a>Visual Studio non è in grado di salvare o caricare istanze del tipo ' \<type name> '

Si tratta di un problema con un componente di terze parti. Contattare il fornitore del componente.

### <a name="visual-studio-is-unable-to-open-document-name-in-design-view"></a>Visual Studio non è in grado di aprire ' \<document name> ' nella visualizzazione progettazione

Messaggio di errore: "Visual Studio non è in grado di aprire ' \<document name> ' nella visualizzazione progettazione. Nessun parser installato per il tipo di file ".

Questo errore indica che la lingua del progetto non supporta una finestra di progettazione e si verifica quando si tenta di aprire un file nella finestra di dialogo Apri file o da Esplora soluzioni. Modificare invece il file nella visualizzazione codice.

### <a name="visual-studio-was-unable-to-find-a-designer-for-classes-of-type-type-name"></a>Visual Studio non è riuscito a trovare una finestra di progettazione per le classi di tipo ' \<type name> '

Visual Studio ha caricato la classe, ma la classe non può essere progettata. Modificare invece la classe nella visualizzazione codice facendo clic con il pulsante destro del mouse sulla classe e scegliendo **Visualizza codice**.

## <a name="see-also"></a>Vedere anche

- [Sviluppare controlli Windows Forms tramite la finestra di progettazione](developing-windows-forms-controls-at-design-time.md)
- [Forum Progettazione Windows Form](https://social.msdn.microsoft.com/Forums/windows/home?forum=winformsdesigner)
