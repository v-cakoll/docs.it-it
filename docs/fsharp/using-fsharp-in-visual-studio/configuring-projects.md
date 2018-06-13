---
title: 'Configurazione di progetti (F #)'
description: 'Informazioni su come utilizzare la finestra di progettazione del progetto quando si lavora con progetti F # in Visual Studio.'
ms.date: 05/16/2016
ms.openlocfilehash: a6c9539945bbd32748ffca1434c984402bc3f17b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565464"
---
# <a name="configuring-projects-in-visual-studio"></a>Configurazione di progetti in Visual Studio

> [!NOTE]
In questo articolo non è aggiornato con il più recente di Visual Studio.  Verrà eseguito un aggiornamento.

Questo argomento include informazioni sull'utilizzo di **progettazione** quando si lavora con progetti F #. Lavorare con progetti F # non è notevolmente diverso dall'utilizzo di progetti Visual Basic o c#. Quando si usa F # è spesso possibile utilizzare la documentazione di progetto di Visual Studio generale come riferimento principale. In questo argomento vengono forniti collegamenti a informazioni pertinenti nella documentazione di Visual Studio per le impostazioni che vengono condivisi con altri linguaggi di Visual Studio e descrive inoltre le impostazioni specifiche di F #.

## <a name="project-designer"></a>Progettazione progetti
Il **progettazione** e il relativo utilizzo generale vengono descritti dettagliatamente nella sezione [Introduzione a Progettazione progetti](https://msdn.microsoft.com/library/898dd854-c98d-430c-ba1b-a913ce3c73d7) nella documentazione di Visual Studio. Il **progettazione** è costituito da più pagine, raggruppate per funzionalità correlate. Le pagine disponibili per i progetti F # sono per lo più un subset di quelle disponibili per altri linguaggi. Le pagine supportate in F # sono descritti nella tabella seguente. Le pagine che non sono disponibili sono relative a funzionalità che non sono disponibili in F # o che sono disponibili solo tramite la modifica di un'opzione della riga di comando. Le pagine che sono disponibili in F # sono simili alle pagine c# maggiormente, in modo rilevante c# è disponibile un collegamento **progettazione** pagina.

|Pagina di Progettazione progetti|Collegamenti correlati|Descrizione|
|---------------------|-------------|-----------|
|`Application`|[Pagina applicazione, Progettazione progetti &#40;C&#35;&#41;](https://msdn.microsoft.com/library/ms247046.aspx)|Consente di specificare le impostazioni a livello di applicazione e proprietà, ad esempio se si sta creando una libreria o un file eseguibile, la versione di .NET Framework è destinata l'applicazione e informazioni in cui il file di risorse dell'applicazione Usa viene archiviati.|
|`Build`|[Pagina compilazione, Progettazione progetti &#40;C&#35;&#41;](https://msdn.microsoft.com/library/kb4wyys2.aspx)|Consente di controllare la modalità con cui il codice viene compilato.|
|`Build Events`|[Pagina eventi di compilazione, Progettazione progetti &#40;C&#35;&#41;](https://msdn.microsoft.com/library/kb4wyys2.aspx)|Consente di specificare i comandi da eseguire prima o dopo una compilazione.|
|`Debug`|[Pagina Debug, Creazione progetti](https://msdn.microsoft.com/library/2wcdezs5.aspx)|Consente di controllare l'esecuzione dell'applicazione durante il debug. Sono incluse la riga di comando da utilizzare e qual è la directory dell'applicazione iniziale e qualsiasi speciale che si desidera abilitare, ad esempio SQL e codice nativo modalità di debug.|
|`Reference Paths`|[Gestione dei riferimenti in un progetto](/visualstudio/ide/managing-references-in-a-project)|Consente di specificare la posizione in cui cercare gli assembly che dipende dal codice.|

## <a name="f-specific-settings"></a>F #-impostazioni specifiche
Nella tabella seguente vengono riepilogate le impostazioni specifiche di F #:

|Pagina di Progettazione progetti|Impostazione|Descrizione|
|---------------------|-------|-----------|
|`Build`|`Generate tail calls`|Se selezionata, consente l'utilizzo della coda di istruzione Microsoft intermediate language (MSIL). In questo modo lo stack frame debba essere riutilizzate per le funzioni ricorsive tail. Equivale al `--tailcalls` l'opzione del compilatore.|
|`Build`|`Other flags`|Consente di specificare ulteriori opzioni del compilatore da riga di comando.|

## <a name="see-also"></a>Vedere anche
 [Introduzione a F # in Visual Studio](../get-started/get-started-visual-studio.md)  
 [Opzioni del compilatore](../language-reference/compiler-options.md)  
 [Introduzione a Creazione progetti](https://msdn.microsoft.com/library/898dd854-c98d-430c-ba1b-a913ce3c73d7(v=vs.100))
