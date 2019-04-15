---
title: Prompt dei comandi per gli sviluppatori per Visual Studio
ms.date: 08/14/2018
helpviewer_keywords:
- command prompt, Windows SDK
- Visual Studio command prompt
- command prompt, Visual Studio
- SDK command prompt
- tools [.NET Framework], setting environment variables
- environment variables, setting for tools
- developer command prompt
ms.assetid: 94fcf524-9045-4993-bfb2-e2d8bad44219
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cc88106a54a00b4b12e5043da7961791a98102c0
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59344364"
---
# <a name="developer-command-prompt-for-visual-studio"></a>Prompt dei comandi per gli sviluppatori per Visual Studio

Il Prompt dei comandi per gli sviluppatori per Visual Studio consente di usare più facilmente gli strumenti di .NET Framework. Questo prompt dei comandi imposta automaticamente variabili di ambiente specifiche.

> [!div class="button"]
> [Scaricare Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)

## <a name="search-for-the-command-prompt-on-your-machine"></a>Cercare il prompt dei comandi nel computer

Si potrebbero avere più prompt dei comandi, in base alla versione di Visual Studio e agli SDK aggiuntivi installati. Ad esempio, le versioni a 64 bit di Visual Studio forniscono prompt dei comandi sia a 32 bit che a 64 bit. Le versioni a 32 bit e a 64 bit della maggior parte degli strumenti sono uguali; tuttavia, alcuni strumenti apportano modifiche specifiche per gli ambienti a 32 bit e a 64 bit. Se i passaggi seguenti non funzionano, è possibile provare [Trovare manualmente i file nel computer](#manually-locate-the-files-on-your-machine) o [Eseguire il prompt dei comandi dall'interno di Visual Studio](#run-the-command-prompt-from-inside-visual-studio).

### <a name="in-windows-10"></a>In Windows 10

1. Nella casella di ricerca della barra delle applicazioni iniziare a digitare il nome dello strumento, ad esempio `dev` o `developer command prompt`. Verrà visualizzato un elenco di app installate che corrispondono ai criteri di ricerca. Se si sta cercando un prompt dei comandi diverso, provare a immettere un termine di ricerca diverso, ad esempio `prompt`.

2. Scegliere **Prompt dei comandi per gli sviluppatori per Visual Studio** (o il prompt dei comandi che si vuole usare).

### <a name="in-windows-81"></a>In Windows 8.1

1. Aprire la schermata **Start** premendo il tasto del ![logo Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") sulla tastiera.

2. Nella schermata **Start** premere **CTRL**+**TAB** per aprire l'elenco **App** e quindi immettere `V`. Verrà visualizzato un elenco che include tutti i prompt dei comandi di Visual Studio installati.

3. Scegliere **Prompt dei comandi per gli sviluppatori** (o il prompt dei comandi che si vuole usare).

### <a name="in-windows-8"></a>In Windows 8

1. Aprire la schermata **Start** premendo il tasto del ![logo Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") sulla tastiera.

2. Nella schermata **Start** premere il tasto del ![logo Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.

3. Scegliere l'icona **Visualizzazione App** nella parte inferiore della schermata e quindi immettere `V`. Verrà visualizzato un elenco che include tutti i prompt dei comandi di Visual Studio installati.

4. Scegliere **Prompt dei comandi per gli sviluppatori** (o il prompt dei comandi che si vuole usare).

### <a name="in-windows-7"></a>In Windows 7

1. Scegliere **Start**, espandere **Tutti i programmi** e quindi espandere **Microsoft Visual Studio**.

2. A seconda della versione di Visual Studio installata, scegliere **Strumenti di Visual Studio**, **Prompt dei comandi di Visual Studio** o il prompt dei comandi che si vuole usare.

Se ci sono altri SDK installati, ad esempio [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) o [versioni precedenti](https://developer.microsoft.com/windows/downloads/sdk-archive), si potranno notare prompt dei comandi aggiuntivi per le architetture ARM, x86 o x64. Consultare la documentazione dei diversi strumenti per determinare quale versione del prompt dei comandi usare.

## <a name="manually-locate-the-files-on-your-machine"></a>Trovare manualmente i file nel computer

In genere, i collegamenti per i prompt dei comandi installati verranno posizionati nella cartella **Menu Start** per Visual Studio, ad esempio in C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools. Tuttavia, se per qualche motivo la ricerca del prompt dei comandi non produce i risultati previsti, è possibile provare a trovare manualmente il collegamento nel computer. Provare a cercare il nome del file del prompt dei comandi, ad esempio *VsDevCmd.bat* o passare alla cartella Tools, ad esempio C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools (il percorso cambierà a seconda del percorso di installazione, della versione e dell'edizione di Visual Studio).

## <a name="run-the-command-prompt-from-inside-visual-studio"></a>Eseguire il prompt dei comandi dall'interno di Visual Studio

Per semplificare l'accesso, è possibile aggiungere il prompt dei comandi per gli sviluppatori Visual Studio o qualsiasi altro prompt dei comandi al menu **Strumenti** in Visual Studio. Per rendere lo strumento disponibile, aggiungerlo all'elenco degli strumenti esterni. Di seguito la procedura:

1. Aprire Visual Studio.

2. Selezionare il menu **Strumenti** e quindi scegliere **Strumenti esterni**.

3. Nella finestra di dialogo **Strumenti esterni** scegliere il pulsante **Aggiungi**. Verrà visualizzata una nuova voce.

4. Immettere un **titolo** per la nuova voce di menu, ad esempio `Command Prompt`.

5. Nel campo **Comando** specificare il file che si vuole avviare, ad esempio `%comspec%` o `C:\Windows\System32\cmd.exe`.

6. Nel campo **Argomenti** specificare dove trovare il prompt dei comandi specifico da usare, ad esempio `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (verrà avviato il Prompt dei comandi per gli sviluppatori installato con Visual Studio 2017 Enterprise). Modificare questo valore in base al percorso di installazione, alla versione e all'edizione di Visual Studio.

7. Scegliere un valore per il campo **Directory iniziale**, ad esempio **Directory di progetto**.

8. Fare clic sul pulsante **OK** .

   Verrà aggiunta la nuova voce di menu e sarà possibile accedere al prompt dei comandi dal menu **Strumenti**.

   ![Voce di menu del prompt dei comandi in Visual Studio](media/command-prompt-vs-menu.png)

## <a name="see-also"></a>Vedere anche

- [Strumenti](../../../docs/framework/tools/index.md)
- [Gestione di strumenti esterni](/visualstudio/ide/managing-external-tools)
