---
title: Prompt dei comandi per gli sviluppatori per Visual Studio
ms.date: 06/18/2018
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
ms.openlocfilehash: 8e64facffd4face929b28d660ffd5210f127c3bd
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2018
ms.locfileid: "36315225"
---
# <a name="developer-command-prompt-for-visual-studio"></a><span data-ttu-id="e21c8-102">Prompt dei comandi per gli sviluppatori per Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e21c8-102">Developer Command Prompt for Visual Studio</span></span>

<span data-ttu-id="e21c8-103">Il prompt dei comandi per gli sviluppatori per Visual Studio imposta automaticamente le variabili di ambiente che consentono di usare facilmente gli strumenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e21c8-103">The Developer Command Prompt for Visual Studio automatically sets the environment variables that enable you to easily use .NET Framework tools.</span></span> <span data-ttu-id="e21c8-104">Il prompt dei comandi per gli sviluppatori viene installato con le versioni complete o della Community di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e21c8-104">The Developer Command Prompt is installed with full or community editions of Visual Studio.</span></span> <span data-ttu-id="e21c8-105">Non viene installato con le versioni Express di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e21c8-105">It isn't installed with the Express versions of Visual Studio.</span></span>

> [!div class="button"]
[<span data-ttu-id="e21c8-106">Download di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e21c8-106">Download Visual Studio</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

## <a name="searching-for-the-command-prompt-on-your-machine"></a><span data-ttu-id="e21c8-107">Ricerca del prompt dei comandi nel computer</span><span class="sxs-lookup"><span data-stu-id="e21c8-107">Searching for the Command Prompt on your machine</span></span>

<span data-ttu-id="e21c8-108">Si potrebbero notare molti prompt dei comandi, in base alla versione di Visual Studio e agli SDK aggiuntivi installati.</span><span class="sxs-lookup"><span data-stu-id="e21c8-108">You may see many command prompts, depending on the version of Visual Studio and any additional SDKs you've installed.</span></span> <span data-ttu-id="e21c8-109">Ad esempio, le versioni a 64 bit di Visual Studio forniscono prompt dei comandi sia a 32 bit che a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="e21c8-109">For example, 64-bit versions of Visual Studio provide both 32-bit and 64-bit command prompts.</span></span> <span data-ttu-id="e21c8-110">Le versioni a 32 bit e a 64 bit della maggior parte degli strumenti sono uguali; tuttavia, alcuni strumenti apportano modifiche specifiche per gli ambienti a 32 bit e a 64 bit. Se i passaggi seguenti non funzionano, è possibile provare [Individuazione manuale dei file nel computer](#manually-locating-the-files-on-your-machine) o [Esecuzione del prompt dei comandi dall'interno di Visual Studio](#running-command-prompt-from-inside-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="e21c8-110">(The 32-bit and 64-bit versions of most tools are the same; however, a few tools make changes specific to 32-bit and 64-bit environments.) If the following steps don't work, you can try [Manually locating the files on your machine](#manually-locating-the-files-on-your-machine) or [Running command prompt from inside Visual Studio](#running-command-prompt-from-inside-visual-studio).</span></span>

### <a name="in-windows-10"></a><span data-ttu-id="e21c8-111">In Windows 10</span><span class="sxs-lookup"><span data-stu-id="e21c8-111">In Windows 10</span></span>

1. <span data-ttu-id="e21c8-112">Nella casella di ricerca della barra delle applicazioni iniziare a digitare il nome dello strumento, ad esempio `dev` o `developer command prompt`.</span><span class="sxs-lookup"><span data-stu-id="e21c8-112">In the search box on the taskbar, start typing the name of the tool, such as `dev` or `developer command prompt`.</span></span> <span data-ttu-id="e21c8-113">Verrà visualizzato un elenco di app installate che corrispondono ai criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="e21c8-113">This brings a list of installed apps that match your search pattern.</span></span> <span data-ttu-id="e21c8-114">Se si sta cercando un prompt dei comandi diverso, provare a immettere un termine di ricerca diverso, ad esempio `prompt`.</span><span class="sxs-lookup"><span data-stu-id="e21c8-114">If you're looking for a different command prompt, try entering a different search term such as `prompt`.</span></span>

2. <span data-ttu-id="e21c8-115">Scegliere **Prompt dei comandi per gli sviluppatori** (o il prompt dei comandi che si vuole usare).</span><span class="sxs-lookup"><span data-stu-id="e21c8-115">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-81"></a><span data-ttu-id="e21c8-116">In Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="e21c8-116">In Windows 8.1</span></span>

1. <span data-ttu-id="e21c8-117">Aprire la schermata **Start** premendo il tasto del ![logo Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") sulla tastiera.</span><span class="sxs-lookup"><span data-stu-id="e21c8-117">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>

2. <span data-ttu-id="e21c8-118">Nella schermata **Start** premere `CTRL + TAB` per aprire l'elenco **App** e quindi immettere `V`.</span><span class="sxs-lookup"><span data-stu-id="e21c8-118">On the **Start** screen, press `CTRL + TAB` to open the **Apps** list and then enter `V`.</span></span> <span data-ttu-id="e21c8-119">Verrà visualizzato un elenco che include tutti i prompt dei comandi di Visual Studio installati.</span><span class="sxs-lookup"><span data-stu-id="e21c8-119">This brings a list that includes all installed Visual Studio command prompts.</span></span>

3. <span data-ttu-id="e21c8-120">Scegliere **Prompt dei comandi per gli sviluppatori** (o il prompt dei comandi che si vuole usare).</span><span class="sxs-lookup"><span data-stu-id="e21c8-120">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-8"></a><span data-ttu-id="e21c8-121">In Windows 8</span><span class="sxs-lookup"><span data-stu-id="e21c8-121">In Windows 8</span></span>

1. <span data-ttu-id="e21c8-122">Aprire la schermata **Start** premendo il tasto del ![logo Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") sulla tastiera.</span><span class="sxs-lookup"><span data-stu-id="e21c8-122">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>

2. <span data-ttu-id="e21c8-123">Nella schermata **Start** premere il tasto del ![logo Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span><span class="sxs-lookup"><span data-stu-id="e21c8-123">On the **Start** screen, press the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span></span>

3. <span data-ttu-id="e21c8-124">Scegliere l'icona **Visualizzazione App** nella parte inferiore della schermata e quindi immettere `V`.</span><span class="sxs-lookup"><span data-stu-id="e21c8-124">Choose the **Apps view** icon at the bottom of the screen and then enter `V`.</span></span> <span data-ttu-id="e21c8-125">Verrà visualizzato un elenco che include tutti i prompt dei comandi di Visual Studio installati.</span><span class="sxs-lookup"><span data-stu-id="e21c8-125">This brings a list that includes all installed Visual Studio command prompts.</span></span>

4. <span data-ttu-id="e21c8-126">Scegliere **Prompt dei comandi per gli sviluppatori** (o il prompt dei comandi che si vuole usare).</span><span class="sxs-lookup"><span data-stu-id="e21c8-126">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-7"></a><span data-ttu-id="e21c8-127">In Windows 7</span><span class="sxs-lookup"><span data-stu-id="e21c8-127">In Windows 7</span></span>

1. <span data-ttu-id="e21c8-128">Scegliere **Start**, espandere **Tutti i programmi** e quindi espandere **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="e21c8-128">Choose **Start**, expand **All Programs**, and then expand **Microsoft Visual Studio**.</span></span>

2. <span data-ttu-id="e21c8-129">A seconda della versione di Visual Studio installata, scegliere **Strumenti di Visual Studio**, **Prompt dei comandi di Visual Studio** o il prompt dei comandi che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="e21c8-129">Depending on the version of Visual Studio you've installed, choose  **Visual Studio Tools**, **Visual Studio Command Prompt**, or the command prompt you want to use.</span></span>

<span data-ttu-id="e21c8-130">Se ci sono altri SDK installati, ad esempio [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) o [versioni precedenti](https://developer.microsoft.com/windows/downloads/sdk-archive), si potranno notare prompt dei comandi aggiuntivi per le architetture ARM, x86 o x64.</span><span class="sxs-lookup"><span data-stu-id="e21c8-130">If you have other SDKs installed such as the [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) or [previous versions](https://developer.microsoft.com/windows/downloads/sdk-archive) installed, you may see additional command prompts for ARM, x86, or x64 architectures.</span></span> <span data-ttu-id="e21c8-131">Consultare la documentazione dei diversi strumenti per determinare quale versione del prompt dei comandi usare.</span><span class="sxs-lookup"><span data-stu-id="e21c8-131">Check the documentation for the individual tools to determine which version of the command prompt you should use.</span></span>

## <a name="manually-locating-the-files-on-your-machine"></a><span data-ttu-id="e21c8-132">Individuazione manuale dei file nel computer</span><span class="sxs-lookup"><span data-stu-id="e21c8-132">Manually locating the files on your machine</span></span>

<span data-ttu-id="e21c8-133">In genere, i collegamenti per i prompt dei comandi installati verranno posizionati nella cartella **Menu Start** per Visual Studio, ad esempio in C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools.</span><span class="sxs-lookup"><span data-stu-id="e21c8-133">Usually, the shortcuts for the command prompts you have installed are placed at the **Start Menu** folder for Visual Studio, such as in C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools.</span></span> <span data-ttu-id="e21c8-134">Tuttavia, se per qualche motivo la ricerca del prompt dei comandi non produce i risultati previsti, è possibile provare a trovare manualmente il collegamento nel computer.</span><span class="sxs-lookup"><span data-stu-id="e21c8-134">But if for some reason, searching for the command prompt doesn't bring the expected results, you can try to manually locate the shortcut on your machine.</span></span> <span data-ttu-id="e21c8-135">Provare a cercare il nome del file del prompt dei comandi, ad esempio *VsDevCmd.bat* o passare alla cartella Tools, ad esempio C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools (il percorso cambierà a seconda del percorso di installazione, della versione e dell'edizione di Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="e21c8-135">Try searching for the name of the command prompt file, such as *VsDevCmd.bat*, or go to the Tools folder such as C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools (path changes according to your Visual Studio version, edition, and installation location).</span></span>

## <a name="running-command-prompt-from-inside-visual-studio"></a><span data-ttu-id="e21c8-136">Esecuzione del prompt dei comandi dall'interno di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e21c8-136">Running command prompt from inside Visual Studio</span></span>

<span data-ttu-id="e21c8-137">Per semplificare l'accesso, è possibile aggiungere il prompt dei comandi per gli sviluppatori Visual Studio o qualsiasi altro prompt dei comandi al menu Strumenti in Visual Studio aggiungendolo all'elenco di strumenti esterni.</span><span class="sxs-lookup"><span data-stu-id="e21c8-137">For easier access, you can add the Visual Studio Developer Command Prompt  or any other command prompt to the Tools menu on Visual Studio, by adding it to the external tools list.</span></span> <span data-ttu-id="e21c8-138">Di seguito è illustrata la procedura per eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="e21c8-138">This is how you can accomplish that:</span></span>

1. <span data-ttu-id="e21c8-139">Aprire Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e21c8-139">Open Visual Studio.</span></span>

2. <span data-ttu-id="e21c8-140">Selezionare il menu **Strumenti** e scegliere **Strumenti esterni**.</span><span class="sxs-lookup"><span data-stu-id="e21c8-140">Select the **Tools** menu and choose **External Tools**.</span></span>

3. <span data-ttu-id="e21c8-141">Nella finestra di dialogo **Strumenti esterni** scegliere il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e21c8-141">On the **External Tools** dialog box, choose the **Add** button.</span></span> <span data-ttu-id="e21c8-142">Verrà visualizzata una nuova voce.</span><span class="sxs-lookup"><span data-stu-id="e21c8-142">A new entry appears.</span></span>

4. <span data-ttu-id="e21c8-143">Immettere un **titolo** per la nuova voce di menu, ad esempio `Command Prompt`.</span><span class="sxs-lookup"><span data-stu-id="e21c8-143">Enter a **Title** for your new menu item such as `Command Prompt`.</span></span>

5. <span data-ttu-id="e21c8-144">Nel campo **Comando** specificare il file che si vuole avviare, ad esempio `%comspec%` o `C:\Windows\System32\cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="e21c8-144">In the **Command** field, specify the file you want to launch such as `%comspec%` or `C:\Windows\System32\cmd.exe`.</span></span>

6. <span data-ttu-id="e21c8-145">Nel campo **Argomenti** specificare dove trovare il prompt dei comandi specifico da usare, ad esempio `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (verrà avviato il Prompt dei comandi per gli sviluppatori installato con Visual Studio 2017 Enterprise).</span><span class="sxs-lookup"><span data-stu-id="e21c8-145">In the **Arguments** field, specify where to find the specific command prompt you want to use such as `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (this command launches the Developer Command Prompt that is installed with Visual Studio 2017 Enterprise).</span></span> <span data-ttu-id="e21c8-146">Modificare questo valore in base al percorso di installazione, alla versione e all'edizione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e21c8-146">Change this value according to your Visual Studio version, edition, and installation location.</span></span>

7. <span data-ttu-id="e21c8-147">Scegliere un valore per il campo **Directory iniziale**, ad esempio **Directory di progetto**.</span><span class="sxs-lookup"><span data-stu-id="e21c8-147">Choose a value for the **Initial directory** field such as **Project Directory**.</span></span>

8. <span data-ttu-id="e21c8-148">Fare clic sul pulsante **OK** .</span><span class="sxs-lookup"><span data-stu-id="e21c8-148">Choose the **OK** button.</span></span>

<span data-ttu-id="e21c8-149">Successivamente, viene aggiunta la nuova voce di menu ed è possibile accedere al prompt dei comandi dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="e21c8-149">After that, the new menu item is added and you can access the command prompt from the **Tools** menu.</span></span>

## <a name="see-also"></a><span data-ttu-id="e21c8-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e21c8-150">See also</span></span>

 [<span data-ttu-id="e21c8-151">Strumenti</span><span class="sxs-lookup"><span data-stu-id="e21c8-151">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="e21c8-152">Gestione di strumenti esterni</span><span class="sxs-lookup"><span data-stu-id="e21c8-152">Managing External Tools</span></span>](/visualstudio/ide/managing-external-tools)  
