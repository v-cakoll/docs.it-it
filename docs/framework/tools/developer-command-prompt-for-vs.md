---
title: Prompt dei comandi per gli sviluppatori per Visual Studio
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- command prompt, Windows SDK
- Visual Studio command prompt
- command prompt, Visual Studio
- SDK command prompt
- tools [.NET Framework], setting environment variables
- environment variables, setting for tools
- developer command prompt
ms.assetid: 94fcf524-9045-4993-bfb2-e2d8bad44219
caps.latest.revision: 45
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0287c3f250a57f7a685191702be3ad5cc28fbec6
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="developer-command-prompt-for-visual-studio"></a><span data-ttu-id="67f6a-102">Prompt dei comandi per gli sviluppatori per Visual Studio</span><span class="sxs-lookup"><span data-stu-id="67f6a-102">Developer Command Prompt for Visual Studio</span></span>
<span data-ttu-id="67f6a-103">Il prompt dei comandi per gli sviluppatori per Visual Studio imposta automaticamente le variabili di ambiente che consentono di usare facilmente gli strumenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="67f6a-103">The Developer Command Prompt for Visual Studio automatically sets the environment variables that enable you to easily use .NET Framework tools.</span></span> <span data-ttu-id="67f6a-104">Il prompt dei comandi per gli sviluppatori viene installato con le versioni complete o della Community di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="67f6a-104">The Developer Command Prompt is installed with full or community editions of Visual Studio.</span></span> <span data-ttu-id="67f6a-105">Non viene installato con le versioni Express di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="67f6a-105">It is not installed with the Express versions of Visual Studio.</span></span>  
  
<a name="find"></a>   
## <a name="searching-for-the-command-prompt-on-your-machine"></a><span data-ttu-id="67f6a-106">Ricerca del prompt dei comandi nel computer</span><span class="sxs-lookup"><span data-stu-id="67f6a-106">Searching for the Command Prompt on your machine</span></span>  
 <span data-ttu-id="67f6a-107">Si potrebbero notare più prompt dei comandi, in base alla versione di Visual Studio e agli SDK aggiuntivi installati.</span><span class="sxs-lookup"><span data-stu-id="67f6a-107">You may see multiple command prompts, depending on the version of Visual Studio and any additional SDKs you've installed.</span></span> <span data-ttu-id="67f6a-108">Ad esempio, le versioni a 64 bit di Visual Studio forniscono prompt dei comandi sia a 32 bit che a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="67f6a-108">For example, 64-bit versions of Visual Studio provide both 32-bit and 64-bit command prompts.</span></span> <span data-ttu-id="67f6a-109">Le versioni a 32 bit e a 64 bit della maggior parte degli strumenti sono identiche; tuttavia, alcuni strumenti apportano modifiche specifiche per gli ambienti a 32 bit e a 64 bit. Se i passaggi seguenti non funzionano, è possibile provare [Individuazione manuale dei file nel computer](#alternative) o [Esecuzione del prompt dei comandi dall'interno di Visual Studio](#visualstudio).</span><span class="sxs-lookup"><span data-stu-id="67f6a-109">(The 32-bit and 64-bit versions of most tools are identical; however, a few tools make changes specific to 32-bit and 64-bit environments.) If the steps below don't work, you can try [Manually locating the files on your machine](#alternative) or [Running command prompt from inside Visual Studio](#visualstudio).</span></span>  
  
 <span data-ttu-id="67f6a-110">**In Windows 10**</span><span class="sxs-lookup"><span data-stu-id="67f6a-110">**In Windows 10**</span></span>  
  
1.  <span data-ttu-id="67f6a-111">Aprire il menu **Start** premendo il tasto del ![logo Windows](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") sulla tastiera.</span><span class="sxs-lookup"><span data-stu-id="67f6a-111">Open the **Start** menu, by pressing the Windows logo key ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>  
  
2.  <span data-ttu-id="67f6a-112">Nel menu **Start** immettere `dev`.</span><span class="sxs-lookup"><span data-stu-id="67f6a-112">On the **Start** menu, enter `dev`.</span></span> <span data-ttu-id="67f6a-113">Verrà visualizzato un elenco di app installate che corrispondono ai criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="67f6a-113">This will bring a list of installed apps that match your search pattern.</span></span> <span data-ttu-id="67f6a-114">Se si sta cercando un prompt dei comandi diverso, provare a immettere un termine di ricerca diverso, ad esempio `prompt`.</span><span class="sxs-lookup"><span data-stu-id="67f6a-114">If you're looking for a different command prompt, try entering a different search term such as `prompt`.</span></span>  
  
3.  <span data-ttu-id="67f6a-115">Scegliere **Prompt dei comandi per gli sviluppatori** (o il prompt dei comandi che si vuole usare).</span><span class="sxs-lookup"><span data-stu-id="67f6a-115">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>  
  
 <span data-ttu-id="67f6a-116">**In Windows 8.1**</span><span class="sxs-lookup"><span data-stu-id="67f6a-116">**In Windows 8.1**</span></span>  
  
1.  <span data-ttu-id="67f6a-117">Aprire la schermata **Start** premendo il tasto del ![logo Windows](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") sulla tastiera.</span><span class="sxs-lookup"><span data-stu-id="67f6a-117">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>  
  
2.  <span data-ttu-id="67f6a-118">Nella schermata **Start** premere `CTRL + TAB` per aprire l'elenco **App** e quindi immettere `V`.</span><span class="sxs-lookup"><span data-stu-id="67f6a-118">On the **Start** screen, press `CTRL + TAB` to open the **Apps** list and then enter `V`.</span></span> <span data-ttu-id="67f6a-119">Verrà visualizzato un elenco che include tutti i prompt dei comandi di Visual Studio installati.</span><span class="sxs-lookup"><span data-stu-id="67f6a-119">This will bring a list that includes all installed Visual Studio command prompts.</span></span>  
  
3.  <span data-ttu-id="67f6a-120">Scegliere **Prompt dei comandi per gli sviluppatori** (o il prompt dei comandi che si vuole usare).</span><span class="sxs-lookup"><span data-stu-id="67f6a-120">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>  
  
 <span data-ttu-id="67f6a-121">**In Windows 8**</span><span class="sxs-lookup"><span data-stu-id="67f6a-121">**In Windows 8**</span></span>  
  
1.  <span data-ttu-id="67f6a-122">Aprire la schermata **Start** premendo il tasto del ![logo Windows](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") sulla tastiera.</span><span class="sxs-lookup"><span data-stu-id="67f6a-122">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>  
  
2.  <span data-ttu-id="67f6a-123">Nella schermata **Start** premere il tasto del ![logo Windows](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span><span class="sxs-lookup"><span data-stu-id="67f6a-123">On the **Start** screen, press the Windows logo key ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span></span>  
  
3.  <span data-ttu-id="67f6a-124">Scegliere l'icona **Visualizzazione App** nella parte inferiore della schermata e quindi immettere `V`.</span><span class="sxs-lookup"><span data-stu-id="67f6a-124">Choose the **Apps view** icon at the bottom of the screen and then enter `V`.</span></span> <span data-ttu-id="67f6a-125">Verrà visualizzato un elenco che include tutti i prompt dei comandi di Visual Studio installati.</span><span class="sxs-lookup"><span data-stu-id="67f6a-125">This will bring a list that includes all installed Visual Studio command prompts.</span></span>  
  
4.  <span data-ttu-id="67f6a-126">Scegliere **Prompt dei comandi per gli sviluppatori** (o il prompt dei comandi che si vuole usare).</span><span class="sxs-lookup"><span data-stu-id="67f6a-126">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>  
  
 <span data-ttu-id="67f6a-127">**In Windows 7**</span><span class="sxs-lookup"><span data-stu-id="67f6a-127">**In Windows 7**</span></span>  
  
1.  <span data-ttu-id="67f6a-128">Scegliere **Start**, espandere **Tutti i programmi** e quindi espandere **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="67f6a-128">Choose **Start**, expand **All Programs**, and then expand **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="67f6a-129">A seconda della versione di Visual Studio installata, scegliere **Strumenti di Visual Studio**, **Prompt dei comandi di Visual Studio** o il prompt dei comandi che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="67f6a-129">Depending on the version of Visual Studio you have installed, choose  **Visual Studio Tools**, **Visual Studio Command Prompt**, or the command prompt you want to use.</span></span>  
  
 <span data-ttu-id="67f6a-130">Se è installato [Windows SDK](http://msdn.microsoft.com/windows/desktop/aa904949) o [Windows Phone SDK](https://dev.windowsphone.com/downloadsdk), è possibile visualizzare prompt dei comandi aggiuntivi per le architetture ARM, x86 o x64.</span><span class="sxs-lookup"><span data-stu-id="67f6a-130">If you have the [Windows SDK](http://msdn.microsoft.com/windows/desktop/aa904949) or [Windows Phone SDK](https://dev.windowsphone.com/downloadsdk) installed, you may see additional command prompts for ARM, x86, or x64 architectures.</span></span> <span data-ttu-id="67f6a-131">Consultare la documentazione dei diversi strumenti per determinare quale versione del prompt dei comandi usare.</span><span class="sxs-lookup"><span data-stu-id="67f6a-131">Check the documentation for the individual tools to determine which version of the command prompt you should use.</span></span>  
  
<a name="alternative"></a>   
## <a name="manually-locating-the-files-on-your-machine"></a><span data-ttu-id="67f6a-132">Individuazione manuale dei file nel computer</span><span class="sxs-lookup"><span data-stu-id="67f6a-132">Manually locating the files on your machine</span></span>  
  <span data-ttu-id="67f6a-133">In genere, i collegamenti per i prompt dei comandi installati verranno posizionati nella cartella **Menu Start** per Visual Studio, ad esempio in C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2015\Visual Studio Tools.</span><span class="sxs-lookup"><span data-stu-id="67f6a-133">Usually, the shortcuts for the command prompts you have installed will be placed at the **Start Menu** folder for Visual Studio, such as in C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2015\Visual Studio Tools.</span></span>    <span data-ttu-id="67f6a-134">Tuttavia, se per qualche motivo la ricerca del prompt dei comandi non produce i risultati previsti, è possibile provare a trovare manualmente il collegamento nel computer.</span><span class="sxs-lookup"><span data-stu-id="67f6a-134">But if for some reason, searching for the command prompt doesn't yield the expected results, you can try to manually locate the shortcut on your machine in order to use it.</span></span>   <span data-ttu-id="67f6a-135">Provare a cercare il nome del file del prompt dei comandi, ad esempio VsDevCmd.bat o passare alla cartella strumenti, ad esempio C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools (il percorso cambierà a seconda del percorso di installazione e della versione di Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="67f6a-135">Try searching for the name of the command prompt file such as VsDevCmd.bat or go to the Tools folder such as C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools (path will change according to your Visual Studio version and installation location).</span></span>  
  
<a name="visualstudio"></a>   
## <a name="running-command-prompt-from-inside-visual-studio"></a><span data-ttu-id="67f6a-136">Esecuzione del prompt dei comandi dall'interno di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="67f6a-136">Running command prompt from inside Visual Studio</span></span>  
 <span data-ttu-id="67f6a-137">Per semplificare l'accesso, è possibile aggiungere il prompt dei comandi per gli sviluppatori Visual Studio o qualsiasi altro prompt dei comandi al menu Strumenti in Visual Studio aggiungendolo all'elenco di strumenti esterni.</span><span class="sxs-lookup"><span data-stu-id="67f6a-137">For easier access, you can add the Visual Studio Developer Command Prompt  or any other command prompt to the Tools menu on Visual Studio, by adding it to the external tools list.</span></span> <span data-ttu-id="67f6a-138">Di seguito è illustrata la procedura per eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="67f6a-138">This is how you can accomplish that:</span></span>  
  
1.  <span data-ttu-id="67f6a-139">Aprire Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="67f6a-139">Open Visual Studio.</span></span>  
  
2.  <span data-ttu-id="67f6a-140">Selezionare il menu **Strumenti** e scegliere **Strumenti esterni...**.</span><span class="sxs-lookup"><span data-stu-id="67f6a-140">Select the **Tools** menu and choose **External Tools...**.</span></span>  
  
3.  <span data-ttu-id="67f6a-141">Nella finestra di dialogo **Strumenti esterni** scegliere il pulsante **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="67f6a-141">On the **External Tools** dialog box, choose the **Add** button.</span></span> <span data-ttu-id="67f6a-142">Verrà visualizzata una nuova voce.</span><span class="sxs-lookup"><span data-stu-id="67f6a-142">A new entry appears</span></span>  
  
4.  <span data-ttu-id="67f6a-143">Immettere un **titolo** per la nuova voce di menu, ad esempio `Command Prompt`.</span><span class="sxs-lookup"><span data-stu-id="67f6a-143">Enter a **Title** for your new menu item such as `Command Prompt`.</span></span>  
  
5.  <span data-ttu-id="67f6a-144">Nel campo **Comando** specificare il file che si vuole avviare, ad esempio `%comspec%` o `C:\Windows\System32\cmd.exe` .</span><span class="sxs-lookup"><span data-stu-id="67f6a-144">In the **Command** field, specify the file you want to launch such as `%comspec%` or `C:\Windows\System32\cmd.exe` .</span></span>  
  
6.  <span data-ttu-id="67f6a-145">Nel campo **Argomenti** specificare dove trovare il prompt dei comandi specifico da usare, ad esempio `/k "C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools\VsDevCmd.bat"` (verrà avviato il prompt dei comandi per sviluppatori installato con [!INCLUDE[vs_dev14](../../../includes/vs-dev14-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="67f6a-145">In the **Arguments** field, specify where to find the specific command prompt you want to use such as `/k "C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools\VsDevCmd.bat"` (this will launch the Developer Command Prompt installed with [!INCLUDE[vs_dev14](../../../includes/vs-dev14-md.md)]).</span></span> <span data-ttu-id="67f6a-146">Questo valore deve essere modificato in base al percorso di installazione e alla versione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="67f6a-146">This value needs to be changed according to your Visual Studio version and installation location.</span></span>  
  
7.  <span data-ttu-id="67f6a-147">Scegliere un valore per il campo **Directory iniziale**, ad esempio **Directory di progetto**.</span><span class="sxs-lookup"><span data-stu-id="67f6a-147">Choose a value for the **Initial directory** field such as **Project Directory** .</span></span>  
  
8.  <span data-ttu-id="67f6a-148">Fare clic sul pulsante **OK** .</span><span class="sxs-lookup"><span data-stu-id="67f6a-148">Choose the **OK** button.</span></span>  
  
 <span data-ttu-id="67f6a-149">Successivamente, viene aggiunta la nuova voce di menu ed è possibile accedere al prompt dei comandi dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="67f6a-149">After that, the new menu item is added and you can access the command prompt from the **Tools** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67f6a-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67f6a-150">See Also</span></span>  
 <span data-ttu-id="67f6a-151">[Strumenti](../../../docs/framework/tools/index.md) </span><span class="sxs-lookup"><span data-stu-id="67f6a-151">[Tools](../../../docs/framework/tools/index.md) </span></span>  
 [<span data-ttu-id="67f6a-152">Gestione di strumenti esterni</span><span class="sxs-lookup"><span data-stu-id="67f6a-152">Managing External Tools</span></span>](/visualstudio/ide/managing-external-tools)

