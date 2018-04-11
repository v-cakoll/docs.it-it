---
title: Opzioni del compilatore (F#)
description: 'Utilizzare opzioni della riga di comando del compilatore F # per controllare la compilazione di App F # e librerie.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c797cf0b-5953-4053-8626-0558e9eaf10f
ms.openlocfilehash: 23731832141bc2f74a04c5f4027fc210b5589537
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/10/2018
---
# <a name="compiler-options"></a>Opzioni del compilatore

In questo argomento vengono descritte le opzioni della riga di comando del compilatore per il compilatore F #, fsc.exe. L'ambiente di compilazione può anche essere controllata impostando le proprietà del progetto.


## <a name="compiler-options-listed-alphabetically"></a>Opzioni del compilatore elencate in ordine alfabetico
La tabella seguente illustra le opzioni del compilatore elencate in ordine alfabetico. Alcune delle opzioni del compilatore F # sono simili alle opzioni del compilatore c#. Se è questo il caso, viene fornito un collegamento all'argomento di opzioni del compilatore c#.



|Opzione del compilatore|Descrizione|
|---------------|-----------|
|**-a****&lt;output-filename&gt;**|Genera una libreria e specifica il nome del file. Questa opzione è una versione abbreviata di **-target: library *&lt;filename&gt;**.|
|**--baseaddress:&lt;string&gt;**|Specifica l'indirizzo di base della libreria da compilare.<br /><br />L'opzione del compilatore è equivalente all'opzione del compilatore c# con lo stesso nome. Per altre informazioni, vedere [ &#47;indirizzo di base &#40;C&#35; opzioni del compilatore&#41;](https://msdn.microsoft.com/library/2fdbz5xd.aspx).|
|**--codepage:&lt;int&gt;**|Specifica la tabella codici utilizzata per leggere i file di origine.<br /><br />L'opzione del compilatore è equivalente all'opzione del compilatore c# con lo stesso nome. Per altre informazioni, vedere [ &#47;tabella codici &#40;C&#35; opzioni del compilatore&#41;](https://msdn.microsoft.com/library/w0kyekyh.aspx).|
|**--consolecolors**|Specifica che gli errori e avvisi utilizzano testo con codifica a colori nella console.|
|**--crossoptimize**[**+**&#124;**-**]|Abilita o disabilita le ottimizzazioni tra i moduli.|
|**--delaysign**[**+**&#124;**-**]|Ritarda la firma dell'assembly utilizzando solo la parte pubblica della chiave con nome sicuro.<br /><br />L'opzione del compilatore è equivalente all'opzione del compilatore c# con lo stesso nome. Per altre informazioni, vedere [ &#47;delaysign &#40;C&#35; opzioni del compilatore&#41;](https://msdn.microsoft.com/library/ta1sxwy8.aspx).|
|**--checked**[**+**&#124;**-**]|Abilita o disabilita la generazione di controllo dell'overflow.<br /><br />L'opzione del compilatore è equivalente all'opzione del compilatore c# con lo stesso nome. Per altre informazioni, vedere [ &#47;archiviato &#40;C&#35; opzioni del compilatore&#41;](https://msdn.microsoft.com/library/h25wtyxf.aspx).|
|**--debug**[**+**&#124;**-**]<br /><br />**-g**[**+**&#124;**-**]<br /><br />**--debug**:[**full**&#124;**pdbonly**]<br /><br />**-g:** [**full**&#124;**pdbonly**]|Abilita o disabilita la generazione delle informazioni di debug o specifica il tipo di informazioni di debug da generare. Il valore predefinito è completo, che consente l'associazione a un programma in esecuzione. Scegliere **pdbonly** per ottenere informazioni di debug limitate archiviate in un file pdb (database di programma).<br /><br />Equivalente all'opzione del compilatore c# con lo stesso nome. Per altre informazioni, vedere<br /><br />[&#47;il debug di &#40;C&#35; le opzioni del compilatore&#41;](https://msdn.microsoft.com/library/8cw0bt21.aspx).|
|**--define:&lt;string&gt;**<br /><br />**-d:&lt;string&gt;**|Definisce un simbolo per l'utilizzo nella compilazione condizionale.|
|**--deterministic**[**+**&#124;**-**]|Generare un assembly deterministico (inclusi i GUID di versione del modulo e timestamp).  Questo non può essere utilizzato con numeri di versione con caratteri jolly e supporta solo tipi di debug incorporati e portatili|
|**--doc:&lt;xmldoc-filename&gt;**|Indica al compilatore di generare commenti della documentazione XML per il file specificato. Per ulteriori informazioni, vedere [documentazione XML](xml-documentation.md).<br /><br />L'opzione del compilatore è equivalente all'opzione del compilatore c# con lo stesso nome. Per altre informazioni, vedere [ &#47;documenti &#40;C&#35; opzioni del compilatore&#41;](https://msdn.microsoft.com/library/3260k4x7.aspx).|
|**--fullpaths**|Indica al compilatore di generare percorsi completi.<br /><br />L'opzione del compilatore è equivalente all'opzione del compilatore c# con lo stesso nome. Per altre informazioni, vedere [ &#47;/fullpaths &#40;C&#35; opzioni del compilatore&#41;](https://msdn.microsoft.com/library/d315xc66.aspx).|
|**--help**<br /><br />**-?**|Consente di visualizzare informazioni sull'utilizzo, inclusa una breve descrizione di tutte le opzioni del compilatore.|
|**--highentropyva**[**+**&#124;**-**]|Abilitare o disabilitare un'entropia elevata ASLR address space layout randomization (), una funzionalità di sicurezza avanzata. Il sistema operativo genera casualmente le posizioni di memoria in cui viene caricato infrastruttura per applicazioni (ad esempio stack e heap). Se si abilita questa opzione, i sistemi operativi è possibile utilizzare questa sequenza casuale per usare la completa 64-bit-spazio degli indirizzi in un computer a 64 bit.|
|**--keycontainer:&lt;string&gt;**|Specifica un contenitore di chiavi con nome sicuro.|
|**-keyfile:&lt;filename&gt;**|Specifica il nome di un file di chiave pubblica per firmare l'assembly generato.|
|**-lib:&lt;-nome della cartella&gt;**<br /><br />**-Ricerca per categorie:&lt;-nome della cartella&gt;**|Specifica una directory in cui cercare gli assembly a cui fa riferimento.<br /><br />L'opzione del compilatore è equivalente all'opzione del compilatore c# con lo stesso nome. Per altre informazioni, vedere [ &#47;lib &#40;C&#35; opzioni del compilatore&#41;](https://msdn.microsoft.com/library/s5bac5fx.aspx).|
|**--linkresource**:**&lt;resource-info&gt;**|Collega una risorsa specificata all'assembly. Il formato di risorsa-info *filename*[,*nome*[,*pubblica*&#124;*privata*]]<br /><br />Il collegamento di una singola risorsa con questa opzione è un'alternativa all'incorporamento di un intero file di risorse con il **-risorse** opzione.<br /><br />L'opzione del compilatore è equivalente all'opzione del compilatore c# con lo stesso nome. Per altre informazioni, vedere [ &#47;/linkresource &#40;C&#35; opzioni del compilatore&#41;](https://msdn.microsoft.com/library/xawyf94k.aspx).|
|**--mlcompatibility**|Ignora gli avvisi che vengono visualizzati quando si utilizzano funzionalità che sono progettate per compatibilità con altre versioni di ML.|
|**--noframework**|Disabilita il riferimento predefinito per l'assembly di .NET Framework.|
|**--nointerfacedata**|Indica al compilatore di omettere la risorsa che viene generalmente aggiunta a un assembly che include F #-metadati specifici.|
|**--nologo**|Quando si avvia il compilatore, non viene visualizzato il testo dell'intestazione.|
|**--nooptimizationdata**|Indica al compilatore di includere solo ottimizzazione essenziali per l'implementazione di costrutti inline. Impedisce intramodulo ma migliora la compatibilità binaria.|
|**--nowin32manifest**|Indica al compilatore di omettere il manifesto Win32 predefinito.|
|**--nowarn:&lt;int-list&gt;**|Disabilita avvisi specifici elencati in base al numero. Separare ogni numero di avviso da una virgola. È possibile individuare il numero di avviso per qualsiasi avviso nell'output della compilazione.<br /><br />L'opzione del compilatore è equivalente all'opzione del compilatore c# con lo stesso nome. Per altre informazioni, vedere [ &#47;/nowarn &#40;C&#35; opzioni del compilatore&#41;](https://msdn.microsoft.com/library/7f28x9z3.aspx).|
|**--optimize**[**+**&#124;**-**]**[&lt;string-list&gt;]**<br /><br />**-O [+&#124;-] [&lt;elenco di stringhe&gt;]**|Abilita o disabilita le ottimizzazioni. Alcune opzioni di ottimizzazione possono essere disabilitati o abilitati in modo selettivo elencandole. Questi sono: **nojitoptimize**, **nojittracking**, **nolocaloptimize**, **nocrossoptimize**, **notailcalls**.|
|**--out:&lt;output-filename&gt;**<br /><br />**-o:&lt;output-filename&gt;**|Specifica il nome dell'assembly compilato o del modulo.<br /><br />L'opzione del compilatore è equivalente all'opzione del compilatore c# con lo stesso nome. Per altre informazioni, vedere [ &#47;out &#40;C&#35; opzioni del compilatore&#41;](https://msdn.microsoft.com/library/bw3t50f3.aspx).|
|**--pdb:&lt;pdb-filename&gt;**|Nome del file di output debug PDB (database di programma). Questa opzione è applicabile solo quando **-debug** è attivato.<br /><br />L'opzione del compilatore è equivalente all'opzione del compilatore c# con lo stesso nome. Per altre informazioni, vedere [ &#47;pdb &#40;C&#35; opzioni del compilatore&#41;](https://msdn.microsoft.com/library/ms228625.aspx).|
|**--platform:&lt;platform-name&gt;**|Specifica che il codice generato verrà eseguito solo nella piattaforma specificata (**x86**, **Itanium**, o **x64**), oppure, se il nome della piattaforma **anycpu**viene scelto, specifica che il codice generato può essere eseguito su qualsiasi piattaforma.<br /><br />L'opzione del compilatore è equivalente all'opzione del compilatore c# con lo stesso nome. Per altre informazioni, vedere [ &#47;della piattaforma &#40;C&#35; opzioni del compilatore&#41;](https://msdn.microsoft.com/library/zekwfyz4.aspx).|
|**--preferreduilang:&lt;lang&gt;**| Specifica il nome di impostazioni cultura della lingua di output preferita (ad esempio, es-ES, ja-JP). |
|**--quotations-debug**|Specifica che le informazioni di debug aggiuntive devono essere generata per le espressioni che sono derivate dai valori letterali di quotation F # e riportate le definizioni. Le informazioni di debug viene aggiunto per gli attributi personalizzati di un nodo dell'albero dell'espressione F #. Vedere [quotation di codice](code-quotations.md) e [CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).|
|**--reference:&lt;assembly-filename&gt;**<br /><br />**-r** &lt;**assembly-filename&gt;**|Rende codice da un assembly F # o .NET Framework disponibili per il codice in fase di compilazione.<br /><br />L'opzione del compilatore è equivalente all'opzione del compilatore c# con lo stesso nome. Per altre informazioni, vedere [ &#47;riferimenti &#40;C&#35; opzioni del compilatore&#41;](https://msdn.microsoft.com/library/yabyz3h4.aspx).|
|**-resource:&lt;nome file di risorse&gt;**|Incorpora un file di risorse gestite nell'assembly generato.<br /><br />L'opzione del compilatore è equivalente all'opzione del compilatore c# con lo stesso nome. Per altre informazioni, vedere [ &#47;risorse &#40;C&#35; opzioni del compilatore&#41;](https://msdn.microsoft.com/library/c0tyye07.aspx).|
|**-sig**:&lt;**firma-nome del file&gt;**|Genera un file di firma in base all'assembly generato. Per ulteriori informazioni sui file di firma, vedere [firme](signatures.md).|
|**--simpleresolution**|Specifica che i riferimenti agli assembly devono essere risolti mediante regole Mono basate su directory anziché la risoluzione MSBuild. Il valore predefinito consiste nell'utilizzare la risoluzione MSBuild tranne quando è in esecuzione in Mono.|
|**--standalone**|Specifica per produrre un assembly che contiene tutte le relative dipendenze in modo da poterlo da sola senza la necessità di assembly aggiuntivi, ad esempio la libreria F #.|
|**--staticlink:&lt;assembly-name**&gt;|Collega in modo statico l'assembly specificato e tutte le DLL a cui fa riferimento che dipendono da questo assembly. Utilizzare il nome dell'assembly, non il nome della DLL.|
|**--subsystemversion**|Specifica la versione del sottosistema del sistema operativo deve essere utilizzato dal file eseguibile generato. Utilizzare 6.02 per Windows 8.1, 6.01 per Windows 7, 6,00 per Windows Vista. Questa opzione solo si applica ai file eseguibili, DLL non e debba essere usata solo se l'applicazione dipende dalle funzionalità di sicurezza specifici disponibili solo in alcune versioni del sistema operativo. Questa opzione viene utilizzata, se un utente tenta di eseguire l'applicazione su una versione precedente del sistema operativo, avrà esito negativo con un messaggio di errore.|
|**--tailcalls**[**+**&#124;**-**]|Abilita o disabilita l'utilizzo dell'istruzione tail, determinando lo stack frame debba essere riutilizzate per le funzioni ricorsive tail. Questa opzione è attivata per impostazione predefinita.|
|**--target**:[**exe** &#124; **winexe** &#124; **library** &#124; **module** ] **&lt;output-filename&gt;**|Specifica il tipo e il nome del codice compilato generato.<ul><li>**file exe** significa che un'applicazione console.<br /></li><li>**winexe** significa che un'applicazione Windows, che è diverso dall'applicazione console, in quanto non dispone di flussi di input/output standard (stdin, stdout e stderr) definiti.<br /></li><li>**libreria** è un assembly senza un punto di ingresso.<br /></li><li>**modulo** è un modulo .NET Framework (con estensione netmodule), che può essere combinato in un secondo momento con altri moduli in un assembly.<br /></li><ul/>L'opzione del compilatore è equivalente all'opzione del compilatore c# con lo stesso nome. Per altre informazioni, vedere [ &#47;destinazione &#40;C&#35; opzioni del compilatore&#41;](https://msdn.microsoft.com/library/6h25dztx.aspx).|
|**-volte**|Consente di visualizzare le informazioni di intervallo per la compilazione.|
|**--utf8output**|Consente di stampare l'output del compilatore nella codifica UTF-8.|
|**-Avviso:&lt;a livello di avviso&gt;**|Imposta un livello di avviso (da 0 a 5). Il livello predefinito è 3. Ogni avviso viene visualizzato un livello in base alla gravità. Livello 5 offre più e meno avvisi gravi, di livello 1.<br /><br />Gli avvisi di livello 5 sono: (utilizzo ricorsivo controllato in fase di esecuzione) 21, 22 (**let rec** valutata non in ordine), 45 (astrazione completa) e 52 (copia difensivo). Tutti gli altri avvisi sono il livello 2.<br /><br />L'opzione del compilatore è equivalente all'opzione del compilatore c# con lo stesso nome. Per altre informazioni, vedere [ &#47;avviso &#40;C&#35; opzioni del compilatore&#41;](https://msdn.microsoft.com/library/13b90fz7.aspx).|
|**--warnon:&lt;int-list&gt;**|Abilita avvisi specifici che potrebbero essere disattivato per impostazione predefinita o disabilitato da un'altra opzione della riga di comando. F # 3.0, solo l'avviso 1182 (variabili inutilizzate) è disattivata per impostazione predefinita.|
|**--warnaserror**[**+**&#124;**-**] [**&lt;int-list&gt;**]|Abilita o disabilita l'opzione di segnalazione degli avvisi come errori. È possibile fornire numeri di avviso specifici per abilitare o disabilitare. Opzioni in un secondo momento nella riga di comando ignorano le opzioni in precedenza nella riga di comando. Per specificare gli avvisi che non si desidera segnalati come errori, ad esempio, è consigliabile specificare **- warnaserror + - warnaserror-:&lt;int-list&gt;**.<br /><br />L'opzione del compilatore è equivalente all'opzione del compilatore c# con lo stesso nome. Per altre informazioni, vedere [ &#47;/warnaserror &#40;C&#35; opzioni del compilatore&#41;](https://msdn.microsoft.com/library/406xhdz3.aspx).|
|**--win32manifest:manifest-filename**|Aggiunge un file manifesto Win32 per la compilazione. L'opzione del compilatore è equivalente all'opzione del compilatore c# con lo stesso nome. Per altre informazioni, vedere [ &#47;win32manifest &#40;C&#35; opzioni del compilatore&#41;](https://msdn.microsoft.com/library/bb545961.aspx).|
|**--win32res:resource-filename**|Aggiunge un file di risorse Win32 per la compilazione.<br /><br />L'opzione del compilatore è equivalente all'opzione del compilatore c# con lo stesso nome. Per altre informazioni, vedere [ &#47;win32res (&#40;C & #35); Opzioni del compilatore&#41;](https://msdn.microsoft.com/library/8f2f5x2e.aspx).|

## <a name="related-topics"></a>Argomenti correlati


|Titolo|Descrizione|
|-----|-----------|
|[Opzioni di F# Interactive](fsharp-interactive-options.md)|Vengono descritte le opzioni della riga di comando supportate dall'interprete F #, fsi.exe.|
|[Riferimenti alle proprietà di progetto](/visualstudio/ide/reference/project-properties-reference)|Descrive l'interfaccia utente per i progetti, incluse le pagine di proprietà di progetto che forniscono le opzioni di compilazione.|
