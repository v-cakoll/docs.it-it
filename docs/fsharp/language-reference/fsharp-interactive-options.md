---
title: Opzioni interattive
description: Informazioni sulle opzioni della riga di comando supportate da F# Interactive, FSI. exe.
ms.date: 05/16/2016
ms.openlocfilehash: cceb8fb50434f3525ebb2ede16e84720d10d320c
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348232"
---
# <a name="f-interactive-options"></a>Opzioni di F# Interactive

> [!NOTE]
> Questo articolo illustra attualmente solo l'esperienza per Windows.  Verrà riscritto.

In questo argomento vengono descritte le opzioni della riga di F# comando supportate da interactive `fsi.exe`. F#Interactive accetta molte delle stesse opzioni della riga di comando F# del compilatore, ma accetta anche alcune opzioni aggiuntive.

## <a name="using-f-interactive-for-scripting"></a>Uso F# di Interactive per lo scripting

F#Interactive, `fsi.exe`, può essere avviato in modo interattivo oppure può essere avviato dalla riga di comando per eseguire uno script. La sintassi della riga di comando è

```console
> fsi.exe [options] [ script-file [arguments] ]
```

L'estensione di file F# per i file di script è `.fsx`.

## <a name="table-of-f-interactive-options"></a>Tabella delle F# opzioni interattive

Nella tabella seguente sono riepilogate le opzioni supportate F# da Interactive. È possibile impostare queste opzioni nella riga di comando o tramite l'IDE di Visual Studio. Per impostare queste opzioni nell'IDE di Visual Studio, aprire il menu **strumenti** , selezionare **Opzioni...** , quindi espandere il  **F# nodo strumenti** e selezionare  **F# interattivo**.

Se gli elenchi sono F# visualizzati in argomenti di opzioni interattive, gli elementi elenco sono separati da punti e virgola (`;`).

|Opzione|Descrizione|
|------|-----------|
|**--**|Utilizzato per indicare F# a interattivo di considerare gli argomenti rimanenti come argomenti della F# riga di comando per il programma o lo script, a cui è possibile accedere nel codice utilizzando l'elenco **FSI. CommandLineArgs**.|
|**--checked**[ **+** &#124; **-** ]|Uguale all'opzione del compilatore **FSC. exe** . Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**--tabella codici:&lt;int&gt;**|Uguale all'opzione del compilatore **FSC. exe** . Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**--consolecolors**[ **+** &#124; **-** ]|Restituisce i messaggi di avviso e di errore a colori.|
|**--crossoptimize**[ **+** &#124; **-** ]|Abilitare o disabilitare le ottimizzazioni tra i moduli.|
|**--debug**[ **+** &#124; **-** ]<br /><br />**--debug:** [**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]<br /><br />**-g**[ **+** &#124; **-** ]<br /><br />**-g:** [**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]|Uguale all'opzione del compilatore **FSC. exe** . Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**--define:&lt;stringa&gt;**|Uguale all'opzione del compilatore **FSC. exe** . Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**--deterministic**[ **+** &#124; **-** ]|Produce un assembly deterministico (incluso il GUID e il timestamp della versione del modulo).|
|**--exec**|Indica a F# Interactive di uscire dopo il caricamento dei file o l'esecuzione del file di script specificato nella riga di comando.|
|**--fullpaths**|Uguale all'opzione del compilatore **FSC. exe** . Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**--gui**[ **+** &#124; **-** ]|Abilita o Disabilita il ciclo di eventi Windows Forms. Per impostazione predefinita questi stili sono abilitati.|
|**--help**<br /><br />**-?**|Utilizzato per visualizzare la sintassi della riga di comando e una breve descrizione di ogni opzione.|
|**--lib:&lt;Folder-List&gt;**<br /><br />**-I:&lt;cartella-list&gt;**|Uguale all'opzione del compilatore **FSC. exe** . Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**--Load:&lt;filename&gt;**|Compila il codice sorgente specificato all'avvio e carica i costrutti F# compilati nella sessione. Se l'origine di destinazione contiene direttive di scripting, ad esempio **#use** o **#load**, è necessario usare **--use** o **#use** anziché **--Load** o **#load**.|
|**--mlcompatibility**|Uguale all'opzione del compilatore **FSC. exe** . Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**--noframework**|Uguale all'opzione del compilatore **FSC. exe** . Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md)|
|**--nologo**|Uguale all'opzione del compilatore **FSC. exe** . Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**--nowarn:&lt;avviso-elenco&gt;**|Uguale all'opzione del compilatore **FSC. exe** . Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**--optimize**[ **+** &#124; **-** ]|Uguale all'opzione del compilatore **FSC. exe** . Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**--preferreduilang:&lt;lang&gt;**| Specifica il nome delle impostazioni cultura della lingua di output preferito, ad esempio es-ES, ja-JP. |
|**--quiet**|Consente F# di non visualizzare l'output interattivo nel flusso **stdout** .|
|**--quotations-debug**|Specifica che le informazioni di debug aggiuntive devono essere emesse per le espressioni derivate da F# valori letterali di virgolette e definizioni riflesse. Le informazioni di debug vengono aggiunte agli attributi personalizzati di un F# nodo dell'albero delle espressioni. Vedere le [citazioni di codice](code-quotations.md) e [expr. CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).|
|**--readline**[ **+** &#124; **-** ]|Abilitare o disabilitare il completamento tramite tasto TAB in modalità interattiva.|
|**--Reference:&lt;filename&gt;**<br /><br />**-r:&lt;filename&gt;**|Uguale all'opzione del compilatore **FSC. exe** . Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**--shadowcopyreferences**[ **+** &#124; **-** ]|Impedisce che i F# riferimenti vengano bloccati dal processo interattivo.|
|**--simpleresolution**|Risolve i riferimenti ad assembly usando regole basate su directory anziché la risoluzione di MSBuild.|
|**--tailcalls**[ **+** &#124; **-** ]|Abilitare o disabilitare l'utilizzo dell'istruzione il tail, che fa in modo che la stack frame venga riutilizzata per le funzioni tail ricorsive. Per impostazione predefinita, questa casella di controllo è selezionata.|
|**--targetprofile:&lt;string&gt;**|Specifica il profilo del Framework di destinazione dell'assembly. I valori validi sono mscorlib, Netcore o netstandard.  Il valore predefinito è mscorlib.|
|**--usare:&lt;filename&gt;**|Indica all'interprete di utilizzare il file specificato all'avvio come input iniziale.|
|**--utf8output**|Uguale all'opzione del compilatore FSC. exe. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**--WARN:&lt;&gt; a livello di avviso**|Uguale all'opzione del compilatore **FSC. exe** . Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**--warnaserror**[ **+** &#124; **-** ]|Uguale all'opzione del compilatore **FSC. exe** . Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**--warnaserror**[ **+** &#124; **-** ]: **&lt;int-list&gt;**|Uguale all'opzione del compilatore **FSC. exe** . Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|

## <a name="related-topics"></a>Argomenti correlati

|Titolo|Descrizione|
|-----|-----------|
|[Opzioni del compilatore](compiler-options.md)|Descrive le opzioni della riga di comando F# disponibili per il compilatore, **FSC. exe**.|
