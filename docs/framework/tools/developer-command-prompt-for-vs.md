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
ms.openlocfilehash: 4c95074190419dd3e984c7659ede917b83b97f08
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43524716"
---
# <a name="developer-command-prompt-for-visual-studio"></a><span data-ttu-id="7597d-102">Prompt dei comandi per gli sviluppatori per Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7597d-102">Developer Command Prompt for Visual Studio</span></span>

<span data-ttu-id="7597d-103">Il prompt dei comandi per gli sviluppatori per Visual Studio imposta automaticamente le variabili di ambiente che consentono di usare facilmente gli strumenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7597d-103">The Developer Command Prompt for Visual Studio automatically sets the environment variables that enable you to easily use .NET Framework tools.</span></span>

> [!div class="button"]
[<span data-ttu-id="7597d-104">Download di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7597d-104">Download Visual Studio</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

## <a name="searching-for-the-command-prompt-on-your-machine"></a><span data-ttu-id="7597d-105">Ricerca del prompt dei comandi nel computer</span><span class="sxs-lookup"><span data-stu-id="7597d-105">Searching for the command prompt on your machine</span></span>

<span data-ttu-id="7597d-106">Si potrebbero avere più prompt dei comandi, in base alla versione di Visual Studio e agli SDK aggiuntivi installati.</span><span class="sxs-lookup"><span data-stu-id="7597d-106">You may have multiple command prompts, depending on the version of Visual Studio and any additional SDKs you've installed.</span></span> <span data-ttu-id="7597d-107">Ad esempio, le versioni a 64 bit di Visual Studio forniscono prompt dei comandi sia a 32 bit che a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="7597d-107">For example, 64-bit versions of Visual Studio provide both 32-bit and 64-bit command prompts.</span></span> <span data-ttu-id="7597d-108">Le versioni a 32 bit e a 64 bit della maggior parte degli strumenti sono uguali; tuttavia, alcuni strumenti apportano modifiche specifiche per gli ambienti a 32 bit e a 64 bit. Se i passaggi seguenti non funzionano, è possibile provare [Individuazione manuale dei file nel computer](#manually-locating-the-files-on-your-machine) o [Esecuzione del prompt dei comandi dall'interno di Visual Studio](#running-command-prompt-from-inside-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="7597d-108">(The 32-bit and 64-bit versions of most tools are the same; however, a few tools make changes specific to 32-bit and 64-bit environments.) If the following steps don't work, you can try [Manually locating the files on your machine](#manually-locating-the-files-on-your-machine) or [Running the command prompt from inside Visual Studio](#running-command-prompt-from-inside-visual-studio).</span></span>

### <a name="in-windows-10"></a><span data-ttu-id="7597d-109">In Windows 10</span><span class="sxs-lookup"><span data-stu-id="7597d-109">In Windows 10</span></span>

1. <span data-ttu-id="7597d-110">Nella casella di ricerca della barra delle applicazioni iniziare a digitare il nome dello strumento, ad esempio `dev` o `developer command prompt`.</span><span class="sxs-lookup"><span data-stu-id="7597d-110">In the search box on the taskbar, start typing the name of the tool, such as `dev` or `developer command prompt`.</span></span> <span data-ttu-id="7597d-111">Verrà visualizzato un elenco di app installate che corrispondono ai criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="7597d-111">This brings up a list of installed apps that match your search pattern.</span></span> <span data-ttu-id="7597d-112">Se si sta cercando un prompt dei comandi diverso, provare a immettere un termine di ricerca diverso, ad esempio `prompt`.</span><span class="sxs-lookup"><span data-stu-id="7597d-112">If you're looking for a different command prompt, try entering a different search term such as `prompt`.</span></span>

2. <span data-ttu-id="7597d-113">Scegliere **Prompt dei comandi per gli sviluppatori** (o il prompt dei comandi che si vuole usare).</span><span class="sxs-lookup"><span data-stu-id="7597d-113">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-81"></a><span data-ttu-id="7597d-114">In Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="7597d-114">In Windows 8.1</span></span>

1. <span data-ttu-id="7597d-115">Aprire la schermata **Start** premendo il tasto del ![logo Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") sulla tastiera.</span><span class="sxs-lookup"><span data-stu-id="7597d-115">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>

2. <span data-ttu-id="7597d-116">Nella schermata **Start** premere `CTRL + TAB` per aprire l'elenco **App** e quindi immettere `V`.</span><span class="sxs-lookup"><span data-stu-id="7597d-116">On the **Start** screen, press `CTRL + TAB` to open the **Apps** list and then enter `V`.</span></span> <span data-ttu-id="7597d-117">Verrà visualizzato un elenco che include tutti i prompt dei comandi di Visual Studio installati.</span><span class="sxs-lookup"><span data-stu-id="7597d-117">This brings a list that includes all installed Visual Studio command prompts.</span></span>

3. <span data-ttu-id="7597d-118">Scegliere **Prompt dei comandi per gli sviluppatori** (o il prompt dei comandi che si vuole usare).</span><span class="sxs-lookup"><span data-stu-id="7597d-118">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-8"></a><span data-ttu-id="7597d-119">In Windows 8</span><span class="sxs-lookup"><span data-stu-id="7597d-119">In Windows 8</span></span>

1. <span data-ttu-id="7597d-120">Aprire la schermata **Start** premendo il tasto del ![logo Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") sulla tastiera.</span><span class="sxs-lookup"><span data-stu-id="7597d-120">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>

2. <span data-ttu-id="7597d-121">Nella schermata **Start** premere il tasto del ![logo Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span><span class="sxs-lookup"><span data-stu-id="7597d-121">On the **Start** screen, press the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span></span>

3. <span data-ttu-id="7597d-122">Scegliere l'icona **Visualizzazione App** nella parte inferiore della schermata e quindi immettere `V`.</span><span class="sxs-lookup"><span data-stu-id="7597d-122">Choose the **Apps view** icon at the bottom of the screen and then enter `V`.</span></span> <span data-ttu-id="7597d-123">Verrà visualizzato un elenco che include tutti i prompt dei comandi di Visual Studio installati.</span><span class="sxs-lookup"><span data-stu-id="7597d-123">This brings a list that includes all installed Visual Studio command prompts.</span></span>

4. <span data-ttu-id="7597d-124">Scegliere **Prompt dei comandi per gli sviluppatori** (o il prompt dei comandi che si vuole usare).</span><span class="sxs-lookup"><span data-stu-id="7597d-124">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-7"></a><span data-ttu-id="7597d-125">In Windows 7</span><span class="sxs-lookup"><span data-stu-id="7597d-125">In Windows 7</span></span>

1. <span data-ttu-id="7597d-126">Scegliere **Start**, espandere **Tutti i programmi** e quindi espandere **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="7597d-126">Choose **Start**, expand **All Programs**, and then expand **Microsoft Visual Studio**.</span></span>

2. <span data-ttu-id="7597d-127">A seconda della versione di Visual Studio installata, scegliere **Strumenti di Visual Studio**, **Prompt dei comandi di Visual Studio** o il prompt dei comandi che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="7597d-127">Depending on the version of Visual Studio you've installed, choose  **Visual Studio Tools**, **Visual Studio Command Prompt**, or the command prompt you want to use.</span></span>

<span data-ttu-id="7597d-128">Se ci sono altri SDK installati, ad esempio [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) o [versioni precedenti](https://developer.microsoft.com/windows/downloads/sdk-archive), si potranno notare prompt dei comandi aggiuntivi per le architetture ARM, x86 o x64.</span><span class="sxs-lookup"><span data-stu-id="7597d-128">If you have other SDKs installed, such as the [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) or [previous versions](https://developer.microsoft.com/windows/downloads/sdk-archive), you may see additional command prompts for ARM, x86, or x64 architectures.</span></span> <span data-ttu-id="7597d-129">Consultare la documentazione dei diversi strumenti per determinare quale versione del prompt dei comandi usare.</span><span class="sxs-lookup"><span data-stu-id="7597d-129">Check the documentation for the individual tools to determine which version of the command prompt you should use.</span></span>

## <a name="manually-locate-the-files-on-your-machine"></a><span data-ttu-id="7597d-130">Trovare manualmente i file nel computer</span><span class="sxs-lookup"><span data-stu-id="7597d-130">Manually locate the files on your machine</span></span>

<span data-ttu-id="7597d-131">In genere, i collegamenti per i prompt dei comandi installati verranno posizionati nella cartella **Menu Start** per Visual Studio, ad esempio in C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools.</span><span class="sxs-lookup"><span data-stu-id="7597d-131">Usually, the shortcuts for the command prompts you have installed are placed at the **Start Menu** folder for Visual Studio, such as in C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools.</span></span> <span data-ttu-id="7597d-132">Tuttavia, se per qualche motivo la ricerca del prompt dei comandi non produce i risultati previsti, è possibile provare a trovare manualmente il collegamento nel computer.</span><span class="sxs-lookup"><span data-stu-id="7597d-132">But if for some reason, searching for the command prompt doesn't bring the expected results, you can try to manually locate the shortcut on your machine.</span></span> <span data-ttu-id="7597d-133">Provare a cercare il nome del file del prompt dei comandi, ad esempio *VsDevCmd.bat* o passare alla cartella Tools, ad esempio C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools (il percorso cambierà a seconda del percorso di installazione, della versione e dell'edizione di Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="7597d-133">Try searching for the name of the command prompt file, such as *VsDevCmd.bat*, or go to the Tools folder such as C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools (path changes according to your Visual Studio version, edition, and installation location).</span></span>

## <a name="run-command-prompt-from-inside-visual-studio"></a><span data-ttu-id="7597d-134">Eseguire il prompt dei comandi dall'interno di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7597d-134">Run command prompt from inside Visual Studio</span></span>

<span data-ttu-id="7597d-135">Per semplificare l'accesso, è possibile aggiungere il prompt dei comandi per gli sviluppatori Visual Studio o qualsiasi altro prompt dei comandi al menu **Strumenti** in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7597d-135">For easier access, you can add the Visual Studio Developer Command Prompt, or any other command prompt, to the **Tools** menu in Visual Studio.</span></span> <span data-ttu-id="7597d-136">Per rendere lo strumento disponibile, aggiungerlo all'elenco degli strumenti esterni.</span><span class="sxs-lookup"><span data-stu-id="7597d-136">To make the tool available, add it to the external tools list.</span></span> <span data-ttu-id="7597d-137">Di seguito la procedura:</span><span class="sxs-lookup"><span data-stu-id="7597d-137">Here are the steps:</span></span>

1. <span data-ttu-id="7597d-138">Aprire Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7597d-138">Open Visual Studio.</span></span>

2. <span data-ttu-id="7597d-139">Selezionare il menu **Strumenti** e quindi scegliere **Strumenti esterni**.</span><span class="sxs-lookup"><span data-stu-id="7597d-139">Select the **Tools** menu, and then choose **External Tools**.</span></span>

3. <span data-ttu-id="7597d-140">Nella finestra di dialogo **Strumenti esterni** scegliere il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="7597d-140">On the **External Tools** dialog box, choose the **Add** button.</span></span> <span data-ttu-id="7597d-141">Verrà visualizzata una nuova voce.</span><span class="sxs-lookup"><span data-stu-id="7597d-141">A new entry appears.</span></span>

4. <span data-ttu-id="7597d-142">Immettere un **titolo** per la nuova voce di menu, ad esempio `Command Prompt`.</span><span class="sxs-lookup"><span data-stu-id="7597d-142">Enter a **Title** for your new menu item such as `Command Prompt`.</span></span>

5. <span data-ttu-id="7597d-143">Nel campo **Comando** specificare il file che si vuole avviare, ad esempio `%comspec%` o `C:\Windows\System32\cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="7597d-143">In the **Command** field, specify the file you want to launch, such as `%comspec%` or `C:\Windows\System32\cmd.exe`.</span></span>

6. <span data-ttu-id="7597d-144">Nel campo **Argomenti** specificare dove trovare il prompt dei comandi specifico da usare, ad esempio `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (verrà avviato il Prompt dei comandi per gli sviluppatori installato con Visual Studio 2017 Enterprise).</span><span class="sxs-lookup"><span data-stu-id="7597d-144">In the **Arguments** field, specify where to find the specific command prompt you want to use such as `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (this command launches the Developer Command Prompt that is installed with Visual Studio 2017 Enterprise).</span></span> <span data-ttu-id="7597d-145">Modificare questo valore in base al percorso di installazione, alla versione e all'edizione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7597d-145">Change this value according to your Visual Studio version, edition, and installation location.</span></span>

7. <span data-ttu-id="7597d-146">Scegliere un valore per il campo **Directory iniziale**, ad esempio **Directory di progetto**.</span><span class="sxs-lookup"><span data-stu-id="7597d-146">Choose a value for the **Initial directory** field, such as **Project Directory**.</span></span>

8. <span data-ttu-id="7597d-147">Fare clic sul pulsante **OK** .</span><span class="sxs-lookup"><span data-stu-id="7597d-147">Choose the **OK** button.</span></span>

   <span data-ttu-id="7597d-148">Verrà aggiunta la nuova voce di menu e sarà possibile accedere al prompt dei comandi dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="7597d-148">The new menu item is added, and you can access the command prompt from the **Tools** menu.</span></span>

## <a name="see-also"></a><span data-ttu-id="7597d-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7597d-149">See also</span></span>

- [<span data-ttu-id="7597d-150">Strumenti</span><span class="sxs-lookup"><span data-stu-id="7597d-150">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="7597d-151">Gestione di strumenti esterni</span><span class="sxs-lookup"><span data-stu-id="7597d-151">Managing External Tools</span></span>](/visualstudio/ide/managing-external-tools)
