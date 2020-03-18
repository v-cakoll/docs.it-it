---
title: Installare i file IntelliSense localizzati
description: Informazioni su come configurare il computer di sviluppo per l'uso di file IntelliSense localizzati per i progetti .NET Core in Visual Studio.
ms.date: 01/23/2020
ms.openlocfilehash: e45e225e58865ca2b529000ada0984fbeca850f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78157713"
---
# <a name="how-to-install-localized-intellisense-files-for-net-core"></a><span data-ttu-id="b6404-103">Come installare i file IntelliSense localizzati per .NET Core</span><span class="sxs-lookup"><span data-stu-id="b6404-103">How to install localized IntelliSense files for .NET Core</span></span>

<span data-ttu-id="b6404-104">[IntelliSense](/visualstudio/ide/using-intellisense) è un supporto per il completamento del codice disponibile in diversi ambienti di sviluppo integrato (IDE), ad esempio Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b6404-104">[IntelliSense](/visualstudio/ide/using-intellisense) is a code-completion aid that is available in different integrated development environments (IDEs), such as Visual Studio.</span></span> <span data-ttu-id="b6404-105">Per impostazione predefinita, quando si sviluppano progetti .NET Core, l'SDK include solo la versione in lingua inglese dei file IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="b6404-105">By default, when you're developing .NET Core projects, the SDK only includes the English version of the IntelliSense files.</span></span> <span data-ttu-id="b6404-106">In questo articolo viene descritto quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b6404-106">This article explains:</span></span>

- <span data-ttu-id="b6404-107">Come installare la versione localizzata di questi file.</span><span class="sxs-lookup"><span data-stu-id="b6404-107">How to install the localized version of those files.</span></span>
- <span data-ttu-id="b6404-108">Come modificare l'installazione di Visual Studio per usare una lingua diversa.</span><span class="sxs-lookup"><span data-stu-id="b6404-108">How to modify the Visual Studio installation to use a different language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b6404-109">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="b6404-109">Prerequisites</span></span>

- <span data-ttu-id="b6404-110">[.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="b6404-110">[.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) or a later version.</span></span>
- <span data-ttu-id="b6404-111">[Visual Studio 2019 versione 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o successiva.</span><span class="sxs-lookup"><span data-stu-id="b6404-111">[Visual Studio 2019 version 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or a later version.</span></span>

## <a name="download-and-install-the-localized-intellisense-files"></a><span data-ttu-id="b6404-112">Scaricare e installare i file IntelliSense localizzati</span><span class="sxs-lookup"><span data-stu-id="b6404-112">Download and install the localized IntelliSense files</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6404-113">Per questa procedura è necessario avere le autorizzazioni di amministratore per copiare i file IntelliSense nella cartella di installazione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b6404-113">This procedure requires that you have administrator permission to copy the IntelliSense files to the .NET Core installation folder.</span></span>

1. <span data-ttu-id="b6404-114">Passare alla pagina per il [download dei file IntelliSense](https://dotnet.microsoft.com/download/dotnet-core/intellisense).</span><span class="sxs-lookup"><span data-stu-id="b6404-114">Go to the [Download IntelliSense files](https://dotnet.microsoft.com/download/dotnet-core/intellisense) page.</span></span>

1. <span data-ttu-id="b6404-115">Scaricare il file IntelliSense per la lingua e la versione che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="b6404-115">Download the IntelliSense file for the language and version you'd like to use.</span></span>

1. <span data-ttu-id="b6404-116">Estrarre il contenuto del file ZIP.</span><span class="sxs-lookup"><span data-stu-id="b6404-116">Extract the contents of the zip file.</span></span>

1. <span data-ttu-id="b6404-117">Passare alla cartella Intellisense di .NET Core.Navigate to the .NET Core Intellisense folder.</span><span class="sxs-lookup"><span data-stu-id="b6404-117">Navigate to the .NET Core Intellisense folder.</span></span>

   1. <span data-ttu-id="b6404-118">Passare alla cartella di installazione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b6404-118">Navigate to the .NET Core installation folder.</span></span> <span data-ttu-id="b6404-119">Per impostazione predefinita, è in *%ProgramFiles%\dotnet\packs*.</span><span class="sxs-lookup"><span data-stu-id="b6404-119">By default, it's under *%ProgramFiles%\dotnet\packs*.</span></span>
   1. <span data-ttu-id="b6404-120">Scegliere l'SDK per cui si vuole installare IntelliSense e passare al percorso associato.</span><span class="sxs-lookup"><span data-stu-id="b6404-120">Choose which SDK you want to install the IntelliSense for, and navigate to the associated path.</span></span> <span data-ttu-id="b6404-121">L'utente ha a disposizione le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="b6404-121">You have the following options:</span></span>

      | <span data-ttu-id="b6404-122">Tipo di SDK</span><span class="sxs-lookup"><span data-stu-id="b6404-122">SDK type</span></span>        | <span data-ttu-id="b6404-123">Path</span><span class="sxs-lookup"><span data-stu-id="b6404-123">Path</span></span>                               |
      | --------------- | ---------------------------------- |
      | <span data-ttu-id="b6404-124">.NET Core</span><span class="sxs-lookup"><span data-stu-id="b6404-124">.NET Core</span></span>       | <span data-ttu-id="b6404-125">*Microsoft.NETCore.App.Ref*</span><span class="sxs-lookup"><span data-stu-id="b6404-125">*Microsoft.NETCore.App.Ref*</span></span>        |
      | <span data-ttu-id="b6404-126">Desktop di Windows</span><span class="sxs-lookup"><span data-stu-id="b6404-126">Windows Desktop</span></span> | <span data-ttu-id="b6404-127">*Microsoft.WindowsDesktop.App.Ref*</span><span class="sxs-lookup"><span data-stu-id="b6404-127">*Microsoft.WindowsDesktop.App.Ref*</span></span> |
      | <span data-ttu-id="b6404-128">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="b6404-128">.NET Standard</span></span>   | <span data-ttu-id="b6404-129">*NETStandard.Library.Ref*</span><span class="sxs-lookup"><span data-stu-id="b6404-129">*NETStandard.Library.Ref*</span></span>          |

   1. <span data-ttu-id="b6404-130">Passare alla versione per cui si vuole installare la versione localizzata di IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="b6404-130">Navigate to the version you want to install the localized IntelliSense for.</span></span> <span data-ttu-id="b6404-131">Ad esempio, *3.1.0*.</span><span class="sxs-lookup"><span data-stu-id="b6404-131">For example, *3.1.0*.</span></span>
   1. <span data-ttu-id="b6404-132">Aprire la cartella *ref*.</span><span class="sxs-lookup"><span data-stu-id="b6404-132">Open the *ref* folder.</span></span>
   1. <span data-ttu-id="b6404-133">Aprire la cartella del moniker.</span><span class="sxs-lookup"><span data-stu-id="b6404-133">Open the moniker folder.</span></span> <span data-ttu-id="b6404-134">Ad esempio, *netcoreapp3.1*.</span><span class="sxs-lookup"><span data-stu-id="b6404-134">For example, *netcoreapp3.1*.</span></span>

   <span data-ttu-id="b6404-135">Il percorso completo a cui si accede dovrebbe essere quindi simile a *C:\Programmi\dotnet\packs\Microsoft.NETCore.App.Ref\3.1.0\ref\netcoreapp3.1*.</span><span class="sxs-lookup"><span data-stu-id="b6404-135">So, the full path that you'd navigate to would look similar to *C:\Program Files\dotnet\packs\Microsoft.NETCore.App.Ref\3.1.0\ref\netcoreapp3.1*.</span></span>

1. <span data-ttu-id="b6404-136">Creare una sottocartella all'interno della cartella del moniker appena aperta.</span><span class="sxs-lookup"><span data-stu-id="b6404-136">Create a subfolder inside the moniker folder you just opened.</span></span> <span data-ttu-id="b6404-137">Il nome della cartella indica la lingua da usare.</span><span class="sxs-lookup"><span data-stu-id="b6404-137">The name of the folder indicates which language you want to use.</span></span> <span data-ttu-id="b6404-138">Nella tabella seguente vengono specificate le diverse opzioni:</span><span class="sxs-lookup"><span data-stu-id="b6404-138">The following table specifies the different options:</span></span>

   | <span data-ttu-id="b6404-139">Linguaggio</span><span class="sxs-lookup"><span data-stu-id="b6404-139">Language</span></span>              | <span data-ttu-id="b6404-140">Nome cartella</span><span class="sxs-lookup"><span data-stu-id="b6404-140">Folder name</span></span> |
   | --------------------- | ----------- |
   | <span data-ttu-id="b6404-141">Portoghese brasiliano</span><span class="sxs-lookup"><span data-stu-id="b6404-141">Brazilian Portuguese</span></span>  | <span data-ttu-id="b6404-142">*pt-br*</span><span class="sxs-lookup"><span data-stu-id="b6404-142">*pt-br*</span></span>     |
   | <span data-ttu-id="b6404-143">Cinese (semplificato)</span><span class="sxs-lookup"><span data-stu-id="b6404-143">Chinese (simplified)</span></span>  | <span data-ttu-id="b6404-144">*zh-hans*</span><span class="sxs-lookup"><span data-stu-id="b6404-144">*zh-hans*</span></span>   |
   | <span data-ttu-id="b6404-145">Cinese (tradizionale)</span><span class="sxs-lookup"><span data-stu-id="b6404-145">Chinese (traditional)</span></span> | <span data-ttu-id="b6404-146">*zh-hant*</span><span class="sxs-lookup"><span data-stu-id="b6404-146">*zh-hant*</span></span>   |
   | <span data-ttu-id="b6404-147">Francese</span><span class="sxs-lookup"><span data-stu-id="b6404-147">French</span></span>                | <span data-ttu-id="b6404-148">*fr*</span><span class="sxs-lookup"><span data-stu-id="b6404-148">*fr*</span></span>        |
   | <span data-ttu-id="b6404-149">Tedesco</span><span class="sxs-lookup"><span data-stu-id="b6404-149">German</span></span>                | <span data-ttu-id="b6404-150">*de*</span><span class="sxs-lookup"><span data-stu-id="b6404-150">*de*</span></span>        |
   | <span data-ttu-id="b6404-151">Italiano</span><span class="sxs-lookup"><span data-stu-id="b6404-151">Italian</span></span>               | <span data-ttu-id="b6404-152">*it*</span><span class="sxs-lookup"><span data-stu-id="b6404-152">*it*</span></span>        |
   | <span data-ttu-id="b6404-153">Giapponese</span><span class="sxs-lookup"><span data-stu-id="b6404-153">Japanese</span></span>              | <span data-ttu-id="b6404-154">*ja*</span><span class="sxs-lookup"><span data-stu-id="b6404-154">*ja*</span></span>        |
   | <span data-ttu-id="b6404-155">Coreano</span><span class="sxs-lookup"><span data-stu-id="b6404-155">Korean</span></span>                | <span data-ttu-id="b6404-156">*ko*</span><span class="sxs-lookup"><span data-stu-id="b6404-156">*ko*</span></span>        |
   | <span data-ttu-id="b6404-157">Russo</span><span class="sxs-lookup"><span data-stu-id="b6404-157">Russian</span></span>               | <span data-ttu-id="b6404-158">*ru*</span><span class="sxs-lookup"><span data-stu-id="b6404-158">*ru*</span></span>        |
   | <span data-ttu-id="b6404-159">Spagnolo</span><span class="sxs-lookup"><span data-stu-id="b6404-159">Spanish</span></span>               | <span data-ttu-id="b6404-160">*es*</span><span class="sxs-lookup"><span data-stu-id="b6404-160">*es*</span></span>        |

1. <span data-ttu-id="b6404-161">Copiare i file con estensione *xml* estratti nel passaggio 3 in questa nuova cartella.</span><span class="sxs-lookup"><span data-stu-id="b6404-161">Copy the *.xml* files you extracted on step 3 to this new folder.</span></span> <span data-ttu-id="b6404-162">I file con estensione *xml* sono suddivisi in base alle cartelle degli SDK, quindi copiarli nell'SDK corrispondente scelto nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="b6404-162">The *.xml* files are broken down by SDK folders, so copy them to the matching SDK you chose on step 4.</span></span>

## <a name="modify-visual-studio-language"></a><span data-ttu-id="b6404-163">Modificare la lingua di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b6404-163">Modify Visual Studio language</span></span>

<span data-ttu-id="b6404-164">Per fare in modo che Visual Studio usi una lingua diversa per IntelliSense, installare il language pack appropriato.</span><span class="sxs-lookup"><span data-stu-id="b6404-164">For Visual Studio to use a different language for IntelliSense, install the appropriate language pack.</span></span> <span data-ttu-id="b6404-165">Questa operazione può essere eseguita [durante l'installazione](/visualstudio/install/install-visual-studio#step-6---install-language-packs-optional) o in un secondo momento modificando l'installazione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b6404-165">This can be done [during installation](/visualstudio/install/install-visual-studio#step-6---install-language-packs-optional) or at a later time by modifying the Visual Studio installation.</span></span> <span data-ttu-id="b6404-166">Se Visual Studio è già configurato per la lingua scelta, l'installazione di IntelliSense è pronta.</span><span class="sxs-lookup"><span data-stu-id="b6404-166">If you already have Visual Studio configured to the language of your choice, your IntelliSense installation is ready.</span></span>

### <a name="install-the-language-pack"></a><span data-ttu-id="b6404-167">Installare il language pack</span><span class="sxs-lookup"><span data-stu-id="b6404-167">Install the language pack</span></span>

<span data-ttu-id="b6404-168">Se il language pack desiderato non è stato installato durante l'installazione, aggiornare Visual Studio come indicato di seguito per installare il language pack:</span><span class="sxs-lookup"><span data-stu-id="b6404-168">If you didn't install the desired language pack during setup, update Visual Studio as follows to install the language pack:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6404-169">Per installare, aggiornare o modificare Visual Studio, è necessario accedere con un account che disponga dell'autorizzazione di amministratore.</span><span class="sxs-lookup"><span data-stu-id="b6404-169">To install, update, or modify Visual Studio, you must log on with an account that has administrator permission.</span></span> <span data-ttu-id="b6404-170">Per altre informazioni, vedere [Autorizzazioni utente e Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="b6404-170">For more information, see [User permissions and Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio).</span></span>

1. <span data-ttu-id="b6404-171">Individuare il programma di installazione di Visual Studio all'interno del computer in uso.</span><span class="sxs-lookup"><span data-stu-id="b6404-171">Find the Visual Studio Installer on your computer.</span></span>

   <span data-ttu-id="b6404-172">Ad esempio, in un computer che esegue Windows 10 selezionare **Start** e scorrere fino alla lettera **P** in cui viene visualizzato come **Programma di installazione di Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="b6404-172">For example, on a computer running Windows 10, select **Start**, and then scroll to the letter **V**, where it's listed as **Visual Studio Installer**.</span></span>

   ![Aprire il programma di installazione di Visual Studio da Windows](./media/localized-intellisense/vs-installer-windows-start.png)

   > [!NOTE]
   > <span data-ttu-id="b6404-174">È anche possibile trovare il programma di installazione di Visual Studio nella posizione seguente:</span><span class="sxs-lookup"><span data-stu-id="b6404-174">You can also find the Visual Studio Installer in the following location:</span></span>
   >
   > `C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe`

   <span data-ttu-id="b6404-175">Prima di continuare, potrebbe essere necessario aggiornare il programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="b6404-175">You might have to update the installer before continuing.</span></span> <span data-ttu-id="b6404-176">In questo caso, seguire i prompt.</span><span class="sxs-lookup"><span data-stu-id="b6404-176">If so, follow the prompts.</span></span>

1. <span data-ttu-id="b6404-177">Nel programma di installazione cercare l'edizione di Visual Studio a cui si vuole aggiungere il language pack e quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="b6404-177">In the installer, look for the edition of Visual Studio that you want to add the language pack to, and then choose **Modify**.</span></span>

   ![Aggiornare o modificare Visual Studio](./media/localized-intellisense/vs-installer-modify.png)

   > [!IMPORTANT]
   > <span data-ttu-id="b6404-179">Se non viene visualizzato il pulsante **Modifica** ma viene invece visualizzato il pulsante **Aggiorna**, è necessario aggiornare Visual Studio prima di poter modificare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="b6404-179">If you don't see a **Modify** button but you see an **Update** one instead, you need to update your Visual Studio before you can modify your installation.</span></span>
   > <span data-ttu-id="b6404-180">Al termine dell'aggiornamento, verrà visualizzato il pulsante **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="b6404-180">After the update is finished, the **Modify** button should appear.</span></span>

1. <span data-ttu-id="b6404-181">Nella scheda **Language pack** selezionare o deselezionare le lingue da installare o disinstallare.</span><span class="sxs-lookup"><span data-stu-id="b6404-181">In the **Language packs** tab, select or deselect the languages you want to install or uninstall.</span></span>

   ![Scheda Language pack di Visual Studio](./media/localized-intellisense/vs-modify-language-packs.png)

1. <span data-ttu-id="b6404-183">Scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="b6404-183">Choose **Modify**.</span></span> <span data-ttu-id="b6404-184">L'aggiornamento si avvia.</span><span class="sxs-lookup"><span data-stu-id="b6404-184">The update starts.</span></span>

### <a name="modify-language-settings-in-visual-studio"></a><span data-ttu-id="b6404-185">Modificare le impostazioni di lingua in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b6404-185">Modify language settings in Visual Studio</span></span>

<span data-ttu-id="b6404-186">Dopo aver installato i language pack desiderati, modificare le impostazioni di Visual Studio per usare una lingua diversa:</span><span class="sxs-lookup"><span data-stu-id="b6404-186">Once you've installed the desired language packs, modify your Visual Studio settings to use a different language:</span></span>

1. <span data-ttu-id="b6404-187">Aprire Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b6404-187">Open Visual Studio.</span></span>

1. <span data-ttu-id="b6404-188">Nella finestra iniziale scegliere **Continua senza codice**.</span><span class="sxs-lookup"><span data-stu-id="b6404-188">On the start window, choose **Continue without code**.</span></span>

1. <span data-ttu-id="b6404-189">Nella barra dei menu, selezionare**Opzioni** **degli strumenti.** > </span><span class="sxs-lookup"><span data-stu-id="b6404-189">On the menu bar, select **Tools** > **Options**.</span></span> <span data-ttu-id="b6404-190">Verrà visualizzata la finestra di dialogo Opzioni.</span><span class="sxs-lookup"><span data-stu-id="b6404-190">The Options dialog opens.</span></span>

1. <span data-ttu-id="b6404-191">Nel nodo **Ambiente** scegliere **Impostazioni internazionali**.</span><span class="sxs-lookup"><span data-stu-id="b6404-191">Under the **Environment** node, choose **International Settings**.</span></span>

1. <span data-ttu-id="b6404-192">Nell'elenco a discesa **Lingua** selezionare la lingua desiderata.</span><span class="sxs-lookup"><span data-stu-id="b6404-192">On the **Language** drop-down, select the desired language.</span></span> <span data-ttu-id="b6404-193">Scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6404-193">Choose **OK**.</span></span>

1. <span data-ttu-id="b6404-194">Una finestra di dialogo informa che è necessario riavviare Visual Studio per rendere effettive le modifiche.</span><span class="sxs-lookup"><span data-stu-id="b6404-194">A dialog informs you that you have to restart Visual Studio for the changes to take effect.</span></span> <span data-ttu-id="b6404-195">Scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6404-195">Choose **OK**.</span></span>

1. <span data-ttu-id="b6404-196">Riavviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b6404-196">Restart Visual Studio.</span></span>

<span data-ttu-id="b6404-197">Al termine di questa operazione, IntelliSense dovrebbe funzionare come previsto quando si apre un progetto .NET Core destinato alla versione dei file IntelliSense appena installati.</span><span class="sxs-lookup"><span data-stu-id="b6404-197">After this, your IntelliSense should work as expected when you open a .NET Core project that targets the version of the IntelliSense files you just installed.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6404-198">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6404-198">See also</span></span>

- [<span data-ttu-id="b6404-199">IntelliSense in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b6404-199">IntelliSense in Visual Studio</span></span>](/visualstudio/ide/using-intellisense)
