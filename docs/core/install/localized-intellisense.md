---
title: Installare i file IntelliSense localizzati
description: Informazioni su come configurare il computer di sviluppo per l'uso di file IntelliSense localizzati per i progetti .NET Core in Visual Studio.
author: mairaw
ms.author: mairaw
ms.date: 12/18/2019
ms.openlocfilehash: 98d75544ab853e75c175dd2919991b250cfaa3b0
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75443477"
---
# <a name="how-to-install-localized-intellisense-files-for-net-core"></a><span data-ttu-id="fac77-103">Come installare i file IntelliSense localizzati per .NET Core</span><span class="sxs-lookup"><span data-stu-id="fac77-103">How to install localized IntelliSense files for .NET Core</span></span>

<span data-ttu-id="fac77-104">[IntelliSense](/visualstudio/ide/using-intellisense) è un supporto per il completamento del codice disponibile in diversi ambienti di sviluppo integrato (IDE), ad esempio Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fac77-104">[IntelliSense](/visualstudio/ide/using-intellisense) is a code-completion aid that is available in different integrated development environments (IDEs), such as Visual Studio.</span></span> <span data-ttu-id="fac77-105">Per impostazione predefinita, quando si sviluppano progetti .NET Core, l'SDK include solo la versione in lingua inglese dei file IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="fac77-105">By default, when you're developing .NET Core projects, the SDK only includes the English version of the IntelliSense files.</span></span> <span data-ttu-id="fac77-106">In questo articolo viene descritto quanto segue:</span><span class="sxs-lookup"><span data-stu-id="fac77-106">This article explains:</span></span>

- <span data-ttu-id="fac77-107">Come installare la versione localizzata di questi file.</span><span class="sxs-lookup"><span data-stu-id="fac77-107">How to install the localized version of those files.</span></span>
- <span data-ttu-id="fac77-108">Come modificare l'installazione di Visual Studio per usare una lingua diversa.</span><span class="sxs-lookup"><span data-stu-id="fac77-108">How to modify the Visual Studio installation to use a different language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fac77-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="fac77-109">Prerequisites</span></span>

- <span data-ttu-id="fac77-110">[.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="fac77-110">[.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) or a later version.</span></span>
- <span data-ttu-id="fac77-111">[Visual Studio 2019 versione 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o successiva.</span><span class="sxs-lookup"><span data-stu-id="fac77-111">[Visual Studio 2019 version 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or a later version.</span></span>

## <a name="download-and-install-the-localized-intellisense-files"></a><span data-ttu-id="fac77-112">Scaricare e installare i file IntelliSense localizzati</span><span class="sxs-lookup"><span data-stu-id="fac77-112">Download and install the localized IntelliSense files</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fac77-113">Per questa procedura è necessario avere le autorizzazioni di amministratore per copiare i file IntelliSense nella cartella di installazione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fac77-113">This procedure requires that you have administrator permission to copy the IntelliSense files to the .NET Core installation folder.</span></span>

1. <span data-ttu-id="fac77-114">Passare alla pagina per il [download dei file IntelliSense](https://dotnet.microsoft.com/download/dotnet-core/intellisense).</span><span class="sxs-lookup"><span data-stu-id="fac77-114">Go to the [Download IntelliSense files](https://dotnet.microsoft.com/download/dotnet-core/intellisense) page.</span></span>

1. <span data-ttu-id="fac77-115">Scaricare il file IntelliSense per la lingua e la versione che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="fac77-115">Download the IntelliSense file for the language and version you'd like to use.</span></span>

1. <span data-ttu-id="fac77-116">Estrarre il contenuto del file ZIP.</span><span class="sxs-lookup"><span data-stu-id="fac77-116">Extract the contents of the zip file.</span></span>

1. <span data-ttu-id="fac77-117">Passare alla cartella di installazione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fac77-117">Navigate to the .NET Core installation folder.</span></span> <span data-ttu-id="fac77-118">Per impostazione predefinita, è in *%ProgramFiles%\dotnet\packs*.</span><span class="sxs-lookup"><span data-stu-id="fac77-118">By default, it's under *%ProgramFiles%\dotnet\packs*.</span></span>

   - <span data-ttu-id="fac77-119">Scegliere l'SDK per cui si vuole installare IntelliSense e passare al percorso associato.</span><span class="sxs-lookup"><span data-stu-id="fac77-119">Choose which SDK you want to install the IntelliSense for, and navigate to the associated path.</span></span> <span data-ttu-id="fac77-120">Sono disponibili le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="fac77-120">You have the following options:</span></span>

      | <span data-ttu-id="fac77-121">Tipo di SDK</span><span class="sxs-lookup"><span data-stu-id="fac77-121">SDK type</span></span>        | <span data-ttu-id="fac77-122">Path</span><span class="sxs-lookup"><span data-stu-id="fac77-122">Path</span></span>                               |
      | --------------- | ---------------------------------- |
      | <span data-ttu-id="fac77-123">.NET Core</span><span class="sxs-lookup"><span data-stu-id="fac77-123">.NET Core</span></span>       | <span data-ttu-id="fac77-124">*Microsoft.NETCore.App.Ref*</span><span class="sxs-lookup"><span data-stu-id="fac77-124">*Microsoft.NETCore.App.Ref*</span></span>        |
      | <span data-ttu-id="fac77-125">Desktop di Windows</span><span class="sxs-lookup"><span data-stu-id="fac77-125">Windows Desktop</span></span> | <span data-ttu-id="fac77-126">*Microsoft.WindowsDesktop.App.Ref*</span><span class="sxs-lookup"><span data-stu-id="fac77-126">*Microsoft.WindowsDesktop.App.Ref*</span></span> |
      | <span data-ttu-id="fac77-127">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="fac77-127">.NET Standard</span></span>   | <span data-ttu-id="fac77-128">*NETStandard.Library.Ref*</span><span class="sxs-lookup"><span data-stu-id="fac77-128">*NETStandard.Library.Ref*</span></span>          |
   
   - <span data-ttu-id="fac77-129">Passare alla versione per cui si vuole installare la versione localizzata di IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="fac77-129">Navigate to the version you want to install the localized IntelliSense for.</span></span> <span data-ttu-id="fac77-130">Ad esempio, *3.1.0*.</span><span class="sxs-lookup"><span data-stu-id="fac77-130">For example, *3.1.0*.</span></span>
   - <span data-ttu-id="fac77-131">Aprire la cartella *ref*.</span><span class="sxs-lookup"><span data-stu-id="fac77-131">Open the *ref* folder.</span></span>
   - <span data-ttu-id="fac77-132">Aprire la cartella del moniker.</span><span class="sxs-lookup"><span data-stu-id="fac77-132">Open the moniker folder.</span></span> <span data-ttu-id="fac77-133">Ad esempio, *netcoreapp3.1*.</span><span class="sxs-lookup"><span data-stu-id="fac77-133">For example, *netcoreapp3.1*.</span></span>

   <span data-ttu-id="fac77-134">Il percorso completo a cui si accede dovrebbe essere quindi simile a *C:\Programmi\dotnet\packs\Microsoft.NETCore.App.Ref\3.1.0\ref\netcoreapp3.1*.</span><span class="sxs-lookup"><span data-stu-id="fac77-134">So, the full path that you'd navigate to would look similar to *C:\Program Files\dotnet\packs\Microsoft.NETCore.App.Ref\3.1.0\ref\netcoreapp3.1*.</span></span>

1. <span data-ttu-id="fac77-135">Creare una sottocartella all'interno della cartella del moniker appena aperta.</span><span class="sxs-lookup"><span data-stu-id="fac77-135">Create a subfolder inside the moniker folder you just opened.</span></span> <span data-ttu-id="fac77-136">Il nome della cartella indica la lingua da usare.</span><span class="sxs-lookup"><span data-stu-id="fac77-136">The name of the folder indicates which language you want to use.</span></span> <span data-ttu-id="fac77-137">Nella tabella seguente vengono specificate le diverse opzioni:</span><span class="sxs-lookup"><span data-stu-id="fac77-137">The following table specifies the different options:</span></span>

   | <span data-ttu-id="fac77-138">Linguaggio</span><span class="sxs-lookup"><span data-stu-id="fac77-138">Language</span></span>              | <span data-ttu-id="fac77-139">Nome cartella</span><span class="sxs-lookup"><span data-stu-id="fac77-139">Folder name</span></span> |
   | --------------------- | ----------- |
   | <span data-ttu-id="fac77-140">Portoghese brasiliano</span><span class="sxs-lookup"><span data-stu-id="fac77-140">Brazilian Portuguese</span></span>  | <span data-ttu-id="fac77-141">*pt-br*</span><span class="sxs-lookup"><span data-stu-id="fac77-141">*pt-br*</span></span>     |
   | <span data-ttu-id="fac77-142">Cinese (semplificato)</span><span class="sxs-lookup"><span data-stu-id="fac77-142">Chinese (simplified)</span></span>  | <span data-ttu-id="fac77-143">*zh-hans*</span><span class="sxs-lookup"><span data-stu-id="fac77-143">*zh-hans*</span></span>   |
   | <span data-ttu-id="fac77-144">Cinese (tradizionale)</span><span class="sxs-lookup"><span data-stu-id="fac77-144">Chinese (traditional)</span></span> | <span data-ttu-id="fac77-145">*zh-hant*</span><span class="sxs-lookup"><span data-stu-id="fac77-145">*zh-hant*</span></span>   |
   | <span data-ttu-id="fac77-146">Francese</span><span class="sxs-lookup"><span data-stu-id="fac77-146">French</span></span>                | <span data-ttu-id="fac77-147">*fr*</span><span class="sxs-lookup"><span data-stu-id="fac77-147">*fr*</span></span>        |
   | <span data-ttu-id="fac77-148">Tedesco</span><span class="sxs-lookup"><span data-stu-id="fac77-148">German</span></span>                | <span data-ttu-id="fac77-149">*de*</span><span class="sxs-lookup"><span data-stu-id="fac77-149">*de*</span></span>        |
   | <span data-ttu-id="fac77-150">Italiano</span><span class="sxs-lookup"><span data-stu-id="fac77-150">Italian</span></span>               | <span data-ttu-id="fac77-151">*it*</span><span class="sxs-lookup"><span data-stu-id="fac77-151">*it*</span></span>        |
   | <span data-ttu-id="fac77-152">Giapponese</span><span class="sxs-lookup"><span data-stu-id="fac77-152">Japanese</span></span>              | <span data-ttu-id="fac77-153">*ja*</span><span class="sxs-lookup"><span data-stu-id="fac77-153">*ja*</span></span>        |
   | <span data-ttu-id="fac77-154">Coreano</span><span class="sxs-lookup"><span data-stu-id="fac77-154">Korean</span></span>                | <span data-ttu-id="fac77-155">*ko*</span><span class="sxs-lookup"><span data-stu-id="fac77-155">*ko*</span></span>        |
   | <span data-ttu-id="fac77-156">Russo</span><span class="sxs-lookup"><span data-stu-id="fac77-156">Russian</span></span>               | <span data-ttu-id="fac77-157">*ru*</span><span class="sxs-lookup"><span data-stu-id="fac77-157">*ru*</span></span>        |
   | <span data-ttu-id="fac77-158">Spagnolo</span><span class="sxs-lookup"><span data-stu-id="fac77-158">Spanish</span></span>               | <span data-ttu-id="fac77-159">*es*</span><span class="sxs-lookup"><span data-stu-id="fac77-159">*es*</span></span>        |

1. <span data-ttu-id="fac77-160">Copiare i file con estensione *xml* estratti nel passaggio 3 in questa nuova cartella.</span><span class="sxs-lookup"><span data-stu-id="fac77-160">Copy the *.xml* files you extracted on step 3 to this new folder.</span></span> <span data-ttu-id="fac77-161">I file con estensione *xml* sono suddivisi in base alle cartelle degli SDK, quindi copiarli nell'SDK corrispondente scelto nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="fac77-161">The *.xml* files are broken down by SDK folders, so copy them to the matching SDK you chose on step 4.</span></span>

## <a name="modify-visual-studio-language"></a><span data-ttu-id="fac77-162">Modificare la lingua di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fac77-162">Modify Visual Studio language</span></span>

<span data-ttu-id="fac77-163">Per fare in modo che Visual Studio usi una lingua diversa per IntelliSense, installare il language pack appropriato.</span><span class="sxs-lookup"><span data-stu-id="fac77-163">For Visual Studio to use a different language for IntelliSense, install the appropriate language pack.</span></span> <span data-ttu-id="fac77-164">Questa operazione può essere eseguita [durante l'installazione](/visualstudio/install/install-visual-studio#step-6---install-language-packs-optional) o in un secondo momento modificando l'installazione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fac77-164">This can be done [during installation](/visualstudio/install/install-visual-studio#step-6---install-language-packs-optional) or at a later time by modifying the Visual Studio installation.</span></span> <span data-ttu-id="fac77-165">Se Visual Studio è già configurato per la lingua scelta, l'installazione di IntelliSense è pronta.</span><span class="sxs-lookup"><span data-stu-id="fac77-165">If you already have Visual Studio configured to the language of your choice, your IntelliSense installation is ready.</span></span>

### <a name="install-the-language-pack"></a><span data-ttu-id="fac77-166">Installare il language pack</span><span class="sxs-lookup"><span data-stu-id="fac77-166">Install the language pack</span></span>

<span data-ttu-id="fac77-167">Se il language pack desiderato non è stato installato durante l'installazione, aggiornare Visual Studio come indicato di seguito per installare il language pack:</span><span class="sxs-lookup"><span data-stu-id="fac77-167">If you didn't install the desired language pack during setup, update Visual Studio as follows to install the language pack:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fac77-168">Per installare, aggiornare o modificare Visual Studio, è necessario accedere con un account con autorizzazioni amministrative.</span><span class="sxs-lookup"><span data-stu-id="fac77-168">To install, update, or modify Visual Studio, you must log on with an account that has administrative permissions.</span></span> <span data-ttu-id="fac77-169">Per altre informazioni, vedere [Autorizzazioni utente e Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="fac77-169">For more information, see [User permissions and Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio).</span></span>

1. <span data-ttu-id="fac77-170">Individuare il programma di installazione di Visual Studio all'interno del computer in uso.</span><span class="sxs-lookup"><span data-stu-id="fac77-170">Find the Visual Studio Installer on your computer.</span></span>

   <span data-ttu-id="fac77-171">Ad esempio, in un computer che esegue Windows 10 selezionare **Start** e scorrere fino alla lettera **P** in cui viene visualizzato come **Programma di installazione di Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="fac77-171">For example, on a computer running Windows 10, select **Start**, and then scroll to the letter **V**, where it's listed as **Visual Studio Installer**.</span></span>

   ![Aprire il programma di installazione di Visual Studio da Windows](./media/localized-intellisense/vs-installer-windows-start.png)

   > [!NOTE]
   > <span data-ttu-id="fac77-173">È anche possibile trovare il programma di installazione di Visual Studio nella posizione seguente:</span><span class="sxs-lookup"><span data-stu-id="fac77-173">You can also find the Visual Studio Installer in the following location:</span></span>
   >
   > `C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe`

   <span data-ttu-id="fac77-174">Prima di continuare, potrebbe essere necessario aggiornare il programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="fac77-174">You might have to update the installer before continuing.</span></span> <span data-ttu-id="fac77-175">In questo caso, seguire i prompt.</span><span class="sxs-lookup"><span data-stu-id="fac77-175">If so, follow the prompts.</span></span>

1. <span data-ttu-id="fac77-176">Nel programma di installazione cercare l'edizione di Visual Studio a cui si vuole aggiungere il language pack e quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="fac77-176">In the installer, look for the edition of Visual Studio that you want to add the language pack to, and then choose **Modify**.</span></span>

   ![Aggiornare o modificare Visual Studio](./media/localized-intellisense/vs-installer-modify.png)

   > [!IMPORTANT]
   > <span data-ttu-id="fac77-178">Se non viene visualizzato il pulsante **Modifica** ma viene invece visualizzato il pulsante **Aggiorna**, è necessario aggiornare Visual Studio prima di poter modificare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="fac77-178">If you don't see a **Modify** button but you see an **Update** one instead, you need to update your Visual Studio before you can modify your installation.</span></span>
   > <span data-ttu-id="fac77-179">Al termine dell'aggiornamento, verrà visualizzato il pulsante **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="fac77-179">After the update is finished, the **Modify** button should appear.</span></span>

1. <span data-ttu-id="fac77-180">Nella scheda **Language pack** selezionare o deselezionare le lingue da installare o disinstallare.</span><span class="sxs-lookup"><span data-stu-id="fac77-180">In the **Language packs** tab, select or deselect the languages you want to install or uninstall.</span></span>

   ![Scheda Language pack di Visual Studio](./media/localized-intellisense/vs-modify-language-packs.png)

1. <span data-ttu-id="fac77-182">Scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="fac77-182">Choose **Modify**.</span></span> <span data-ttu-id="fac77-183">L'aggiornamento si avvia.</span><span class="sxs-lookup"><span data-stu-id="fac77-183">The update starts.</span></span>

### <a name="modify-language-settings-in-visual-studio"></a><span data-ttu-id="fac77-184">Modificare le impostazioni di lingua in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fac77-184">Modify language settings in Visual Studio</span></span>

<span data-ttu-id="fac77-185">Dopo aver installato i language pack desiderati, modificare le impostazioni di Visual Studio per usare una lingua diversa:</span><span class="sxs-lookup"><span data-stu-id="fac77-185">Once you've installed the desired language packs, modify your Visual Studio settings to use a different language:</span></span>

1. <span data-ttu-id="fac77-186">Aprire Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fac77-186">Open Visual Studio.</span></span>

1. <span data-ttu-id="fac77-187">Nella finestra iniziale scegliere **Continua senza codice**.</span><span class="sxs-lookup"><span data-stu-id="fac77-187">On the start window, choose **Continue without code**.</span></span>

1. <span data-ttu-id="fac77-188">Nel menu principale selezionare **Strumenti** > **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="fac77-188">On the main menu, select **Tools** > **Options**.</span></span> <span data-ttu-id="fac77-189">Verrà visualizzata la finestra di dialogo Opzioni.</span><span class="sxs-lookup"><span data-stu-id="fac77-189">The Options dialog opens.</span></span>

1. <span data-ttu-id="fac77-190">Nella cartella **Ambiente** scegliere **impostazioni internazionali**.</span><span class="sxs-lookup"><span data-stu-id="fac77-190">Under the **Environment** folder, choose **International Settings**.</span></span>

1. <span data-ttu-id="fac77-191">Nell'elenco a discesa **Lingua** selezionare la lingua desiderata.</span><span class="sxs-lookup"><span data-stu-id="fac77-191">On the **Language** drop-down, select the desired language.</span></span> <span data-ttu-id="fac77-192">Scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="fac77-192">Choose **OK**.</span></span> 

1. <span data-ttu-id="fac77-193">Una finestra di dialogo informa che è necessario riavviare Visual Studio per rendere effettive le modifiche.</span><span class="sxs-lookup"><span data-stu-id="fac77-193">A dialog informs you that you have to restart Visual Studio for the changes to take effect.</span></span> <span data-ttu-id="fac77-194">Scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="fac77-194">Choose **OK**.</span></span>

1. <span data-ttu-id="fac77-195">Riavviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fac77-195">Restart Visual Studio.</span></span>

<span data-ttu-id="fac77-196">Al termine di questa operazione, IntelliSense dovrebbe funzionare come previsto quando si apre un progetto .NET Core destinato alla versione dei file IntelliSense appena installati.</span><span class="sxs-lookup"><span data-stu-id="fac77-196">After this, your IntelliSense should work as expected when you open a .NET Core project that targets the version of the IntelliSense files you just installed.</span></span>

## <a name="see-also"></a><span data-ttu-id="fac77-197">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fac77-197">See also</span></span>

- [<span data-ttu-id="fac77-198">IntelliSense in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fac77-198">IntelliSense in Visual Studio</span></span>](/visualstudio/ide/using-intellisense)
