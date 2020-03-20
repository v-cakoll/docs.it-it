---
title: Prompt dei comandi per gli sviluppatori per Visual Studio
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
ms.openlocfilehash: f028281d477284acf3ac4dac63f5ddbbd79f5259
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75715868"
---
# <a name="developer-command-prompt-for-visual-studio"></a>Prompt dei comandi per gli sviluppatori per Visual Studio

Developer Command Prompt per Visual Studio consente di utilizzare gli strumenti di .NET Framework più facilmente. Si tratta di un prompt dei comandi che imposta automaticamente variabili di ambiente specifiche. Dopo aver aperto il prompt dei comandi per gli sviluppatori, è possibile immettere i comandi per [gli strumenti di .NET Framework,](index.md) ad `ildasm` esempio o `clrver`.

## <a name="prerequisites"></a>Prerequisites

- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)

## <a name="search-for-the-command-prompt-on-your-machine"></a>Cercare il prompt dei comandi nel computer

È possibile disporre di più prompt dei comandi, a seconda della versione di Visual Studio e di eventuali SDK e carichi di lavoro aggiuntivi installati. Se la procedura seguente non funziona, è possibile provare a [individuare manualmente i file nel computer](#manually-locate-the-files-on-your-machine) o [avviare il prompt dei comandi dall'interno](#start-the-command-prompt-from-inside-visual-studio)di Visual Studio .

### <a name="windows-10"></a>Windows 10

1. Seleziona Il tasto Start Windows **(Avvia** ![Windows) sulla tastiera.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png) e scorrere fino alla lettera **V**.

1. Espandere la cartella **Visual Studio 2019.**

1. Scegliere Prompt dei comandi per **sviluppatori per VS 2019** (o il prompt dei comandi che si desidera utilizzare).

   In alternativa, è possibile iniziare a digitare il nome del prompt dei comandi nella casella di ricerca sulla barra delle applicazioni e scegliere il risultato desiderato quando l'elenco dei risultati inizia a visualizzare le corrispondenze di ricerca.

   ![Gif animata che mostra il comportamento di ricerca in Windows 10](./media/developer-command-prompt-for-vs/windows10-search.gif)

### <a name="windows-81"></a>Windows 8.1

1. Andare alla schermata **Start** ad esempio premendo il tasto WINDOWS![tasto WINDOWS sulla tastiera.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png) sulla tastiera.

1. Nella schermata **Start** premere **CTRL**+**TAB** per aprire l'elenco **App** e quindi premere **V**. Verrà visualizzato un elenco che include tutti i prompt dei comandi di Visual Studio installati.

1. Scegliere Prompt dei comandi per **sviluppatori per VS 2019** (o il prompt dei comandi che si desidera utilizzare).

### <a name="windows-7"></a>Windows 7

1. Scegliere **Start** , quindi **scegliere Tutti i programmi**.

1. Scegliere **Visual Studio 2019** > **Visual Studio Tools** > **Developer Command Prompt per VS 2019**o il prompt dei comandi che si desidera utilizzare.

   ![Menu Start di Windows 7 con il prompt dei comandi evidenziato](./media/developer-command-prompt-for-vs/windows7-menu.png)

Se sono installati altri SDK, ad esempio [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) o [versioni precedenti,](https://developer.microsoft.com/windows/downloads/sdk-archive)è possibile che vengano visualizzati prompt dei comandi aggiuntivi. Consultare la documentazione dei diversi strumenti per determinare quale versione del prompt dei comandi usare.

## <a name="manually-locate-the-files-on-your-machine"></a>Trovare manualmente i file nel computer

In genere, i collegamenti per i prompt dei comandi installati vengono inseriti nella cartella del **menu Start** per Visual Studio, ad esempio in *%ProgramData%*. Ma se, per qualche motivo, la ricerca del prompt dei comandi non produce i risultati previsti, è possibile provare a individuare manualmente il collegamento nel computer. Provare a cercare il nome del file del prompt dei comandi, ad esempio *VsDevCmd.bat*, oppure passare alla cartella Strumenti, ad esempio *%ProgramFiles(x86)% .*

## <a name="start-the-command-prompt-from-inside-visual-studio"></a>Avviare il prompt dei comandi dall'interno di Visual StudioStart the command prompt from inside Visual Studio

Per semplificare l'accesso, è possibile aggiungere prompt dei comandi per sviluppatori o qualsiasi altro prompt dei comandi al menu Strumenti in Visual Studio.For easier access, you can add Developer Command Prompt, or any other command prompt, to the Tools menu in Visual Studio. Per rendere lo strumento disponibile, aggiungerlo all'elenco degli strumenti esterni. I passaggi necessari sono i seguenti:

1. Aprire Visual Studio.

1. Nella finestra iniziale scegliere **Continua senza codice**.

1. Nella barra dei menu scegliere **Strumenti** > **esterni strumenti**.

1. Nella finestra di dialogo **Strumenti esterni** scegliere il pulsante **Aggiungi**. Verrà visualizzata una nuova voce.

1. Immettere un **titolo** per la nuova voce di menu, ad esempio `Command Prompt`.

1. Nel campo **Comando** specificare il file che `%comspec%` si `C:\Windows\System32\cmd.exe`desidera avviare, ad esempio o .

1. Nel campo **Argomenti** specificare dove trovare il prompt dei comandi `/k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\Tools\VsDevCmd.bat"`specifico che si desidera utilizzare, ad esempio . Questo comando avvia il prompt dei comandi per gli sviluppatori installato con la community di Visual Studio 2019. Modificare questo valore in base al percorso di installazione, alla versione e all'edizione di Visual Studio.

1. Nel campo **Directory iniziale** specificare la directory in cui verrà avviato il prompt dei comandi. Scegliere un valore, ad esempio **Directory progetto,** selezionando la freccia accanto al campo.

1. Fare clic su **OK** .

   ![Finestra di dialogo Strumenti esterni con i valori dei campi compilati.](./media/developer-command-prompt-for-vs/add-external-tool.png)

   Verrà aggiunta la nuova voce di menu e sarà possibile accedere al prompt dei comandi dal menu Strumenti.

   ![Voce di menu del prompt dei comandi in Visual Studio](./media/developer-command-prompt-for-vs/command-prompt-vs-menu.png)

## <a name="see-also"></a>Vedere anche

- [Strumenti di .NET Framework](index.md)
- [Gestione di strumenti esterni](/visualstudio/ide/managing-external-tools)
- [Utilizzare il set di strumenti Microsoft C](/cpp/build/building-on-the-command-line)
