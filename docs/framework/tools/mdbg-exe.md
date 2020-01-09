---
title: MDbg.exe (Debugger della riga di comando di .NET Framework)
ms.date: 03/30/2017
helpviewer_keywords:
- command-line debugger [.NET Framework]
- MDbg.exe
ms.assetid: 28a3f509-07e2-4dbe-81df-874c5e969cc4
ms.openlocfilehash: 58502626fed6c9cee52acb673ae34f6024f78b9b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715759"
---
# <a name="mdbgexe-net-framework-command-line-debugger"></a>MDbg.exe (Debugger della riga di comando di .NET Framework)
Il debugger della riga di comando di .NET Framework consente ai fornitori di strumenti e agli sviluppatori di applicazioni di individuare e correggere i bug nei programmi destinati a Common Language Runtime di .NET Framework. Questo strumento usa l'API di debug del runtime per offrire servizi di debug. È possibile usare MDbg.exe solo per eseguire il debug di codice gestito in quanto non esiste alcun supporto per il debug di codice non gestito.  
  
Questo strumento è disponibile tramite NuGet. Per informazioni sull'installazione, vedere [MDbg 0.1.0](https://www.nuget.org/packages/MDbg/0.1.0). Per eseguire lo strumento, usare la console di Gestione pacchetti. Per altre informazioni su come usare la console di Gestione pacchetti, vedere l'articolo [Console di Gestione pacchetti](/nuget/tools/package-manager-console).
  
Al prompt di Gestione pacchetti, digitare quanto segue:  
  
## <a name="syntax"></a>Sintassi  
  
```console  
MDbg [ProgramName[arguments]] [options]  
```  
  
## <a name="commands"></a>Comandi  
 Quando si è nel debugger (come indicato dal prompt **mdbg>** ), digitare i comandi descritti nella sezione seguente:  
  
 **comando** [*argomenti*]  
  
 I comandi di MDbg.exe sono soggetti alla distinzione tra maiuscole e minuscole.  
  
|Comando|Descrizione|  
|-------------|-----------------|  
|**ap**[**rocess**] [*numero*]|Passa a un altro processo di cui viene eseguito il debug o visualizza i processi disponibili. I numeri non corrispondono a ID di processo (PID) effettivi ma a un elenco a indice zero.|  
|**a**[**ttach**] [*pid*]|Esegue la connessione a un processo o visualizza i processi disponibili.|  
|**b**[**reak**] [*NomeClasse.Metodo* &#124; *NomeFile:NumeroRiga*]|Imposta un punto di interruzione in corrispondenza del metodo specificato. I moduli vengono sottoposti a scansione in sequenza.<br /><br /> -   **break** *FileName: LINOO* imposta un punto di interruzione in una posizione nell'origine.<br />-   **break** *~ Number* imposta un punto di interruzione su un simbolo visualizzato di recente con il comando **x** .<br />modulo -   **break** *. Nomeclasse. Method + IlOffset* imposta un punto di interruzione nel percorso completo.|  
|**block**[**ingObjects**]|Visualizza i blocchi di monitoraggio che stanno bloccando i thread.|  
|**ca**[**tch**] [*tipoEccezione*]|Determina l'arresto del debugger in corrispondenza di tutte le eccezioni, non solo di quelle non gestite.|  
|**cl**[**earException**]|Contrassegna l'eccezione corrente come gestita in modo che l'esecuzione continui. Se non si risolve la causa dell'eccezione, questa potrebbe essere nuovamente generata in breve tempo.|  
|**conf**[**ig**] [*valoreopzione*]|Visualizza tutte le opzioni configurabili e mostra come richiamare le opzioni senza valori facoltativi. Se si specifica l'opzione, imposta `value` come opzione corrente. Attualmente sono disponibili le seguenti opzioni:<br /><br /> -   `extpath` imposta il percorso per la ricerca delle estensioni quando viene usato il comando `load`.<br />-   `extpath+` aggiunge un percorso per caricare le estensioni.|  
|**del**[**ete**]|Elimina un punto di interruzione.|  
|**de**[**tach**]|Esegue la disconnessione da un processo sottoposto a debug.|  
|**d**[**own**] [*frame*]|Sposta verso il basso lo stack frame attivo.|  
|**echo**|Restituisce un messaggio alla console.|  
|**enableNotif**[**ication**] *nomeTipo* 0&#124;1|Abilita (1) o disabilita (0) le notifiche personalizzate per il tipo specificato.|  
|**ex**[**it**] [*codiceuscita*]|Esce dalla shell di MDbg.exe e specifica, facoltativamente, il codice di uscita del processo.|  
|**fo**[**reach**] [*AltroComando*]|Esegue un comando su tutti i thread. *AltroComando* è un comando valido che opera su un thread. **foreach** *AltroComando* esegue lo stesso comando su tutti i thread.|  
|**f**[**unceval**] [`-ad` *num*] *FunctionName* [*args...* ]|Esegue una valutazione della funzione sul thread attivo corrente specificata da *nomeFunzione*. Il nome della funzione deve essere completo e includere gli spazi dei nomi.<br /><br /> L'opzione `-ad` specifica il dominio applicazione da usare per risolvere la funzione. Se l'opzione `-ad` non viene specificata, per impostazione predefinita, il dominio applicazione per la risoluzione corrisponde a quello in cui è reperibile il thread usato per la valutazione della funzione.<br /><br /> Se la funzione da valutare non è statica, il primo parametro passato deve essere un puntatore `this`. La ricerca degli argomenti per la valutazione della funzione viene eseguita in tutti i domini applicazione.<br /><br /> Per richiedere un valore di un dominio applicazione, anteporre alla variabile il nome del modulo e del dominio applicazione, ad esempio `funceval -ad 0 System.Object.ToString hello.exe#0!MyClass.g_rootRef`. Questo comando valuta la funzione `System.Object.ToString` nel dominio applicazione `0`. Dato che il metodo `ToString` è una funzione di istanza, il primo parametro deve essere un puntatore `this`.|  
|**g**[**o**]|Determina la continuazione dell'esecuzione del programma fino a quando non viene rilevato un punto di interruzione, il programma non viene chiuso o un evento, ad esempio un'eccezione non gestita, non causa la chiusura del programma.|  
|**h**[**elp**] [*comando*]<br /><br /> oppure<br /><br /> **?** [*comando*]|Visualizza una descrizione di tutti i comandi o una descrizione dettagliata di un comando specificato.|  
|**ig**[**nore**] [*evento*]|Determina l'arresto del debugger solo in corrispondenza di eccezioni non gestite.|  
|**int**[**ercept**] *NumeroFrame*|Esegue il rollback del debugger a un numero di frame specificato.<br /><br /> Se il debugger rileva un'eccezione, usare questo comando per eseguire il rollback del debugger al numero di frame specificato. È possibile modificare lo stato del programma tramite il comando **set** e usare il comando **go** per continuare.|  
|**k**[**ill**]|Arresta il processo attivo.|  
|**l**[**ist**] [*moduli* &#124; *dominiapp* &#124; *assembly*]|Visualizza i moduli, i domini applicazione o gli assembly caricati.|  
|**lo**[**ad**] *nomeAssembly*|Carica un'estensione in questo modo: l'assembly specificato viene caricato e viene quindi effettuato un tentativo di eseguire il metodo statico `LoadExtension` dal tipo `Microsoft.Tools.Mdbg.Extension.Extension`.|  
|**log** [*tipoEvento*]|Imposta o visualizza gli eventi da registrare.|  
|**mo**[**de**] [*opzione on/off*]|Imposta opzioni differenti del debugger. Usare `mode` senza opzioni per ottenere un elenco delle modalità di debug e delle relative impostazioni correnti.|  
|**mon**[**itorInfo**] *riferimentoMonitoraggio*|Visualizza le informazioni sul blocco di monitoraggio degli oggetti.|  
|**newo**[**bj**] *nomeTipo* [*argomenti...* ]|Crea un nuovo oggetto di tipo *nomeTipo*.|  
|**n**[**ext**]|Esegue il codice e passa alla riga successiva anche se questa include molte chiamate di funzione.|  
|*Percorsofiledump* Opendump|Apre il file dump specificato per il debug.|  
|**o**[**ut**]|Esegue lo spostamento alla fine della funzione corrente.|  
|**pa**[**th**] [*nomePercorso*]|Cerca i file di origine nel percorso specificato se il percorso non è disponibile nei binari.|  
|**p**[**rint**] [*variabile*] &#124; [`-d`]|Stampa tutte le variabili nell'ambito (**Print**), stampa la variabile specificata (**Print** *var*) o Visualizza le variabili del debugger (**Print**`-d`).|  
|**printe**[**xception**] [ *-r*]|Visualizza l'ultima eccezione sul thread corrente. Usare l'opzione di ricorsione `–r` per attraversare la proprietà `InnerException` sull'oggetto eccezione per ottenere informazioni sull'intera catena delle eccezioni.|  
|**pro**[**cessenum**]|Visualizza i processi attivi.|  
|**q**[**uit**] [*codiceUscita*]|Esce dalla shell di MDbg.exe specificando, facoltativamente, il codice di uscita del processo.|  
|**re**[**sume**] [`*` &#124; [`~`]*numeroThread*]|Riprende il thread corrente o quello specificato dal parametro *numeroThread*.<br /><br /> Se il parametro *numeroThread* viene specificato come `*` o se il numero del thread inizia con `~`, il comando viene applicato a tutti i thread ad eccezione di quello specificato da *numeroThread*.<br /><br /> La ripresa di un thread non sospeso non produce alcun effetto.|  
|**r**[**un**] [`-d`(`ebug`) &#124; -`o`(`ptimize`) &#124;`-enc`] [[*percorso_per_fileExe*] [*argomenti_per_fileExe*]]|Arresta l'eventuale processo corrente e ne avvia uno nuovo. Se non viene passato alcun argomento eseguibile, verrà eseguito l'ultimo programma eseguito con il comando `run`. Se l'argomento eseguibile viene fornito, per l'esecuzione del programma specificato verranno usati gli argomenti facoltativamente indicati.<br /><br /> Se gli eventi di caricamento classi, caricamento moduli e avvio thread vengono ignorati (come avviene per impostazione predefinita), il programma verrà arrestato in corrispondenza della prima istruzione eseguibile del thread principale.<br /><br /> È possibile forzare la compilazione JIT (just-in-time) del codice usando uno dei tre flag seguenti:<br /><br /> -   `-d` *(* `ebug` *)* Disabilita le ottimizzazioni. Questa è l'impostazione predefinita per MDbg.exe.<br />-   `-o` *(* `ptimize` *)* impone l'esecuzione del codice in modo analogo all'esterno del debugger, ma rende anche più difficile l'esperienza di debug. Questo è il flag predefinito da usare all'esterno del debugger.<br />-   `-enc` abilita la funzionalità Modifica e continuazione ma comporta una riduzione delle prestazioni.|  
|**Imposta** *valore*=*variabile*|Modifica il valore di qualsiasi variabile inclusa nell'ambito.<br /><br /> È anche possibile creare variabili personalizzate per il debugger e assegnarvi valori di riferimento dall'interno dell'applicazione. Questi valori fungono da handle del valore originale e anche quest'ultimo non è incluso nell'ambito. Tutte le variabili del debugger devono iniziare con `$`, ad esempio `$var`. Per cancellare questi handle, impostarli su un valore vuoto tramite il comando seguente:<br /><br /> `set $var=`|  
|**Setip** [`-il`] *numero*|Imposta il puntatore all'istruzione (IP, Instruction Pointer) corrente nel file sulla posizione specificata. Se si specifica l'opzione `-il`, il numero rappresenta un offset MSIL (Microsoft Intermediate Language) nel metodo. In caso contrario, il numero rappresenta un numero di riga del codice sorgente.|  
|**sh**[**ow**] [*righe*]|Specifica il numero di righe da visualizzare.|  
|**s**[**tep**]|Sposta l'esecuzione alla funzione successiva della riga corrente oppure passa alla riga successiva se non è disponibile un'altra funzione di cui eseguire le istruzioni.|  
|**su**[**spend**] [\* &#124; [~]*numeroThread*]|Sospende il thread corrente o quello specificato dal parametro *numeroThread*.  Se *numeroThread* viene specificato come `*`, il comando viene applicato a tutti i thread. Se il numero di thread inizia con `~`, il comando viene applicato a tutti i thread, ad eccezione di quello specificato da *numeroThread*. I thread sospesi sono esclusi dall'esecuzione quando il processo viene eseguito tramite il comando **go** o **step**. L'esecuzione del processo non continuerà se il processo non include thread non sospesi e si usa il comando **go**. In tal caso, premere CTRL-C per passare al processo.|  
|**sy**[**mbol**] *nomeComando* [*valoreComando*]|Specifica uno dei seguenti comandi:<br /><br /> -   `symbol path` [`"value"`] - Visualizza o imposta il percorso del simbolo corrente.<br />-   `symbol addpath` `"value"`: aggiunge al percorso del simbolo corrente.<br />-   `symbol reload` [`"module"`] - Ricarica tutti i simboli o i simboli per il modulo specificato.<br />-   `symbol list` [`module`] - Visualizza tutti i simboli attualmente caricati per tutti i moduli o per il modulo specificato.|  
|**t**[**hread**] [*nuovoThread*] [-*soprannome*`]`|Il comando thread senza parametri visualizza tutti i thread gestiti nel processo corrente. I thread sono in genere identificati in base ai relativi numeri. Se tuttavia al thread è assegnato un nome alternativo, verrà visualizzato tale nome. È possibile usare il parametro `-nick` per assegnare un nome alternativo a un thread.<br /><br /> -   **thread** `-nick` *ThreadName* assegna un nome alternativo al thread attualmente in esecuzione.<br /><br /> I nomi alternativi non possono essere numeri. Se al thread corrente è già stato assegnato un nome alternativo, il nome alternativo precedente verrà sostituito da quello nuovo. Se il nuovo nome alternativo è una stringa vuota (""), il nome alternativo del thread corrente verrà eliminato e non ne verrà assegnato un altro.|  
|**u**[**p**]|Spostare verso l'alto lo stack frame attivo.|  
|**uwgc**[**handle**] [*variabile*] &#124; [*indirizzo*]|Visualizza la variabile rilevata da un handle. L'handle può essere specificato in base al nome o all'indirizzo.|  
|**when**|Visualizza le istruzioni `when` attualmente attive.<br /><br /> **quando** **Delete All** &#124; `num` [`num` [`num`...]]-Elimina l'istruzione `when` specificata dal numero o tutte le istruzioni `when` se viene specificato `all`.<br /><br /> **quando** `stopReason` [`specific_condition`] **`cmd` [** `cmd` [`cmd`...]]-il parametro *stopReason* può essere uno dei seguenti:<br /><br /> `StepComplete`, `ProcessExited`, `ThreadCreated`, `BreakpointHit`, `ModuleLoaded`, `ClassLoaded`, `AssemblyLoaded`, `AssemblyUnloaded`, `ControlCTrapped`, `ExceptionThrown`, `UnhandledExceptionThrown`, `AsyncStop`, `AttachComplete`, `UserBreak`, `EvalComplete`, `EvalException`, `RemapOpportunityReached`, `NativeStop`.<br /><br /> *condizione_specifica* può accettare uno dei seguenti valori:<br /><br /> -   *numero* - Per `ThreadCreated` e `BreakpointHit`, attiva l'azione solo quando arrestata da un numero ID thread/punto di interruzione con lo stesso valore.<br />-   [`!`]*nome* - Per `ModuleLoaded`, `ClassLoaded`, `AssemblyLoaded`, `AssemblyUnloaded`, `ExceptionThrown` e `UnhandledExceptionThrown`, attiva l'operazione solo quando il nome corrisponde al nome di *motivoInterruzione*.<br /><br /> *condizione_specifica* deve essere vuoto per gli altri valori di *motivoInterruzione*.|  
|**w**[**qui**] [`-v`] [ *profondità*`-c`] [*ThreadID*]|Visualizza informazioni di debug relative agli stack frame.<br /><br /> -   L'opzione `-v` offre informazioni dettagliate su ogni stack frame visualizzato.<br />-   Specificando un numero per `depth`, limita il numero di frame visualizzati. Usare il comando **all** per visualizzare tutti i frame. Il valore predefinito è 100.<br />Se si specifica il parametro *IDthread*, è possibile determinare quale thread è associato allo stack. Il valore predefinito è il solo thread corrente. Usare il comando **all** per ottenere tutti i thread.|  
|**x** [`-c`*numeroSimboli*] [*modulo*[`!`*modello*]]|Visualizza le funzioni che corrispondono al parametro `pattern` per un modulo.<br /><br /> Se viene specificato il parametro *numeroSimboli*, l'output viene limitato al numero indicato. Se non viene specificato `!` (che indica un'espressione regolare) per il parametro *modello*, vengono visualizzate tutte le funzioni. Se non viene specificato un valore per il parametro *modulo*, vengono visualizzati tutti i moduli caricati. È possibile usare simboli ( *~#* ) per impostare punti di interruzione tramite il comando **break**.|  
  
## <a name="remarks"></a>Note  
 Compilare l'applicazione di cui eseguire il debug usando flag specifici del compilatore che determinano la generazione di simboli di debug da parte del compilatore. Per altre informazioni su questi flag, vedere la documentazione fornita con il compilatore. È possibile eseguire il debug delle applicazioni ottimizzate, tuttavia alcune informazioni di debug risulteranno mancanti. Molte variabili locali, ad esempio, non risulteranno visibili e le righe del codice sorgente non saranno accurate.  
  
 Dopo aver compilato l'applicazione, digitare **mdbg** al prompt dei comandi per avviare una sessione di debug, come illustrato nell'esempio seguente.  
  
```console  
C:\Program Files\Microsoft Visual Studio 8\VC>mdbg  
MDbg (Managed debugger) v2.0.50727.42 (RTM.050727-4200) started.  
Copyright (C) Microsoft Corporation. All rights reserved.  
  
For information about commands type "help";  
to exit program type "quit".  
mdbg>  
```  
  
 Il prompt `mdbg>` indica che il debugger è in esecuzione.  
  
 Una volta nel debugger, usare i comandi e gli argomenti descritti nella sezione precedente.  
  
## <a name="see-also"></a>Vedere anche

- [Strumenti](index.md)
- [Prompt dei comandi](developer-command-prompt-for-vs.md)
