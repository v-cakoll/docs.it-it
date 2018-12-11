---
title: Opzioni di F# Interactive
description: Informazioni sulle opzioni della riga di comando supportate da F# fsi.exe interattivo.
ms.date: 05/16/2016
ms.openlocfilehash: cca1ef6671878acb1b837d6590139d5de7b7167d
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128154"
---
# <a name="f-interactive-options"></a>Opzioni di F# Interactive

> [!NOTE]
> Questo articolo illustra attualmente solo l'esperienza per Windows.  Verrà riscritto.

In questo argomento vengono descritte le opzioni della riga di comando supportate da F# Interactive `fsi.exe`. F#Interactive accetta numerose le stesse opzioni della riga di comando di F# compilatore, ma accetta anche alcune opzioni aggiuntive.

## <a name="using-f-interactive-for-scripting"></a>Usando F# interattiva per lo Scripting
F#Interattivo, `fsi.exe`, possono essere avviate in modo interattivo o può essere avviata dalla riga di comando per eseguire uno script. La sintassi della riga di comando è

```
> fsi.exe [options] [ script-file [arguments] ]
```

L'estensione di file per F# file di script viene `.fsx`.

## <a name="table-of-f-interactive-options"></a>Tabella di F# opzioni interattive
Nella tabella seguente vengono riepilogate le opzioni supportate da F# Interactive. È possibile impostare queste opzioni nella riga di comando o tramite l'IDE di Visual Studio. Per impostare queste opzioni nell'IDE di Visual Studio, aprire il **degli strumenti** dal menu **opzioni...** , quindi espandere il  **F# Tools** nodo e selezionare  **F# Interactive**.

In cui sono presenti elenchi negli F# gli argomenti dell'opzione interattiva, gli elementi dell'elenco sono separati da punti e virgola (`;`).

|Opzione|Descrizione|
|------|-----------|
|**--**|Utilizzato per indicare a F# Interactive di trattare gli argomenti restanti come argomenti della riga di comando per il F# programma o script, che è possibile accedere nel codice usando l'elenco **CommandLineArgs**.|
|**--checked**[**+**&#124;**-**]|Stesso come il **fsc.exe** opzione del compilatore. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**-codepage:&lt;int&gt;**|Stesso come il **fsc.exe** opzione del compilatore. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**-consolecolors**[**+**&#124;**-**]|Output di avviso e messaggi di errore nel colore.|
|**--crossoptimize**[**+**&#124;**-**]|Abilitare o disabilitare le ottimizzazioni intramodulo.|
|**--debug**[**+**&#124;**-**]<br /><br />**-debug:**[**completa**&#124;**pdbonly**&#124;**portabile**&#124;**embedded**]<br /><br />**-g**[**+**&#124;**-**]<br /><br />**-g**[**completa**&#124;**pdbonly**&#124;**portabile**&#124;**embedded**]|Stesso come il **fsc.exe** opzione del compilatore. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**-definire:&lt;stringa&gt;**|Stesso come il **fsc.exe** opzione del compilatore. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**--deterministic**[**+**&#124;**-**]|Produce un assembly deterministico (tra cui GUID di versione del modulo e timestamp).|
|**-exec**|Indica a F# interactive di chiudersi dopo il caricamento dei file o in esecuzione il file di script fornito nella riga di comando.|
|**--fullpaths**|Stesso come il **fsc.exe** opzione del compilatore. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**--gui**[**+**&#124;**-**]|Abilita o disabilita il ciclo di eventi di Windows Form. Per impostazione predefinita questi stili sono abilitati.|
|**--help**<br /><br />**-?**|Utilizzato per visualizzare la sintassi della riga di comando e una breve descrizione di ogni opzione.|
|**-lib:&lt;elenco cartelle&gt;**<br /><br />**-Ricerca per categorie:&lt;elenco cartelle&gt;**|Stesso come il **fsc.exe** opzione del compilatore. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**-caricare:&lt;nomefile&gt;**|Compila il codice sorgente specificato all'avvio e carica compilato F# costruisce nella sessione. Se l'origine di destinazione contiene direttive di scripting, ad esempio **#use** oppure **#load**, sarà necessario usare **-usare** oppure **#use** anziché **-caricare** oppure **#load**.|
|**mlcompatibility:**|Stesso come il **fsc.exe** opzione del compilatore. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**--noframework**|Stesso come il **fsc.exe** opzione del compilatore. Per altre informazioni, vedere [opzioni del compilatore](compiler-options.md)|
|**--nologo**|Stesso come il **fsc.exe** opzione del compilatore. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**-nowarn:&lt;dall'elenco degli avvisi&gt;**|Stesso come il **fsc.exe** opzione del compilatore. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**--optimize**[**+**&#124;**-**]|Stesso come il **fsc.exe** opzione del compilatore. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**--preferreduilang:&lt;lang&gt;**| Specifica il nome delle impostazioni cultura della lingua preferita di output (ad esempio, es-ES, ja-JP). |
|**-quiet**|Eliminare F# Interactive di output per il **stdout** stream.|
|**--quotations-debug**|Specifica che le informazioni di debug aggiuntive devono essere emessi per le espressioni che derivano da F# valori letterali di quotation e definizioni riflesse. Le informazioni di debug vengono aggiunte agli attributi personalizzati di un F# nodo dell'albero dell'espressione. Visualizzare [citazioni di codice](code-quotations.md) e [CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).|
|**--readline**[**+**&#124;**-**]|Abilitare o disabilitare il completamento tramite tasto tab in modalità interattiva.|
|**: riferimento:&lt;nomefile&gt;**<br /><br />**-r:&lt;nomefile&gt;**|Stesso come il **fsc.exe** opzione del compilatore. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**-shadowcopyreferences**[**+**&#124;**-**]|Impedisce i riferimenti da bloccati dal F# processo interattivo.|
|**--simpleresolution**|Risolve i riferimenti di assembly usando regole basate su directory invece la risoluzione MSBuild.|
|**--tailcalls**[**+**&#124;**-**]|Abilitare o disabilitare l'uso dell'istruzione tail, che comporta il frame dello stack essere riutilizzata per le funzioni tail ricorsive. Questa opzione è attivata per impostazione predefinita.|
|**--targetprofile:&lt;string&gt;**|Specifica del profilo di framework di destinazione di questo assembly. I valori validi sono mscorlib, netcore o netstandard.  Il valore predefinito è mscorlib.|
|**-usare:&lt;nomefile&gt;**|Indica all'interprete di utilizzare il file specificato all'avvio come input iniziale.|
|**--utf8output**|Uguale all'opzione del compilatore fsc.exe. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**-warn:&lt;a livello di avviso&gt;**|Stesso come il **fsc.exe** opzione del compilatore. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**--warnaserror**[**+**&#124;**-**]|Stesso come il **fsc.exe** opzione del compilatore. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|
|**--warnaserror**[**+**&#124;**-**]:**&lt;int-list&gt;**|Stesso come il **fsc.exe** opzione del compilatore. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).|

## <a name="related-topics"></a>Argomenti correlati

|Titolo|Descrizione|
|-----|-----------|
|[Opzioni del compilatore](compiler-options.md)|Vengono descritte le opzioni della riga di comando disponibili per il F# compilatore **fsc.exe**.|
