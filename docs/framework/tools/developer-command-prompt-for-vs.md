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
# <a name="developer-command-prompt-for-visual-studio"></a><span data-ttu-id="af1a7-104">Prompt dei comandi per gli sviluppatori per Visual Studio</span><span class="sxs-lookup"><span data-stu-id="af1a7-104">Developer Command Prompt for Visual Studio</span></span>

<span data-ttu-id="af1a7-105">Prompt dei comandi per gli sviluppatori per Visual Studio consente di usare gli strumenti di .NET Framework più facilmente.</span><span class="sxs-lookup"><span data-stu-id="af1a7-105">Developer Command Prompt for Visual Studio enables you to use .NET Framework tools more easily.</span></span> <span data-ttu-id="af1a7-106">Si tratta di un prompt dei comandi che imposta automaticamente variabili di ambiente specifiche.</span><span class="sxs-lookup"><span data-stu-id="af1a7-106">It's a command prompt that automatically sets specific environment variables.</span></span> <span data-ttu-id="af1a7-107">Dopo l'apertura di Prompt dei comandi per gli sviluppatori, è possibile immettere i comandi per [.NET Framework strumenti](index.md) , ad esempio `ildasm` o `clrver` .</span><span class="sxs-lookup"><span data-stu-id="af1a7-107">After opening Developer Command Prompt, you can enter the commands for [.NET Framework tools](index.md) such as `ildasm` or `clrver`.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="af1a7-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="af1a7-108">Prerequisites</span></span>

- [<span data-ttu-id="af1a7-109">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="af1a7-109">Visual Studio 2019</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)

## <a name="search-for-the-command-prompt-on-your-machine"></a><span data-ttu-id="af1a7-110">Cercare il prompt dei comandi nel computer</span><span class="sxs-lookup"><span data-stu-id="af1a7-110">Search for the command prompt on your machine</span></span>

<span data-ttu-id="af1a7-111">È possibile che siano presenti più prompt dei comandi, a seconda della versione di Visual Studio e di eventuali SDK e carichi di lavoro aggiuntivi installati.</span><span class="sxs-lookup"><span data-stu-id="af1a7-111">You may have multiple command prompts, depending on the version of Visual Studio and any additional SDKs and workloads you've installed.</span></span> <span data-ttu-id="af1a7-112">Se i passaggi seguenti non funzionano, è possibile provare a [individuare manualmente i file nel computer](#manually-locate-the-files-on-your-machine) o [avviare il prompt dei comandi dall'interno di Visual Studio](#start-the-command-prompt-from-inside-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="af1a7-112">If the following steps don't work, you can try to [manually locate the files on your machine](#manually-locate-the-files-on-your-machine) or [start the command prompt from inside Visual Studio](#start-the-command-prompt-from-inside-visual-studio).</span></span>

### <a name="windows-10"></a><span data-ttu-id="af1a7-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="af1a7-113">Windows 10</span></span>

1. <span data-ttu-id="af1a7-114">Selezionare **Avvia** ![ il tasto logo Windows sulla tastiera.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span><span class="sxs-lookup"><span data-stu-id="af1a7-114">Select **Start** ![Windows logo key on the keyboard.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span></span> <span data-ttu-id="af1a7-115">e scorrere fino alla lettera **V**.</span><span class="sxs-lookup"><span data-stu-id="af1a7-115">and scroll to the letter **V**.</span></span>

1. <span data-ttu-id="af1a7-116">Espandere la cartella **Visual Studio 2019** .</span><span class="sxs-lookup"><span data-stu-id="af1a7-116">Expand the **Visual Studio 2019** folder.</span></span>

1. <span data-ttu-id="af1a7-117">Scegliere **prompt dei comandi per gli sviluppatori per VS 2019** (o il prompt dei comandi che si vuole usare).</span><span class="sxs-lookup"><span data-stu-id="af1a7-117">Choose **Developer Command Prompt for VS 2019** (or the command prompt you want to use).</span></span>

   <span data-ttu-id="af1a7-118">In alternativa, è possibile iniziare a digitare il nome del prompt dei comandi nella casella di ricerca sulla barra delle applicazioni e scegliere il risultato desiderato, perché l'elenco dei risultati inizia a visualizzare le corrispondenze di ricerca.</span><span class="sxs-lookup"><span data-stu-id="af1a7-118">Alternatively, you can start typing the name of the command prompt in the search box on the taskbar, and choose the result you want as the result list starts to display the search matches.</span></span>

   ![Gif animata che mostra il comportamento di ricerca in Windows 10](./media/developer-command-prompt-for-vs/windows10-search.gif)

### <a name="windows-81"></a><span data-ttu-id="af1a7-120">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="af1a7-120">Windows 8.1</span></span>

1. <span data-ttu-id="af1a7-121">Andare alla schermata **Start** ad esempio premendo il tasto WINDOWS![tasto WINDOWS sulla tastiera.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span><span class="sxs-lookup"><span data-stu-id="af1a7-121">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo key on the keyboard.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span></span> <span data-ttu-id="af1a7-122">sulla tastiera.</span><span class="sxs-lookup"><span data-stu-id="af1a7-122">on your keyboard for example.</span></span>

1. <span data-ttu-id="af1a7-123">Nella schermata **Start** premere **CTRL** + **Tab** per aprire l'elenco **app** e quindi premere **V**. Viene visualizzato un elenco che include tutti i prompt dei comandi di Visual Studio installati.</span><span class="sxs-lookup"><span data-stu-id="af1a7-123">On the **Start** screen, press **Ctrl**+**Tab** to open the **Apps** list, and then press **V**. This brings up a list that includes all installed Visual Studio command prompts.</span></span>

1. <span data-ttu-id="af1a7-124">Scegliere **prompt dei comandi per gli sviluppatori per VS 2019** (o il prompt dei comandi che si vuole usare).</span><span class="sxs-lookup"><span data-stu-id="af1a7-124">Choose **Developer Command Prompt for VS 2019** (or the command prompt you want to use).</span></span>

### <a name="windows-7"></a><span data-ttu-id="af1a7-125">Windows 7</span><span class="sxs-lookup"><span data-stu-id="af1a7-125">Windows 7</span></span>

1. <span data-ttu-id="af1a7-126">Scegliere **Start** , quindi espandere **tutti i programmi**.</span><span class="sxs-lookup"><span data-stu-id="af1a7-126">Choose **Start** and then expand **All Programs**.</span></span>

1. <span data-ttu-id="af1a7-127">Scegliere **Visual Studio 2019**  >  **strumenti di Visual Studio**  >  **prompt dei comandi per gli sviluppatori per vs 2019**o il prompt dei comandi che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="af1a7-127">Choose **Visual Studio 2019** > **Visual Studio Tools** > **Developer Command Prompt for VS 2019**, or the command prompt you want to use.</span></span>

   ![Menu Start di Windows 7 con il prompt dei comandi evidenziato](./media/developer-command-prompt-for-vs/windows7-menu.png)

<span data-ttu-id="af1a7-129">Se sono installati altri SDK, ad esempio [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) o [versioni precedenti](https://developer.microsoft.com/windows/downloads/sdk-archive), è possibile visualizzare prompt dei comandi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="af1a7-129">If you have other SDKs installed, such as the [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) or [previous versions](https://developer.microsoft.com/windows/downloads/sdk-archive), you may see additional command prompts.</span></span> <span data-ttu-id="af1a7-130">Consultare la documentazione dei diversi strumenti per determinare quale versione del prompt dei comandi usare.</span><span class="sxs-lookup"><span data-stu-id="af1a7-130">Check the documentation for the individual tools to determine which version of the command prompt you should use.</span></span>

## <a name="manually-locate-the-files-on-your-machine"></a><span data-ttu-id="af1a7-131">Trovare manualmente i file nel computer</span><span class="sxs-lookup"><span data-stu-id="af1a7-131">Manually locate the files on your machine</span></span>

<span data-ttu-id="af1a7-132">In genere, i collegamenti per i prompt dei comandi installati vengono inseriti nella cartella del **menu Start** per Visual Studio, ad esempio in *%ProgramData%\Microsoft\Windows\Start Menu\Programs\Visual Studio 2019 \ strumenti di Visual Studio*.</span><span class="sxs-lookup"><span data-stu-id="af1a7-132">Usually, the shortcuts for the command prompts you have installed are placed at the **Start Menu** folder for Visual Studio, such as in *%ProgramData%\Microsoft\Windows\Start Menu\Programs\Visual Studio 2019\Visual Studio Tools*.</span></span> <span data-ttu-id="af1a7-133">Tuttavia, se per qualche motivo la ricerca del prompt dei comandi non produce i risultati previsti, è possibile provare a individuare manualmente il collegamento nel computer.</span><span class="sxs-lookup"><span data-stu-id="af1a7-133">But if, for some reason, searching for the command prompt doesn't produce the expected results, you can try to manually locate the shortcut on your machine.</span></span> <span data-ttu-id="af1a7-134">Provare a cercare il nome del file del prompt dei comandi, ad esempio *VsDevCmd.bat*, oppure passare alla cartella strumenti, ad esempio *% ProgramFiles (x86)% \ Microsoft Visual Studio\2019\Community\Common7\Tools* (percorso modificato in base alla versione, all'edizione e al percorso di installazione di Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="af1a7-134">Try searching for the name of the command prompt file, such as *VsDevCmd.bat*, or go to the Tools folder, such as *%ProgramFiles(x86)%\Microsoft Visual Studio\2019\Community\Common7\Tools* (path changes according to your Visual Studio version, edition, and installation location).</span></span>

## <a name="start-the-command-prompt-from-inside-visual-studio"></a><span data-ttu-id="af1a7-135">Avviare il prompt dei comandi dall'interno di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="af1a7-135">Start the command prompt from inside Visual Studio</span></span>

<span data-ttu-id="af1a7-136">Per semplificare l'accesso, è possibile aggiungere Prompt dei comandi per gli sviluppatori o qualsiasi altro prompt dei comandi al menu strumenti in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="af1a7-136">For easier access, you can add Developer Command Prompt, or any other command prompt, to the Tools menu in Visual Studio.</span></span> <span data-ttu-id="af1a7-137">Per rendere lo strumento disponibile, aggiungerlo all'elenco degli strumenti esterni.</span><span class="sxs-lookup"><span data-stu-id="af1a7-137">To make the tool available, add it to the external tools list.</span></span> <span data-ttu-id="af1a7-138">Seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="af1a7-138">Here are the steps:</span></span>

1. <span data-ttu-id="af1a7-139">Aprire Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="af1a7-139">Open Visual Studio.</span></span>

1. <span data-ttu-id="af1a7-140">Nella finestra iniziale scegliere **Continua senza codice**.</span><span class="sxs-lookup"><span data-stu-id="af1a7-140">On the start window, choose **Continue without code**.</span></span>

1. <span data-ttu-id="af1a7-141">Sulla barra dei menu scegliere **strumenti**strumenti  >  **esterni**.</span><span class="sxs-lookup"><span data-stu-id="af1a7-141">On the menu bar, choose **Tools** > **External Tools**.</span></span>

1. <span data-ttu-id="af1a7-142">Nella finestra di dialogo **Strumenti esterni** scegliere il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="af1a7-142">On the **External Tools** dialog box, choose the **Add** button.</span></span> <span data-ttu-id="af1a7-143">Verrà visualizzata una nuova voce.</span><span class="sxs-lookup"><span data-stu-id="af1a7-143">A new entry appears.</span></span>

1. <span data-ttu-id="af1a7-144">Immettere un **titolo** per la nuova voce di menu, ad esempio `Command Prompt`.</span><span class="sxs-lookup"><span data-stu-id="af1a7-144">Enter a **Title** for your new menu item such as `Command Prompt`.</span></span>

1. <span data-ttu-id="af1a7-145">Nel campo **comando** specificare il file che si vuole avviare, ad esempio `%comspec%` o `C:\Windows\System32\cmd.exe` .</span><span class="sxs-lookup"><span data-stu-id="af1a7-145">In the **Command** field, specify the file you want to launch, such as `%comspec%` or `C:\Windows\System32\cmd.exe`.</span></span>

1. <span data-ttu-id="af1a7-146">Nel campo **argomenti** specificare dove trovare il prompt dei comandi specifico che si desidera utilizzare, ad esempio `/k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\Tools\VsDevCmd.bat"` .</span><span class="sxs-lookup"><span data-stu-id="af1a7-146">In the **Arguments** field, specify where to find the specific command prompt you want to use, such as `/k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\Tools\VsDevCmd.bat"`.</span></span> <span data-ttu-id="af1a7-147">Questo comando avvia il Prompt dei comandi per gli sviluppatori installato con la community di Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="af1a7-147">This command launches the Developer Command Prompt that's installed with Visual Studio 2019 Community.</span></span> <span data-ttu-id="af1a7-148">Modificare questo valore in base al percorso di installazione, alla versione e all'edizione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="af1a7-148">Change this value according to your Visual Studio version, edition, and installation location.</span></span>

1. <span data-ttu-id="af1a7-149">Nel campo **directory iniziale** specificare la directory in cui verrà avviato il prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="af1a7-149">In the **Initial directory** field, specify the directory in which the command prompt will start.</span></span> <span data-ttu-id="af1a7-150">Scegliere un valore, ad esempio **Directory progetto** , selezionando la freccia accanto al campo.</span><span class="sxs-lookup"><span data-stu-id="af1a7-150">Choose a value such as **Project Directory** by selecting the arrow next to the field.</span></span>

1. <span data-ttu-id="af1a7-151">Fare clic su **OK** .</span><span class="sxs-lookup"><span data-stu-id="af1a7-151">Choose the **OK** button.</span></span>

   ![Finestra di dialogo strumenti esterni con i valori del campo compilati.](./media/developer-command-prompt-for-vs/add-external-tool.png)

   <span data-ttu-id="af1a7-153">Verrà aggiunta la nuova voce di menu e sarà possibile accedere al prompt dei comandi dal menu Strumenti.</span><span class="sxs-lookup"><span data-stu-id="af1a7-153">The new menu item is added, and you can access the command prompt from the Tools menu.</span></span>

   ![Voce di menu del prompt dei comandi in Visual Studio](./media/developer-command-prompt-for-vs/command-prompt-vs-menu.png)

## <a name="see-also"></a><span data-ttu-id="af1a7-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af1a7-155">See also</span></span>

- [<span data-ttu-id="af1a7-156">Strumenti di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="af1a7-156">.NET Framework Tools</span></span>](index.md)
- [<span data-ttu-id="af1a7-157">Gestione di strumenti esterni</span><span class="sxs-lookup"><span data-stu-id="af1a7-157">Managing External Tools</span></span>](/visualstudio/ide/managing-external-tools)
- [<span data-ttu-id="af1a7-158">Usare il set di strumenti di Microsoft C++ dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="af1a7-158">Use the Microsoft C++ toolset from the command line</span></span>](/cpp/build/building-on-the-command-line)
