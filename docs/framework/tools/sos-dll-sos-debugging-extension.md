---
title: SOS.dll (estensione del debugger SOS)
ms.date: 03/30/2017
helpviewer_keywords:
- debugging extensions
- SOS debugging extensions
- SOS.dll
ms.assetid: 9ac1b522-77ab-4cdc-852a-20fcdc9ae498
ms.openlocfilehash: 4c3a7f2798791f0c8a6b752f06bc2937fc970d40
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715736"
---
# <a name="sosdll-sos-debugging-extension"></a>SOS.dll (estensione del debugger SOS)

L'estensione del debugger SOS (SOS.dll) facilita l'esecuzione del debug di programmi gestiti in Visual Studio e nel debugger Windows (WinDbg.exe) fornendo informazioni sull'ambiente Common Language Runtime (CLR) interno. L'uso di questo strumento richiede l'abilitazione del debug non gestito nel progetto. SOS.dll viene installato automaticamente con .NET Framework. Per usare SOS.dll in Visual Studio, installare [Windows Driver Kit (WDK)](/windows-hardware/drivers/download-the-wdk).

## <a name="syntax"></a>Sintassi

```console
![command] [options]
```

## <a name="commands"></a>Comandi

|Comando|Descrizione|
|-------------|-----------------|
|**AnalyzeOOM** (**ao**)|Visualizza le informazioni sull'ultimo evento di memoria insufficiente verificatosi in una richiesta di allocazione all'heap di Garbage Collection (in Garbage Collection per il server, visualizza le informazioni sulla memoria insufficiente, se disponibili, per ogni heap di Garbage Collection).|
|**BPMD** [ **-nofuturemodule**] [ *nome modulo*\<> *nome metodo*\<>] [ **-md** <`MethodDesc`>] **-list** **-Clear** \<numero di punti di *interruzione in sospeso*>  **-ClearAll**|Crea un punto di interruzione in corrispondenza del metodo specificato nel modulo specificato.<br /><br /> Se il modulo e il metodo specificati non sono stati caricati, questo comando attende una notifica del caricamento e della compilazione JIT (just-in-time) del modulo prima di creare un punto di interruzione.<br /><br /> È possibile gestire l'elenco di punti di interruzione in sospeso usando le opzioni **-list**, **-clear** e **-clearall**:<br /><br /> L'opzione **-list** genera un elenco di tutti i punti di interruzione in sospeso. Se un punto di interruzione in sospeso dispone di un ID modulo diverso da zero, il punto di interruzione è specifico di una funzione in quel particolare modulo caricato. Se il punto di interruzione in sospeso dispone di un ID modulo pari a zero, il punto di interruzione si applica a moduli che non sono stati ancora caricati.<br /><br /> Usare l'opzione **-clear** o **-clearall** per rimuovere punti di interruzione in sospeso dall'elenco.|
|**CLRStack** [ **-a**] [ **-l**] [ **-p**] [ **-n**]|Fornisce l'analisi dello stack del solo codice gestito.<br /><br /> L'opzione **-p** mostra gli argomenti della funzione gestita.<br /><br /> L'opzione **-l** mostra le informazioni sulle variabili locali in un frame. L'estensione del debugger SOS non è in grado di recuperare i nomi locali, quindi l'output per i nomi locali è nel formato \<*indirizzo locale*>  **=** *valore*\<>.<br /><br /> L'opzione **-a** (tutto) è una scelta rapida per la combinazione di **-l** e **-p**.<br /><br /> L'opzione **-n** disabilita la visualizzazione dei nomi dei file di origine e dei numeri di riga. Se nel debugger è specificata l'opzione SYMOPT_LOAD_LINES, verranno ricercati i simboli di ogni frame gestito e, in caso di esito positivo, verranno visualizzati il nome del file di origine e il numero di riga corrispondenti. È possibile specificare il parametro **-n** (nessun numero di riga) per disabilitare questo comportamento.<br /><br /> L'estensione del debugger SOS non supporta la visualizzazione di frame di transizione su piattaforme basate su x64 e IA-64.|
|**COMState**|Elenca il modello di apartment COM per ogni thread e un puntatore `Context`, se disponibile.|
|**DumpArray** [ **-start** \<*startIndex*>] [ **-length** \<*length*>] [ **-Details**] [ **-nofields**] \<*indirizzo oggetto matrice*><br /><br /> oppure<br /><br /> **Da** [ **-start** \<*startIndex*>] [ **-length** \<*length*>] [ **-detail**] [ **-nofields**] *indirizzo oggetto matrice*>|Esamina gli elementi di un oggetto matrice.<br /><br /> L'opzione **-start** specifica l'indice iniziale in corrispondenza del quale devono essere visualizzati gli elementi.<br /><br /> L'opzione **-length** specifica il numero di elementi da visualizzare.<br /><br /> L'opzione **-details** visualizza dettagli dell'elemento usando i formati **DumpObj** e **DumpVC**.<br /><br /> L'opzione **-nofields** impedisce la visualizzazione delle matrici. È disponibile solo se viene specificata l'opzione **-detail**.|
|*Indirizzo assembly* \<**DumpAssembly**>|Visualizza informazioni su un assembly.<br /><br /> Il comando **DumpAssembly** elenca più moduli, se esistenti.<br /><br /> È possibile ottenere l'indirizzo di un assembly usando il comando **DumpDomain**.|
|**DumpClass** \<> *Indirizzo EEClass*|Visualizza informazioni sulla struttura `EEClass` associata a un tipo.<br /><br /> Il comando **DumpClass** visualizza valori di campi statici e non visualizza valori di campi non statici.<br /><br /> Usare il comando **DumpMT**, **DumpObj**, **Name2EE** o **Token2EE** per ottenere l'indirizzo di una struttura `EEClass`.|
|**DumpDomain** [\<*indirizzo dominio*>]|Enumera tutti gli oggetti <xref:System.Reflection.Assembly> caricati all'interno dell'indirizzo dell'oggetto <xref:System.AppDomain> specificato.  In caso di chiamata senza parametri, il comando **DumpDomain** elenca tutti gli oggetti <xref:System.AppDomain> in un processo.|
|**DumpHeap** [ **-Stat**] [ **-Strings**] **[-short**] [ **-min** \<*size*>] **[-Max** \<*size*>] [ **-thinlock**] [ **-startAtLowerBound**] [ **-mt** \<*MethodTable Address*>] [ **-Type** \<nome del *tipo parziale*>] [*Start* [*end*]]|Visualizza le informazioni sull'heap sottoposto a procedura di Garbage Collection e le statistiche di raccolta relative agli oggetti.<br /><br /> Il comando **DumpHeap** visualizza un avviso se rileva una frammentazione eccessiva nell'heap del Garbage Collector.<br /><br /> L'opzione **-stat** limita l'output al riepilogo di tipo statistico.<br /><br /> L'opzione **-strings** limita l'output a un riepilogo di valori di stringa statistici.<br /><br /> L'opzione **-short** limita l'output al solo indirizzo di ogni oggetto. In tal modo, è possibile inviare facilmente l'output dal comando a un altro comando del debugger per l'automazione.<br /><br /> L'opzione **-min** ignora gli oggetti minori del parametro `size`, specificato in byte.<br /><br /> L'opzione **-max** ignora gli oggetti maggiori del parametro `size`, specificato in byte.<br /><br /> L'opzione **-thinlock** segnala la presenza di ThinLock.  Per altre informazioni, vedere il comando **SyncBlk**.<br /><br /> L'opzione `-startAtLowerBound` forza l'inizio del percorso nell'heap al limite inferiore di un intervallo di indirizzi specificato. Durante la fase della pianificazione, l'heap spesso non è percorribile perché gli oggetti vengono spostati. Questa opzione forza **DumpHeap** a iniziare il percorso al limite inferiore specificato. È necessario fornire l'indirizzo di un oggetto valido come limite inferiore affinché questa opzione funzioni. È possibile visualizzare la memoria in corrispondenza dell'indirizzo di un oggetto non valido per trovare manualmente la tabella dei metodi successiva. Se il processo di Garbage Collection è attualmente impegnato in una chiamata a `memcopy`, è possibile riuscire a trovare l'indirizzo dell'oggetto successivo anche aggiungendo la dimensione all'indirizzo iniziale, fornito come parametro.<br /><br /> L'opzione **-mt** elenca solo gli oggetti che corrispondono alla struttura `MethodTable` specificata.<br /><br /> L'opzione **-type** elenca solo gli oggetti il cui nome di tipo è una sottostringa corrispondente alla stringa specificata.<br /><br /> Il parametro `start` inizia l'elenco a partire dall'indirizzo specificato.<br /><br /> Il parametro `end` arresta l'elenco in corrispondenza dell'indirizzo specificato.|
|**DumpIL** \<*oggetto DynamicMethod gestito*> &#124;\<*puntatore DynamicMethodDesc*> &#124;\<*puntatore MethodDesc*>|Visualizza il linguaggio MSIL (Microsoft Intermediate Language) associato a un metodo gestito.<br /><br /> Il codice MSIL dinamico è generato in modo diverso rispetto al codice MSIL caricato da un assembly. Il codice MSIL dinamico fa riferimento agli oggetti in una matrice di oggetti gestiti anziché ai token di metadati.|
|**Dumplog** [ **-addr** \<*AddressOfStressLog*>] [<*FILENAM*`e`>]|Scrive nel file specificato il contenuto di un log di stress in memoria. Se non si specifica un nome, questo comando crea un file denominato StressLog.txt nella directory corrente.<br /><br /> Il log di stress in memoria facilita la diagnosi degli errori da stress senza utilizzare blocchi o I/O. Per abilitare il log di stress, impostare le chiavi del Registro di sistema seguenti in HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework:<br /><br /> (DWORD) StressLog = 1<br /><br /> (DWORD) LogFacility = 0xffffffff<br /><br /> (DWORD) StressLogSize = 65536<br /><br /> L'opzione `-addr` facoltativa consente di specificare un log di stress diverso dal log predefinito.|
|**DumpMD** \<> *Indirizzo MethodDesc*|Visualizza informazioni su una struttura `MethodDesc` in corrispondenza dell'indirizzo specificato.<br /><br /> È possibile usare il comando **IP2MD** per ottenere l'indirizzo della struttura `MethodDesc` da una funzione gestita.|
|**DumpMT** [ **-MD**] \<*indirizzo MethodTable*>|Visualizza informazioni su una tabella dei metodi in corrispondenza dell'indirizzo specificato. Specificando l'opzione **-MD** è possibile visualizzare un elenco di tutti i metodi definiti con l'oggetto.<br /><br /> Ogni oggetto gestito contiene un puntatore alla tabella dei metodi.|
|**DumpMethodSig** \<*sigaddr*> <*moduleadd*`r`>|Visualizza informazioni su una struttura `MethodSig` in corrispondenza dell'indirizzo specificato.|
|**DumpModule** [ **-mt**] \<*indirizzo modulo*>|Visualizza informazioni su un modulo in corrispondenza dell'indirizzo specificato. L'opzione **-mt** visualizza i tipi definiti in un modulo e i tipi a cui fa riferimento il modulo.<br /><br /> È possibile usare il comando **DumpDomain** o **DumpAssembly** per recuperare l'indirizzo di un modulo.|
|**DumpObj** [ **-nofields**] \<*indirizzo oggetto*><br /><br /> oppure<br /><br /> **\<** *indirizzo oggetto*>|Visualizza informazioni su un oggetto in corrispondenza dell'indirizzo specificato. Il comando **DumpObj** visualizza i campi, le informazioni sulla struttura `EEClass`, la tabella dei metodi e la dimensione dell'oggetto.<br /><br /> È possibile usare il comando **DumpStackObjects** per recuperare l'indirizzo di un oggetto.<br /><br /> Il comando **DumpObj** può essere eseguito sui campi di tipo `CLASS` perché sono anch'essi oggetti.<br /><br /> L'opzione `-`**nofields** impedisce la visualizzazione dei campi dell'oggetto. Utile per gli oggetti di tipo String.|
|**DumpRuntimeTypes**|Visualizza gli oggetti di tipo runtime nell'heap del Garbage Collector ed elenca i nomi dei tipi e le tabelle dei metodi associati.|
|**DumpStack** [ **-EE**] [ **-n**] [ *stack* di`top` [`bottom` *STAC*`k`]]|Visualizza l'analisi di uno stack.<br /><br /> L'opzione **-EE** fa sì che il comando **DumpStack** visualizzi solo funzioni gestite. Utilizzare i parametri `top` e `bottom` per limitare gli stack frame visualizzati sulle piattaforme x86.<br /><br /> L'opzione **-n** disabilita la visualizzazione dei nomi dei file di origine e dei numeri di riga. Se nel debugger è specificata l'opzione SYMOPT_LOAD_LINES, verranno ricercati i simboli di ogni frame gestito e, in caso di esito positivo, verranno visualizzati il nome del file di origine e il numero di riga corrispondenti. È possibile specificare il parametro **-n** (nessun numero di riga) per disabilitare questo comportamento.<br /><br /> Nelle piattaforme x86 e x64 il comando **DumpStack** crea un'analisi dello stack dettagliata.<br /><br /> Nelle piattaforme basate su IA-64 il comando **DumpStack** simula il comando **K** del debugger. I parametri `top` e `bottom` vengono ignorati sulle piattaforme basate su IA-64.|
|**DumpSig** \<*sigaddr*> \<*moduleaddr*>|Visualizza informazioni su una struttura `Sig` in corrispondenza dell'indirizzo specificato.|
|**DumpSigElem** \<*sigaddr*> \<*moduleaddr*>|Visualizza un singolo elemento di un oggetto firma. Nella maggior parte dei casi va usato il comando **DumpSig** per analizzare singoli oggetti firma. Se tuttavia una firma è stata danneggiata in qualche modo, è possibile usare **DumpSigElem** per leggerne le parti valide.|
|**DumpStackObjects** [ **-Verify**] [ *stack* di`top` [ *stack*`bottom`]]<br /><br /> oppure<br /><br /> **DSO** [ **-Verify**] [ *stack* di`top` [ *stack*`bottom`]]|Visualizza tutti gli oggetti gestiti trovati nell'ambito dei limiti dello stack corrente.<br /><br /> L'opzione **-verify** convalida tutti i campi `CLASS` non statici di un campo dell'oggetto.<br /><br /> Usare il comando **DumpStackObject** con i comandi di analisi dello stack, ad esempio i comandi **K** e **CLRStack**, per determinare i valori di parametri e variabili locali.|
|**DumpVC** \<*MethodTable Address*> \<*Address*>|Visualizza informazioni sui campi di una classe di valori in corrispondenza dell'indirizzo specificato.<br /><br /> Il parametro **MethodTable** consente al comando **DumpVC** di interpretare correttamente i campi. Le classi di valori non dispongono di una tabella dei metodi come primo campo.|
|**EEHeap** [ **-gc**] [ **-loader**]|Visualizza informazioni sulla memoria di processo utilizzata dalle strutture dati CLR interne.<br /><br /> Le opzioni **-gc** e **-loader** limitano l'output di questo comando alle strutture dati del Garbage Collector o del caricatore.<br /><br /> Le informazioni relative al Garbage Collector elencano gli intervalli di ogni segmento nell'heap gestito.  Se il puntatore è compreso nell'intervallo di segmenti specificato da **-gc**, si tratta del puntatore a un oggetto.|
|**EEStack** [ **-short**] [ **-EE**]|Esegue il comando **DumpStack** su tutti i thread del processo.<br /><br /> L'opzione **-EE** viene passata direttamente al comando **DumpStack**. Il parametro **-short** limita l'output ai seguenti tipi di thread:<br /><br /> Thread che sono stati sottoposti a un blocco.<br /><br /> Thread bloccati per consentire un processo di Garbage Collection.<br /><br /> Thread che sono attualmente nel codice gestito.|
|**EEVersion**|Visualizza la versione di CLR.|
|**EHInfo** [\<*indirizzo MethodDesc*>] [\<*indirizzo codice*>]|Visualizza i blocchi di gestione delle eccezioni in un metodo specificato.  Questo comando visualizza gli indirizzi e gli offset del codice per il blocco della clausola (il blocco `try`) e il blocco del gestore (il blocco `catch`).|
|**FAQ**|Visualizza le domande frequenti.|
|**FinalizeQueue** [ **-detail**] &#124; [ **-allReady**] [ **-short**]|Visualizza tutti gli oggetti registrati per la finalizzazione.<br /><br /> L'opzione **-detail** visualizza informazioni aggiuntive su eventuali oggetti `SyncBlocks` da pulire ed eventuali oggetti `RuntimeCallableWrappers` (RCW) in attesa di pulizia. Entrambe le strutture dati vengono memorizzate nella cache e pulite dal thread del finalizzatore in esecuzione.<br /><br /> L'opzione `-allReady` visualizza tutti gli oggetti pronti per la finalizzazione, indipendentemente dal fatto che siano già contrassegnati dall'operazione di Garbage Collection o se saranno contrassegnati dalla prossima operazione di Garbage Collection. Gli oggetti che sono nell'elenco "pronti per la finalizzazione" sono oggetti finalizzabili senza più radice. Questa opzione può essere molto costosa, perché verifica se tutti gli oggetti nelle code finalizzabili contengono ancora una radice.<br /><br /> L'opzione `-short` limita l'output all'indirizzo di ogni oggetto. Se usata insieme a **-allReady**, enumera tutti gli oggetti con un finalizzatore che non contengono più una radice. Se utilizzata in modo indipendente, elenca tutti gli oggetti nelle code di oggetti finalizzabili e "pronti per la finalizzazione".|
|Indirizzo dell' *oggetto* \<**FindAppDomain**>|Determina il dominio applicazione di un oggetto in corrispondenza dell'indirizzo specificato.|
|**FindRoots** **-gen** \<*N*> &#124; **-gen qualsiasi** &#124;\<*indirizzo oggetto*>|Determina l'interruzione dell'oggetto del debug da parte del debugger alla raccolta successiva della generazione specificata. L'effetto viene reimpostato appena si verifica l'interruzione. Per impostare l'interruzione alla raccolta successiva, è necessario emettere nuovamente il comando. Il formato *\<indirizzo oggetto>* del comando viene usato dopo l'interruzione causata da **-gen** o **-gen any**. In quel momento l'oggetto del debug è nello stato appropriato per consentire a **FindRoots** di identificare le radici degli oggetti dalle generazioni condannate correnti.|
|**GCHandles** [ **-perdomain**]|Visualizza le statistiche relative agli handle del Garbage Collector nel processo.<br /><br /> L'opzione **-perdomain** organizza le statistiche per dominio dell'applicazione.<br /><br /> Usare il comando **GCHandles** per trovare perdite di memoria causate da perdite degli handle del Garbage Collector. Una perdita di memoria si verifica ad esempio se nel codice viene mantenuta una matrice di grandi dimensioni perché un handle sicuro del Garbage Collector che punta ancora a essa viene eliminato senza liberarla.|
|**GCHandleLeaks**|Ricerca nella memoria i riferimenti a handle sicuri e bloccati del Garbage Collector nel processo e visualizza i risultati. Se viene trovato un handle, il comando **GCHandleLeaks** visualizza l'indirizzo del riferimento. Se invece in memoria non viene trovato alcun handle, il comando visualizza una notifica.|
|**GCInfo** \<*indirizzo MethodDesc*>\<*indirizzo del codice*>|Visualizza i dati che indicano quando nei registri o nei percorsi dello stack sono contenuti oggetti gestiti. Se si verifica un'operazione di Garbage Collection, il Garbage Collector deve conoscere le posizioni dei riferimenti agli oggetti in modo da poterli aggiornare con i nuovi valori dei puntatori agli oggetti.|
|**GCRoot** [ **-nostacks**] \<*indirizzo oggetto*>|Visualizza informazioni sui riferimenti (o radici) a un oggetto in corrispondenza dell'indirizzo specificato.<br /><br /> Il comando **GCRoot** esamina l'intero heap gestito e la tabella degli handle per cercare gli handle in altri oggetti e handle nello stack. In ogni stack viene quindi eseguita la ricerca dei puntatori agli oggetti. Viene eseguita la ricerca anche nella coda del finalizzatore.<br /><br /> Questo comando non determina se la radice di uno stack è valida o viene ignorata. Usare i comandi **CLRStack** e **U** per disassemblare il frame a cui appartiene il valore dell'argomento o quello locale per poter determinare se la radice dello stack è ancora in uso.<br /><br /> L'opzione **-nostacks** restringe l'ambito della ricerca agli handle del Garbage Collector e agli oggetti raggiungibili.|
|*Indirizzo dell'oggetto\<GCWhere >*|Visualizza il percorso e le dimensioni dell'argomento passato nell'heap di Garbage Collection. Quando l'argomento rientra nell'heap gestito ma non è un indirizzo di oggetto valido, la dimensione viene visualizzata come 0 (zero).|
|**help** [\<*comando*>] [`faq`]|Visualizza tutti i comandi disponibili se non è specificato alcun parametro oppure visualizza informazioni di Guida dettagliate sul comando specificato.<br /><br /> Il parametro `faq` visualizza le risposte alle domande frequenti.|
|**HeapStat** [ **-inclUnrooted** &#124; **-iu**]|Visualizza le dimensioni della generazione per ogni heap e lo spazio disponibile totale in ogni generazione su ogni heap. Se viene specificata l'opzione -**inclUnrooted**, il report include informazioni sugli oggetti gestiti dall'heap di Garbage Collection che non contiene più una radice.|
|**HistClear**|Rilascia tutte le risorse utilizzate dalla famiglia di comandi `Hist`.<br /><br /> In genere non è necessario chiamare in modo esplicito `HistClear`, perché ogni `HistInit` pulisce le risorse precedenti.|
|**HistInit**|Inizializza le strutture SOS dal log di stress salvato nell'oggetto del debug.|
|**HistObj** *\<obj_address >*|Esamina tutti i record delle rilocazioni del log di stress e visualizza la catena di rilocazioni di Garbage Collection che hanno potuto condurre all'indirizzo passato come argomento.|
|**HistObjFind** *\<obj_address >*|Visualizza tutte le voci del log che fanno riferimento a un oggetto in corrispondenza dell'indirizzo specificato.|
|*> radice\<* HistRoot|Visualizza informazioni correlate sia alle promozioni sia alle rilocazioni della radice specificata.<br /><br /> Il valore radice può essere utilizzato per tenere traccia del movimento di un oggetto attraverso le operazioni di Garbage Collection.|
|Indirizzo del *codice* \<**IP2MD**>|Visualizza la struttura `MethodDesc` in corrispondenza dell'indirizzo specificato nel codice con compilazione JIT.|
|`ListNearObj` (`lno`) *\<obj_address>*|Visualizza gli oggetti che precedono e seguono l'indirizzo specificato. Il comando cerca l'indirizzo nell'heap di Garbage Collection che sembra un inizio valido di un oggetto gestito (in base a una tabella dei metodi valida) e l'oggetto che segue l'indirizzo dell'argomento.|
|**MinidumpMode** [**0**] [**1**]|Impedisce l'esecuzione di comandi non sicuri quando si utilizza un minidump.<br /><br /> Passare **0** per disabilitare la funzionalità o **1** per abilitarla. Per impostazione predefinita, il valore **MinidumpMode** è impostato su **0**.<br /><br /> I minidump creati con il comando **.dump /m** o **.dump** contengono una quantità limitata di dati specifici di CLR e consentono la corretta esecuzione solo di un subset di comandi SOS. È possibile che alcuni comandi abbiano esito negativo con errori imprevisti perché aree richieste di memoria non sono mappate o sono mappate solo parzialmente. Questa opzione impedisce l'esecuzione di comandi non sicuri sui minidump.|
|**Name2EE** \<*nome del modulo*> \<*nome del tipo o del metodo*><br /><br /> oppure<br /><br /> **Name2EE** \<*nome del modulo*> **!** \<il *nome del tipo o del metodo*>|Visualizza le strutture `MethodTable` e `EEClass` per il tipo o il metodo specificato nel modulo specificato.<br /><br /> Il modulo specificato deve essere caricato nel processo.<br /><br /> Per ottenere il nome del tipo corretto, esplorare il modulo usando [Ildasm.exe (Disassembler IL)](ildasm-exe-il-disassembler.md). È inoltre possibile passare `*` come parametro del nome del modulo per eseguire la ricerca in tutti i moduli gestiti caricati. Il parametro *nome modulo* può anche essere il nome del debugger di un modulo, ad esempio `mscorlib` o `image00400000`.<br /><br /> Questo comando supporta la sintassi del debugger Windows di <`module`>`!`<`type`>. Il tipo deve essere completo.|
|**ObjSize** [\<*indirizzo oggetto*>] &#124; [ **-aggregate**] [ **-stat**]|Visualizza la dimensione dell'oggetto specificato. Se non si specifica alcun parametro, il comando **ObjSize** visualizza la dimensione di tutti gli oggetti trovati nei thread gestiti, visualizza tutti gli handle del Garbage Collector nel processo e somma la dimensione di tutti gli oggetti a cui puntano tali handle. Il comando **ObjSize** include la dimensione di tutti gli oggetti figlio oltre a quella dell'entità principale.<br /><br /> L'opzione **-aggregate** può essere usata con l'argomento **-stat** per ottenere una visualizzazione dettagliata dei tipi che contengono ancora una radice. Usando **!dumpheap -stat** e **!objsize -aggregate -stat** è possibile determinare quali oggetti non contengono più una radice e diagnosticare vari problemi relativi alla memoria.|
|**PrintException** [ **-nested**] [ **-lines**] [\<*indirizzo oggetto Exception*>]<br /><br /> oppure<br /><br /> **PE** [ **-nested**] [\<*indirizzo oggetto Exception*>]|Visualizza e formatta i campi di qualsiasi oggetto derivato dalla classe <xref:System.Exception> in corrispondenza dell'indirizzo specificato. Se non si specifica un indirizzo, il comando **PrintException** visualizza l'ultima eccezione generata nel thread corrente.<br /><br /> L'opzione **-nested** visualizza dettagli sugli oggetti eccezione annidati.<br /><br /> L'opzione **-lines** visualizza informazioni sull'origine, se disponibili.<br /><br /> È possibile utilizzare questo comando per formattare e visualizzare il campo `_stackTrace`, che è una matrice binaria.|
|**ProcInfo** [ **-env**] [ **-time**] [ **-mem**]|Visualizza le variabili di ambiente del processo, il tempo CPU del kernel e le statistiche di utilizzo della memoria.|
|**RCWCleanupList** \<> *Indirizzo RCWCleanupList*|Visualizza l'elenco di Runtime Callable Wrapper in corrispondenza dell'indirizzo specificato che sono in attesa di pulizia.|
|**SaveModule** \<*indirizzo di base*> \<*filename*>|Scrive nel file specificato un'immagine caricata in memoria in corrispondenza dell'indirizzo specificato.|
|**SOSFlush**|Scarica la cache SOS interna.|
|**StopOnException** [ **-derived**] [ **-create** &#124; **-create2**] \<*eccezione*> \<*numero pseudo-registro*>|Determina l'arresto del debugger solo quando viene generata l'eccezione specificata, consentendo la continuazione dell'esecuzione quando vengono generate altre eccezioni.<br /><br /> L'opzione **-derived** rileva l'eccezione specificata e tutte le eccezioni che derivano da essa.|
|**SyncBlk** [ **-all** &#124; \<*numero syncblk*>]|Visualizza la struttura `SyncBlock` specificata o tutte le strutture `SyncBlock`.  Se non si passano argomenti, il comando **SyncBlk** visualizza la struttura `SyncBlock` che corrisponde agli oggetti di proprietà di un thread.<br /><br /> Una struttura `SyncBlock` è un contenitore per informazioni aggiuntive che non deve essere creato per ogni oggetto. Può contenere dati di interoperabilità COM, codici hash e informazioni di blocco per operazioni thread-safe.|
|**ThreadPool**|Visualizza informazioni sul pool di thread gestiti, tra cui il numero di richieste di lavoro nella coda, il numero di thread della porta di completamento e il numero di timer.|
|**Token2EE** \<*nome del modulo*> \<*token*>|Trasforma il token di metadati specificato del modulo specificato in una struttura `MethodTable` o `MethodDesc`.<br /><br /> È possibile passare `*` come parametro del nome del modulo per trovare il mapping del token in ogni modulo gestito caricato. È anche possibile passare il nome del debugger di un modulo, ad esempio `mscorlib` o `image00400000`.|
|**Threads** [ **-live**] [ **-special**]|Visualizza tutti i thread gestiti del processo.<br /><br /> Il comando **Threads** visualizza l'ID abbreviato del debugger, l'ID del thread di CLR e l'ID del thread del sistema operativo.  Il comando **Threads** visualizza anche una colonna Domain in cui viene indicato il dominio dell'applicazione in cui è in esecuzione un thread, una colonna APT in cui viene indicata la modalità apartment COM e una colonna Exception in cui viene visualizzata l'ultima eccezione generata nel thread.<br /><br /> L'opzione **-live** visualizza i thread associati a un thread attivo.<br /><br /> L'opzione **-special** visualizza tutti i thread speciali creati da CLR. Tra i thread speciali sono inclusi i thread della Garbage Collection (nell'esecuzione contemporanea e su server), i thread di supporto del debugger, i thread del finalizzatore, i thread di scaricamento di <xref:System.AppDomain> e i thread di timer del pool di thread.|
|*Campo del valore dello stato* del **\<ThreadState** **>**|Visualizza lo stato del thread. Il parametro `value` è il valore del campo `State` nell'output del report **Threads**.<br /><br /> Esempio:<br /><br /> `0:003> !Threads     ThreadCount:      2     UnstartedThread:  0     BackgroundThread: 1     PendingThread:    0     DeadThread:       0     Hosted Runtime:   no                                           PreEmptive   GC Alloc           Lock            ID OSID ThreadOBJ    State     GC       Context       Domain   Count APT Exception        0    1  250 0019b068      a020 Disabled 02349668:02349fe8 0015def0     0 MTA        2    2  944 001a6020      b220 Enabled  00000000:00000000 0015def0     0 MTA (Finalizer)     0:003> !ThreadState b220         Legal to Join         Background         CLR Owns         CoInitialized         In Multi Threaded Apartment`|
|**TraverseHeap** [ **-xml**] \<*nomefile*>|Scrive informazioni sull'heap nel file specificato, in un formato leggibile dal profiler CLR. L'opzione **-xml** fa sì che il comando **TraverseHeap** formatti il file come XML.<br /><br /> Il profiler CLR può essere scaricato dall'[Area download Microsoft](https://go.microsoft.com/fwlink/?LinkID=67325).|
|**U** [ **-gcinfo**] [ **-ehinfo**] [ **-n**] \<*indirizzo MethodDesc*> &#124; \<*indirizzo codice*>|Visualizza un disassembly annotato di un metodo gestito specificato da un puntatore alla struttura `MethodDesc` del metodo o da un indirizzo di codice all'interno del corpo del metodo. Il comando **U** visualizza l'intero metodo dall'inizio alla fine, con annotazioni che convertono i token di metadati in nomi.<br /><br /> L'opzione **-gcinfo** fa sì che il comando **U** visualizzi la struttura `GCInfo` del metodo.<br /><br /> L'opzione **-ehinfo** visualizza informazioni sulle eccezioni del metodo. È possibile ottenere queste informazioni anche con il comando **EHInfo**.<br /><br /> L'opzione **-n** disabilita la visualizzazione dei nomi dei file di origine e dei numeri di riga. Se nel debugger è specificata l'opzione SYMOPT_LOAD_LINES, vengono ricercati i simboli di ogni frame gestito e, in caso di esito positivo, vengono visualizzati il nome del file di origine e il numero di riga corrispondenti. È possibile specificare l'opzione **-n** per disabilitare questo comportamento.|
|**VerifyHeap**|Cerca segni di danneggiamento nell'heap del Garbage Collector e visualizza gli eventuali errori trovati.<br /><br /> L'heap può danneggiarsi a causa di chiamate di pInvoke costruite in modo non corretto.|
|Indirizzo dell' *oggetto* \<**VerifyObj**>|Cerca segni di danneggiamento nell'oggetto passato come argomento.|
|**VMMap**|Attraversa lo spazio degli indirizzi virtuali e visualizza il tipo di protezione applicato a ogni regione.|
|**VMStat**|Fornisce una visualizzazione di riepilogo dello spazio degli indirizzi virtuali, ordinata in base a ogni tipo di protezione applicato alla memoria (free, reserved, committed, private, mapped, image). La colonna TOTAL visualizza il risultato della colonna AVERAGE moltiplicato per la colonna BLK COUNT.|

## <a name="remarks"></a>Note

L'estensione del debugger SOS consente di visualizzare informazioni sul codice in esecuzione nell'ambiente CLR. È ad esempio possibile utilizzarla per visualizzare informazioni sull'heap gestito, cercare eventuali danneggiamenti dell'heap, visualizzare i tipi di dati interni utilizzati dal runtime e visualizzare informazioni su tutto il codice gestito in esecuzione nel runtime.

Per usare l'estensione del debugger SOS in Visual Studio, installare [Windows Driver Kit (WDK)](/windows-hardware/drivers/download-the-wdk). Per informazioni sull'ambiente di debug integrato in Visual Studio, vedere la pagina [Debugging Environments](/windows-hardware/drivers/debugger/debuggers-in-the-debugging-tools-for-windows-package) (Ambienti di debug).

È anche possibile usare l'estensione del debugger SOS caricandola nel debugger [WinDbg.exe](/windows-hardware/drivers/debugger/debugger-download-tools) ed eseguendo i comandi in WinDbg.exe.

Per caricare l'estensione del debugger SOS nel debugger WinDbg.exe, eseguire il comando riportato sotto nello strumento:

```console
.loadby sos clr
```

In WinDbg.exe e Visual Studio viene utilizzata una versione di SOS.dll che corrisponde alla versione di Mscorwks.dll attualmente in uso. Per impostazione predefinita, è necessario utilizzare la versione di SOS.dll che corrisponde alla versione corrente di Mscorwks.dll.

Per utilizzare un file dump creato in un altro computer, assicurarsi che il file Mscorwks.dll fornito con l'installazione sia contenuto nel percorso dei simboli e caricare la versione corrispondente di SOS.dll.

Per caricare una versione specifica di SOS.dll, digitare il comando seguente nel debugger Windows:

```console
.load <full path to sos.dll>
```

## <a name="examples"></a>Esempi

Il comando riportato di seguito visualizza il contenuto di una matrice in corrispondenza dell'indirizzo `00ad28d0`.  La visualizzazione parte dal secondo elemento e continua per cinque elementi.

```console
!dumparray -start 2 -length 5 -detail 00ad28d0
```

Il comando riportato di seguito visualizza il contenuto di un assembly in corrispondenza dell'indirizzo `1ca248`.

```console
!dumpassembly 1ca248
```

Il comando riportato di seguito visualizza informazioni sull'heap del Garbage Collector.

```console
!dumpheap
```

Il comando riportato di seguito scrive il contenuto del log di stress in memoria in un file (predefinito) denominato StressLog.tx nella directory corrente.

```console
!DumpLog
```

Il comando riportato di seguito visualizza la struttura `MethodDesc` in corrispondenza dell'indirizzo `902f40`.

```console
!dumpmd 902f40
```

Il comando riportato di seguito visualizza informazioni su un modulo in corrispondenza dell'indirizzo `1caa50`.

```console
!dumpmodule 1caa50
```

Il comando riportato di seguito visualizza informazioni su un oggetto in corrispondenza dell'indirizzo `a79d40`.

```console
!DumpObj a79d40
```

Il comando riportato di seguito visualizza i campi di una classe di valori in corrispondenza dell'indirizzo `00a79d9c` utilizzando la tabella dei metodi in corrispondenza dell'indirizzo `0090320c`.

```console
!DumpVC 0090320c 00a79d9c
```

Il comando riportato di seguito visualizza la memoria di processo utilizzata dal Garbage Collector.

```console
!eeheap -gc
```

Il comando riportato di seguito visualizza tutti gli oggetti per i quali è pianificata la finalizzazione.

```console
!finalizequeue
```

Il comando riportato di seguito determina il dominio applicazione di un oggetto in corrispondenza dell'indirizzo `00a79d98`.

```console
!findappdomain 00a79d98
```

Il comando riportato di seguito visualizza tutti gli handle del Garbage Collector nel processo corrente.

```console
!gcinfo 5b68dbb8
```

Il comando riportato di seguito visualizza le strutture `MethodTable` e `EEClass` per il metodo `Main` nella classe `MainClass` nel modulo `unittest.exe`.

```console
!name2ee unittest.exe MainClass.Main
```

Il comando riportato di seguito visualizza informazioni sul token di metadati in corrispondenza dell'indirizzo `02000003` nel modulo `unittest.exe`.

```console
!token2ee unittest.exe 02000003
```

## <a name="see-also"></a>Vedere anche

- [Strumenti](index.md)
- [Prompt dei comandi](developer-command-prompt-for-vs.md)
