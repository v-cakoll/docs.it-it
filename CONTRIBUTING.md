---
ms.openlocfilehash: 469be53e14c42775f21ef1ef815becd5cad03a97
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75336718"
---
# <a name="contributing"></a>Contributi al codice

Grazie per l'interesse dimostrato nell'apporto di contributi alla documentazione di .NET.

> È in corso lo spostamento delle linee guida in una guida alla collaborazione a livello di sito.
> Per visualizzare il nuovo materiale sussidiario, vedere [Panoramica della guida per i collaboratori di Microsoft Docs](https://docs.microsoft.com/contribute/).

Il documento illustra il processo per offrire il proprio contributo per gli articoli e gli esempi di codice ospitati nel [sito della documentazione di .NET](https://docs.microsoft.com/dotnet). I contributi possono essere semplici come le correzioni di errori di ortografia o complessi, ad esempio nuovi articoli.

- [Cosa fare e cosa non fare](#dos-and-donts)
- [Processo per fornire il contributo](#process-for-contributing)
- [Esperienza interattiva in C#](#the-c-interactive-experience)
- [Contratto di licenza con il collaboratore](#contributor-license-agreement)

Questo repository contiene la documentazione concettuale per .NET. Il sito della documentazione di .NET è costituito da più repository oltre a questo:

- [Esempi di codice e frammenti di codice](https://github.com/dotnet/samples) I problemi e le attività per questo repository vengono rilevati in [DotNet/docs/issues](https://github.com/dotnet/docs/issues).
- Informazioni di [riferimento sulle API .NET](https://github.com/dotnet/dotnet-api-docs) I problemi e le attività per questo repository vengono rilevati in [DotNet/DotNet-API-docs/issues](https://github.com/dotnet/dotnet-api-docs/issues).
- Informazioni di [riferimento su .NET Compiler Platform SDK](https://github.com/dotnet/roslyn-api-docs) I problemi e le attività per questo repository vengono rilevati in [DotNet/docs/issues](https://github.com/dotnet/docs/issues).

## <a name="dos-and-donts"></a>Cosa fare e cosa non fare

Il seguente elenco illustra alcune regole che è necessario tenere presenti quando si inviano contributi alla documentazione di .NET:

- **NON** inviare richieste pull di grandi dimensioni. Al contrario, segnalare un problema e avviare una discussione in modo che si possa concordare una direzione prima di investire una grande quantità di tempo. Per le modifiche bulk, suddividere il lavoro in richieste pull più piccole (fino a 100 di file). Questa guida è fortemente consigliata se la richiesta pull non segue le linee guida seguenti.
- **Esaminare i** [problemi correnti per i](https://github.com/dotnet/docs/labels/up-for-grabs) suggerimenti sulle attività.
- **Creare una** richiesta pull per ogni attività. Le richieste pull che includono più modifiche non correlate sono molto più difficili da rivedere. Che ritarda le revisioni e l'Unione di richieste pull. Questa linea guida si applica anche alle revisioni: si prova a non suggerire modifiche non correlate nelle revisioni. si chiede che le revisioni della community rispettano questa linea guida.
- **Fornire una** descrizione chiara del lavoro nella richiesta pull. Indicare le modifiche e il motivo. La descrizione predefinita di "Update article.md" non è utile per i revisori.
- **Non** inviare richieste pull per le modifiche solo stile senza una discussione preliminare. Queste richieste pull hanno tempo aggiuntivo per verificarne l'accuratezza e l'Unione causa spesso conflitti di merge con altri aggiornamenti importanti. Ci stiamo impegnando per seguire uno stile coerente, ma stiamo bilanciando il lavoro con altre attività. Gli articoli vengono introdotti in conformità allo stile quando si eseguono aggiornamenti principali per altri motivi.
- **LEGGERE** le linee guida riportate nella [Guida di stile](./styleguide/template.md) e sulla [voce e tono](./styleguide/voice-tone.md). Le nuove aggiunte devono seguire queste linee guida.
- **CREARE** un ramo separato nel fork prima di lavorare sugli articoli.
- **SEGUIRE** il [flusso di lavoro di GitHub Flow](https://guides.github.com/introduction/flow/).
- **SCIVERE UN BLOG O INVIARE TWEET** (o usare altri mezzi) frequentemente per informazioni sui contributi.

Queste linee guida consentono di rispettare il tempo degli utenti. Molti utenti contribuiscono a questi repository. Seguendo queste linee guida, è più semplice esaminare e unire la richiesta pull in modo tempestivo. Queste procedure riducono al minimo i conflitti con le richieste pull di altri membri della community e del team. Poiché le richieste pull che non seguono queste linee guida spesso causano un lavoro aggiuntivo per i membri della community e degli Stati Uniti, tali richieste potrebbero essere rifiutate. Se si desidera un'eccezione, iniziare creando un problema.

> Nota: si potrebbe osservare che attualmente alcuni argomenti non seguono tutte le linee guida indicate qui e nella [Guida di stile](./styleguide/template.md). Ci stiamo impegnando per il raggiungimento della coerenza in tutto il sito.

## <a name="process-for-contributing"></a>Processo per apportare il contributo

Sono necessarie conoscenze di base di [Git e GitHub.com](https://guides.github.com/activities/hello-world/).

**Passaggio 1:** Ignorare questo passaggio per le piccole modifiche (ad esempio, se si corregge un errore di digitazione o si apre immediatamente una richiesta pull per risolvere un problema riscontrato nei documenti). Se si è interessati a scrivere nuovo contenuto o a revisionare completamente un contenuto esistente, aprire un [problema](https://github.com/dotnet/docs/issues) descrivendo che cosa si intende fare.
Il contenuto all'interno della cartella *docs* è suddiviso in sezioni visibili nel sommario. Definire la posizione del sommario in cui verrà inserito l'argomento. Ottenere feedback sulla proposta.

oppure

È anche possibile scegliere tra i problemi esistenti per cui sono previsti i contributi della community. In [Projects for .NET Community contributors](https://github.com/dotnet/docs/projects/35) (Progetti per i collaboratori della community di .NET) sono elencati molti elementi di lavoro disponibili per i collaboratori della community. In base ai propri interessi e livello di impegno, è possibile scegliere tra i problemi nelle categorie seguenti:

- **Maintenance** (Manutenzione). Questa categoria include contributi piuttosto semplici, ad esempio la correzione di collegamenti interrotti o non corretti, l'aggiunta di esempi di codice mancanti o la risoluzione di problemi di contenuto limitato. In alcuni casi, questi problemi possono riguardare un numero elevato di file. In tal caso, è opportuno comunicare su che cosa si vuole intervenire prima di iniziare.

- **Content updates** (Aggiornamenti del contenuto). A causa dell'enormità del set di documenti, il contenuto diventa facilmente obsoleto e richiede una revisione. Per diversi motivi, inoltre, il contenuto è stato duplicato o anche triplicated. L'aggiornamento del contenuto richiede di verificare che i singoli argomenti siano aggiornati o di revisionare il contenuto in un'area funzionale per eliminare i duplicati assicurandosi che tutto il contenuto univoco venga conservato nel set di documenti più piccolo.

- **New content authoring** (Creazione di nuovi contenuti). Se si è interessati a creare il proprio argomento, questi problemi elencano gli argomenti che sarebbe opportuno aggiungere al set di documenti. Prima di iniziare a lavorare su un argomento, inviare un messaggio. Se si è interessati a scrivere un argomento non elencato qui, aprire un problema.

È anche possibile esaminare l'elenco di [problemi aperti](https://github.com/dotnet/docs/issues) e proporsi per lavorare a quelli a cui si è interessati. I problemi aperti per il contributo sono contrassegnati dall'etichetta [up-for-grabs](https://github.com/dotnet/docs/labels/up-for-grabs).

**Passaggio 2:** Creare una copia tramite fork dei repository `dotnet/docs`, `dotnet/samples` o `dotnet/dotnet-api-docs` in base alle esigenze e creare un ramo per le modifiche.

Per le piccole modifiche, è possibile usare l'interfaccia Web di GitHub. È sufficiente fare clic su **Edit the file in your fork of this project** (Modifica il file nel fork di questo progetto) nel file che si vuole modificare. GitHub crea automaticamente il nuovo ramo quando si inviano le modifiche.

**Passaggio 3:** Apportare le modifiche in questo nuovo ramo.

Se si tratta di un nuovo argomento, è possibile usare questo [file modello](./styleguide/template.md) come punto di partenza. Il file contiene le linee guida per la scrittura e illustra anche i metadati necessari per ogni articolo, ad esempio le informazioni sull'autore.

Passare alla cartella che corrisponde alla posizione del sommario determinata per l'articolo nel passaggio 1.
Questa cartella contiene i file markdown per tutti gli articoli nella sezione.
Se necessario, creare una nuova cartella in cui inserire i file per il contenuto. L'articolo principale di tale sezione è denominato *index.md*.
Per le immagini e le altre risorse statiche, creare una sottocartella denominata *media* all'interno della cartella contenente l'articolo, se non esiste già. Nella cartella *media* creare una sottocartella con il nome dell'articolo (tranne che per il file di indice).
Includere gli esempi di dimensioni maggiori nella cartella *samples* nella radice del repository.

Assicurarsi di seguire la sintassi di Markdown appropriata. Per altre informazioni, vedere la [guida di stile](./styleguide/template.md).

### <a name="example-structure"></a>Struttura di esempio

```
docs
  /about
  /core
    /porting
      porting-overview.md
      /media
        /porting-overview
            portability_report.png
```

**Passaggio 4:** Inviare una richiesta pull (PR) dal ramo a `dotnet/docs/master`, `dotnet/dotnet-api-docs/master`o `dotnet/samples/master`.

La richiesta pull deve *sempre* essere destinata al ramo predefinito del repository, a meno che non si stia lavorando a un ramo di rilascio. Per DotNet/docs, Master Branch è il ramo predefinito. Per i repository localizzati, il ramo attivo è quello predefinito. Non aprire *mai* una richiesta pull destinata al ramo Live su DotNet/docs.

Ogni richiesta pull deve in genere fare riferimento a un problema alla volta. La richiesta pull può modificare uno o più file. Se è necessario apportare più correzioni in file diversi, è preferibile inviare richieste pull separate.

Se la richiesta pull tratta un problema esistente, aggiungere la parola chiave `Fixes #Issue_Number` al messaggio di commit o alla descrizione della richiesta pull. In questo modo, il problema viene chiuso automaticamente quando viene eseguito il merge della richiesta pull. Per altre informazioni vedere l'argomento relativo alla [chiusura di problemi tramite i messaggi di commit](https://help.github.com/articles/closing-issues-via-commit-messages/).

Il team di .NET esaminerà la richiesta pull e informerà l'utente se sono necessari altri aggiornamenti o modifiche per l'approvazione.

**Passaggio 5:** eseguire gli aggiornamenti necessari per il ramo come discusso con il team.

Dopo aver applicato il feedback e se la modifica viene approvata, i responsabili eseguiranno il merge della richiesta pull nel ramo master.

A intervalli stabiliti, verrà eseguito il push di tutti i commit dal ramo master al ramo attivo e l'utente sarà in grado di visualizzare i propri contributi in tempo reale in https://docs.microsoft.com/dotnet/.

### <a name="contributing-to-samples"></a>Contributo per gli esempi

Viene fatta la distinzione seguente per il codice esistente nel repository:

- Esempi: i lettori possono scaricare ed eseguire gli esempi. Tutti gli esempi devono essere librerie o applicazioni complete. Se l'esempio crea una libreria, deve includere gli unit test o un'applicazione che consente ai lettori di eseguire il codice.

- Frammenti di codice: illustrano un concetto o un'attività più ridotta. Eseguono la compilazione, ma non sono applicazioni complete.

Tutti i codici si trovano nel repository [dotnet/samples](https://github.com/dotnet/samples). Microsoft sta lavorando a un modello in cui la struttura della cartella samples corrisponda alla struttura della cartella docs. Gli standard seguiti sono:

- La cartella *snippets* di primo livello contiene i frammenti per i piccoli esempi specifici.
- Gli esempi di riferimento API sono stati inseriti in una cartella che segue questo modello: *snippets/\<linguaggio>/api/\<spazio dei nomi>/\<nomeapi>* .
- Le altre cartelle di primo livello corrispondono alle cartelle di primo livello nel repository *docs*. Il repository docs include, ad esempio, una cartella *machine-learning/tutorials* e gli esempi per le esercitazioni su Machine Learning si trovano nella cartella *samples/machine-learning/tutorials*.

Inoltre, tutti gli esempi nelle cartelle *core* e *standard* devono essere compilati ed eseguiti in tutte le piattaforme supportate da .NET Core. Il sistema di compilazione CI imporrà questo requisito. La cartella *framework* di primo livello contiene esempi che vengono eseguiti e convalidati solo in Windows.

Queste directory potrebbe essere espanse man mano che vengono aggiunti nuovi contenuti al repository docs. Verranno, ad esempio, aggiunte directory Xamarin, come le directory `xamarin-ios` e `xamarin-android`.

Ogni esempio completo creato deve contenere un file *readme.md*. Questo file deve contenere una breve descrizione dell'esempio (uno o due paragrafi). Il file *readme.md* deve indicare ai lettori quali informazioni otterranno esplorando questo esempio. Il file *readme.md* deve contenere anche un collegamento al documento live nel [sito della documentazione di .NET](https://docs.microsoft.com/dotnet/welcome).
Per determinare dove un determinato file del repository esegue il mapping a tale sito, sostituire `/docs` nel percorso del repository con `https://docs.microsoft.com/dotnet`.

L'argomento conterrà anche collegamenti all'esempio. Creare un collegamento diretto alla cartella dell'esempio in GitHub.

Per altre informazioni, vedere il [file leggimi sugli esempi](https://github.com/dotnet/samples/blob/master/README.md).

## <a name="the-c-interactive-experience"></a>Esperienza interattiva in C#

Gli esempi di codice breve in C# possono usare il tag di linguaggio `csharp-interactive` per specificare un esempio C# che viene eseguito nel browser. (Gli esempi di codice inline usano il tag `csharp-interactive` per i frammenti di codice inclusi nell'origine, usare il tag `code-csharp-interactive`). Questi esempi di codice visualizzano una finestra del codice e una finestra di output nell'articolo. La finestra di output visualizza gli output dell'esecuzione del codice interattivo dopo che l'utente ha eseguito l'esempio.

L'esperienza interattiva in C# cambia il modo di usare gli esempi. I visitatori possono eseguire l'esempio per visualizzare i risultati. Una serie di fattori consente di determinare se l'esempio o il testo corrispondente deve includere informazioni sull'output.

### <a name="when-to-display-the-expected-output-without-running-the-sample"></a>Quando visualizzare l'output previsto senza eseguire l'esempio

- Gli articoli destinati a principianti dovrebbero fornire l'output in modo che i lettori possano confrontare l'output del proprio lavoro con la risposta prevista.
- Gli esempi in cui l'output è fondamentale per l'argomento devono visualizzare tale output. Ad esempio, gli articoli sul testo formattato devono mostrare il formato di testo senza eseguire l'esempio.
- Quando sia l'esempio che l'output previsto sono brevi, prendere in considerazione la possibilità di visualizzare l'output, per risparmiare tempo.
- Gli articoli che spiegano come le impostazioni cultura o le impostazioni cultura inglese non dipendenti da paese/area geografica influiscono sull'output devono spiegare l'output previsto. Il ciclo Read–Eval–Print interattivo viene eseguito in un host basato su Linux. Le impostazioni cultura predefinite e le impostazioni cultura inglese non dipendenti da paese/area geografica producono output diversi a seconda dei sistemi operativi e dei computer. L'articolo deve spiegare l'output nei sistemi Windows, Linux e Mac.

### <a name="when-to-exclude-expected-output-from-the-sample"></a>Quando escludere l'output previsto dall'esempio

- Gli articoli in cui il codice di esempio genera un output di maggiori dimensioni non devono includerlo nei commenti perché nasconde il codice dopo che l'esempio è stato eseguito.
- Articoli in cui l'esempio illustra un argomento, ma l'output non è fondamentale per comprenderlo, ad esempio un codice che esegue una query LINQ per illustrare la sintassi della query e quindi visualizzare ogni elemento nella raccolta di output.

## <a name="contributor-license-agreement"></a>Contratto di licenza per contributi

È necessario firmare il [contratto di licenza per contributi di .NET Foundation](https://cla.dotnetfoundation.org) (CLA) prima che la richiesta pull venga unita. Questa è una procedura da eseguire una volta sola per i progetti in .NET Foundation. Per altre informazioni, vedere [Contributor License Agreement](https://en.wikipedia.org/wiki/Contributor_License_Agreement) (Contratto di licenza per contributi) su Wikipedia.

Contratto: [net-foundation-contribution-license-agreement.pdf](https://github.com/dotnet/home/blob/master/guidance/net-foundation-contribution-license-agreement.pdf)

Non è necessario firmare il contratto in anticipo. È possibile clonare, creare una copia tramite fork e inviare la richiesta pull come di consueto. Quando viene creata, la richiesta pull è classificata da un bot CLA. Se la modifica è piuttosto semplice, ad esempio è stato corretto un errore di digitazione, la richiesta pull viene etichettata come `cla-not-required`. In caso contrario, viene classificata come `cla-required`. Una volta che il contratto di licenza per contributi è stato firmato, la richiesta pull attuale e tutte le richieste future sono etichettate come `cla-signed`.
