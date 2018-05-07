---
title: Opzioni di F# Interactive
description: 'Informazioni sulle opzioni della riga di comando supportate da F # Interactive, fsi.exe.'
ms.date: 05/16/2016
ms.openlocfilehash: a461dd0eeff2de3d15e557ba37138fbd62ca43ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="f-interactive-options"></a>Opzioni di F# Interactive

> [!NOTE]
Questo articolo illustra attualmente solo l'esperienza per Windows.  Verrà riscritto.

In questo argomento vengono descritte le opzioni della riga di comando supportate da F # Interactive, `fsi.exe`. F # Interactive accetta molte delle stesse opzioni di riga di comando del compilatore F #, ma accetta inoltre alcune opzioni aggiuntive.

## <a name="using-f-interactive-for-scripting"></a>Utilizzo di F # Interactive per lo Scripting
F # Interactive, `fsi.exe`, può essere avviato in modo interattivo o può essere avviata dalla riga di comando per eseguire uno script. La sintassi della riga di comando

```
> fsi.exe [options] [ script-file [arguments] ]
```

L'estensione per i file di script F # è `.fsx`.

## <a name="table-of-f-interactive-options"></a>Tabella delle opzioni di F # Interactive
Nella tabella seguente sono riepilogate le opzioni supportate da F # Interactive. È possibile impostare queste opzioni nella riga di comando o tramite l'IDE di Visual Studio. Per impostare queste opzioni nell'IDE di Visual Studio, aprire il **strumenti** dal menu **opzioni...** , quindi espandere il **strumenti F #** nodo e selezionare **F # Interactive**.

In cui vengono visualizzati elenchi in F # Interactive argomenti dell'opzione, gli elementi di elenco sono separati da punti e virgola (`;`).

|Opzione|Descrizione|
|------|-----------|
|**--**|Utilizzato in modo che F # Interactive tratta gli argomenti rimanenti come argomenti della riga di comando per il programma F # o uno script che è possibile accedere nel codice utilizzando l'elenco **fsi. CommandLineArgs**.|
|**--checked**[**+**&#124;**-**]|Stesso come il **fsc.exe** l'opzione del compilatore. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**-codepage:&lt;int&gt;**|Stesso come il **fsc.exe** l'opzione del compilatore. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**-consolecolors**[**+**&#124;**-**]|Output di avviso e messaggi di errore nel colore.|
|**--crossoptimize**[**+**&#124;**-**]|Abilitare o disabilitare le ottimizzazioni tra i moduli.|
|**--debug**[**+**&#124;**-**]<br /><br />**-eseguire il debug:**[**completo**&#124;**pdbonly**&#124;**portabile**&#124;**incorporato**]<br /><br />**-g**[**+**&#124;**-**]<br /><br />**-g**[**completo**&#124;**pdbonly**&#124;**portabile**&#124;**incorporato**]|Stesso come il **fsc.exe** l'opzione del compilatore. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**-definire:&lt;stringa&gt;**|Stesso come il **fsc.exe** l'opzione del compilatore. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**--deterministic**[**+**&#124;**-**]|Produce un assembly deterministico (inclusi i GUID di versione del modulo e timestamp).|
|**-exec**|Indica a F # interactive per uscire dall'installazione dopo il caricamento dei file o l'esecuzione del file di script specificato nella riga di comando.|
|**--fullpaths**|Stesso come il **fsc.exe** l'opzione del compilatore. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**--gui**[**+**&#124;**-**]|Abilita o disabilita il ciclo di eventi di Windows Form. Per impostazione predefinita questi stili sono abilitati.|
|**--help**<br /><br />**-?**|Consente di visualizzare la sintassi della riga di comando e una breve descrizione di ogni opzione.|
|**-lib:&lt;elenco di cartelle&gt;**<br /><br />**-Ricerca per categorie:&lt;elenco di cartelle&gt;**|Stesso come il **fsc.exe** l'opzione del compilatore. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**-caricare:&lt;filename&gt;**|Compila il codice sorgente specificato all'avvio e carica i costrutti F # compilati nella sessione. Se l'origine di destinazione contiene le istruzioni di scripting, ad esempio **#use** o **#load**, è necessario utilizzare **-utilizzare** o **#use** anziché **-caricare** o **#load**.|
|**-mlcompatibility**|Stesso come il **fsc.exe** l'opzione del compilatore. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**--noframework**|Stesso come il **fsc.exe** l'opzione del compilatore. Per ulteriori informazioni, vedere [opzioni del compilatore](compiler-options.md)|
|**--nologo**|Stesso come il **fsc.exe** l'opzione del compilatore. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**-nowarn:&lt;-elenco di avvisi&gt;**|Stesso come il **fsc.exe** l'opzione del compilatore. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**--optimize**[**+**&#124;**-**]|Stesso come il **fsc.exe** l'opzione del compilatore. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**--preferreduilang:&lt;lang&gt;**| Specifica il nome di impostazioni cultura della lingua di output preferita (ad esempio, es-ES, ja-JP). |
|**-quiet**|Esclusione di output del F # Interactive di **stdout** flusso.|
|**--quotations-debug**|Specifica che le informazioni di debug aggiuntive devono essere generata per le espressioni che sono derivate dai valori letterali di quotation F # e riportate le definizioni. Le informazioni di debug viene aggiunto per gli attributi personalizzati di un nodo dell'albero dell'espressione F #. Vedere [quotation di codice](code-quotations.md) e [CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).|
|**--readline**[**+**&#124;**-**]|Abilitare o disabilitare il completamento tramite tab in modalità interattiva.|
|**-riferimento:&lt;filename&gt;**<br /><br />**-r:&lt;filename&gt;**|Stesso come il **fsc.exe** l'opzione del compilatore. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**-shadowcopyreferences**[**+**&#124;**-**]|Impedisce i riferimenti vengano bloccati dal processo F # Interactive.|
|**--simpleresolution**|Risolve i riferimenti di assembly mediante regole basate su directory anziché la risoluzione MSBuild.|
|**--tailcalls**[**+**&#124;**-**]|Abilitare o disabilitare l'uso dell'istruzione tail, determinando lo stack frame debba essere riutilizzate per le funzioni ricorsive tail. Questa opzione è attivata per impostazione predefinita.|
|**--targetprofile:&lt;string&gt;**|Specifica profilo del framework di destinazione di questo assembly. I valori validi sono mscorlib o netcore moniker netstandard.  Il valore predefinito è mscorlib.|
|**-utilizzare:&lt;filename&gt;**|Indica all'interprete di utilizzare il file specificato all'avvio come input iniziale.|
|**--utf8output**|Come l'opzione del compilatore fsc.exe. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**-Avviso:&lt;a livello di avviso&gt;**|Stesso come il **fsc.exe** l'opzione del compilatore. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**--warnaserror**[**+**&#124;**-**]|Stesso come il **fsc.exe** l'opzione del compilatore. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**--warnaserror**[**+**&#124;**-**]:**&lt;int-list&gt;**|Stesso come il **fsc.exe** l'opzione del compilatore. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|

## <a name="related-topics"></a>Argomenti correlati

|Titolo|Descrizione|
|-----|-----------|
|[Opzioni del compilatore](compiler-options.md)|Vengono descritte le opzioni della riga di comando disponibili per il compilatore F #, **fsc.exe**.|
