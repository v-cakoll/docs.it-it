---
title: Prompt dei comandi per gli sviluppatori per Visual Studio
description: Informazioni su come usare la Prompt dei comandi per gli sviluppatori per Visual Studio, che consente di usare gli strumenti .NET in modo più semplice. Imposta automaticamente variabili di ambiente specifiche.
ms.date: 01/05/2020
helpviewer_keywords:
- command prompt, Windows SDK
- Visual Studio command prompt
- command prompt, Visual Studio
- SDK command prompt
- tools [.NET Framework], setting environment variables
- environment variables, setting for tools
- developer command prompt
ms.assetid: 94fcf524-9045-4993-bfb2-e2d8bad44219
ms.openlocfilehash: 92416820f47cb778dfcc916b8626df4aa328814c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167173"
---
# <a name="developer-command-prompt-for-visual-studio"></a>Prompt dei comandi per gli sviluppatori per Visual Studio

Prompt dei comandi per gli sviluppatori per Visual Studio consente di usare gli strumenti di .NET Framework più facilmente. Si tratta di un prompt dei comandi che imposta automaticamente variabili di ambiente specifiche. Dopo l'apertura di Prompt dei comandi per gli sviluppatori, è possibile immettere i comandi per [.NET Framework strumenti](index.md) , ad esempio `ildasm` o `clrver` .

## <a name="prerequisites"></a>Prerequisiti

- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)

## <a name="search-for-the-command-prompt-on-your-machine"></a>Cercare il prompt dei comandi nel computer

È possibile che siano presenti più prompt dei comandi, a seconda della versione di Visual Studio e di eventuali SDK e carichi di lavoro aggiuntivi installati. Se i passaggi seguenti non funzionano, è possibile provare a [individuare manualmente i file nel computer](#manually-locate-the-files-on-your-machine) o [avviare il prompt dei comandi dall'interno di Visual Studio](#start-the-command-prompt-from-inside-visual-studio).

### <a name="windows-10"></a>Windows 10

1. Selezionare **Avvia** ![ il tasto logo Windows sulla tastiera.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png) e scorrere fino alla lettera **V**.

1. Espandere la cartella **Visual Studio 2019** .

1. Scegliere **prompt dei comandi per gli sviluppatori per VS 2019** (o il prompt dei comandi che si vuole usare).

   In alternativa, è possibile iniziare a digitare il nome del prompt dei comandi nella casella di ricerca sulla barra delle applicazioni e scegliere il risultato desiderato, perché l'elenco dei risultati inizia a visualizzare le corrispondenze di ricerca.

   ![Gif animata che mostra il comportamento di ricerca in Windows 10](./media/developer-command-prompt-for-vs/windows10-search.gif)

### <a name="windows-81"></a>Windows 8.1

1. Andare alla schermata **Start** ad esempio premendo il tasto WINDOWS![tasto WINDOWS sulla tastiera.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png) sulla tastiera.

1. Nella schermata **Start** premere **CTRL** + **Tab** per aprire l'elenco **app** e quindi premere **V**. Viene visualizzato un elenco che include tutti i prompt dei comandi di Visual Studio installati.

1. Scegliere **prompt dei comandi per gli sviluppatori per VS 2019** (o il prompt dei comandi che si vuole usare).

### <a name="windows-7"></a>Windows 7

1. Scegliere **Start** , quindi espandere **tutti i programmi**.

1. Scegliere **Visual Studio 2019**  >  **strumenti di Visual Studio**  >  **prompt dei comandi per gli sviluppatori per vs 2019**o il prompt dei comandi che si vuole usare.

   ![Menu Start di Windows 7 con il prompt dei comandi evidenziato](./media/developer-command-prompt-for-vs/windows7-menu.png)

Se sono installati altri SDK, ad esempio [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) o [versioni precedenti](https://developer.microsoft.com/windows/downloads/sdk-archive), è possibile visualizzare prompt dei comandi aggiuntivi. Consultare la documentazione dei diversi strumenti per determinare quale versione del prompt dei comandi usare.

## <a name="manually-locate-the-files-on-your-machine"></a>Trovare manualmente i file nel computer

In genere, i collegamenti per i prompt dei comandi installati vengono inseriti nella cartella del **menu Start** per Visual Studio, ad esempio in *%ProgramData%\Microsoft\Windows\Start Menu\Programs\Visual Studio 2019 \ strumenti di Visual Studio*. Tuttavia, se per qualche motivo la ricerca del prompt dei comandi non produce i risultati previsti, è possibile provare a individuare manualmente il collegamento nel computer. Provare a cercare il nome del file del prompt dei comandi, ad esempio *VsDevCmd.bat*, oppure passare alla cartella strumenti, ad esempio *% ProgramFiles (x86)% \ Microsoft Visual Studio\2019\Community\Common7\Tools* (percorso modificato in base alla versione, all'edizione e al percorso di installazione di Visual Studio).

## <a name="start-the-command-prompt-from-inside-visual-studio"></a>Avviare il prompt dei comandi dall'interno di Visual Studio

Per semplificare l'accesso, è possibile aggiungere Prompt dei comandi per gli sviluppatori o qualsiasi altro prompt dei comandi al menu strumenti in Visual Studio. Per rendere lo strumento disponibile, aggiungerlo all'elenco degli strumenti esterni. Seguire questa procedura:

1. Aprire Visual Studio.

1. Nella finestra iniziale scegliere **Continua senza codice**.

1. Sulla barra dei menu scegliere **strumenti**strumenti  >  **esterni**.

1. Nella finestra di dialogo **Strumenti esterni** scegliere il pulsante **Aggiungi**. Verrà visualizzata una nuova voce.

1. Immettere un **titolo** per la nuova voce di menu, ad esempio `Command Prompt`.

1. Nel campo **comando** specificare il file che si vuole avviare, ad esempio `%comspec%` o `C:\Windows\System32\cmd.exe` .

1. Nel campo **argomenti** specificare dove trovare il prompt dei comandi specifico che si desidera utilizzare, ad esempio `/k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\Tools\VsDevCmd.bat"` . Questo comando avvia il Prompt dei comandi per gli sviluppatori installato con la community di Visual Studio 2019. Modificare questo valore in base al percorso di installazione, alla versione e all'edizione di Visual Studio.

1. Nel campo **directory iniziale** specificare la directory in cui verrà avviato il prompt dei comandi. Scegliere un valore, ad esempio **Directory progetto** , selezionando la freccia accanto al campo.

1. Fare clic su **OK** .

   ![Finestra di dialogo strumenti esterni con i valori del campo compilati.](./media/developer-command-prompt-for-vs/add-external-tool.png)

   Verrà aggiunta la nuova voce di menu e sarà possibile accedere al prompt dei comandi dal menu Strumenti.

   ![Voce di menu del prompt dei comandi in Visual Studio](./media/developer-command-prompt-for-vs/command-prompt-vs-menu.png)

## <a name="see-also"></a>Vedere anche

- [Strumenti di .NET Framework](index.md)
- [Gestione di strumenti esterni](/visualstudio/ide/managing-external-tools)
- [Usare il set di strumenti di Microsoft C++ dalla riga di comando](/cpp/build/building-on-the-command-line)
