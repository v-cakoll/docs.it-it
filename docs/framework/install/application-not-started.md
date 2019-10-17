---
title: Risoluzione dei problemi ' Impossibile avviare l'applicazione '
description: Informazioni sulle operazioni da eseguire se viene visualizzata la finestra di dialogo "Impossibile avviare l'applicazione".
author: rpetrusha
ms.author: ronpet
ms.date: 09/05/2019
ms.openlocfilehash: 8fa8381f1b05445f259b4e4af5cc17fa487b2ce0
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319172"
---
# <a name="troubleshooting-a-this-application-could-not-be-started-error-message"></a><span data-ttu-id="f3dae-103">Risoluzione dei problemi relativi a un messaggio di errore "Impossibile avviare l'applicazione"</span><span class="sxs-lookup"><span data-stu-id="f3dae-103">Troubleshooting a 'This application could not be started' error message</span></span>

<span data-ttu-id="f3dae-104">Per le applicazioni sviluppate per il .NET Framework in genere è necessario che nel sistema sia installata una versione specifica del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f3dae-104">Applications that are developed for the .NET Framework typically require that a specific version of the .NET Framework be installed on your system.</span></span> <span data-ttu-id="f3dae-105">In alcuni casi, è possibile tentare di eseguire un'applicazione senza una versione installata o la versione prevista del .NET Framework presente.</span><span class="sxs-lookup"><span data-stu-id="f3dae-105">In some cases, you may attempt to run an application without either an installed version or the expected version of the .NET Framework present.</span></span> <span data-ttu-id="f3dae-106">Questa operazione spesso genera una finestra di dialogo di errore simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="f3dae-106">This often produces an error dialog box like the following:</span></span>

![Impossibile avviare l'applicazione](media/application-not-started/app-could-not-be-started.png)

<span data-ttu-id="f3dae-108">Questo indica in genere una delle seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="f3dae-108">This typically indicates one of the following conditions:</span></span>

- <span data-ttu-id="f3dae-109">Un .NET Framework installazione nel sistema è stato danneggiato.</span><span class="sxs-lookup"><span data-stu-id="f3dae-109">A .NET Framework installation on your system has become corrupted.</span></span>

- <span data-ttu-id="f3dae-110">Non è possibile rilevare la versione del .NET Framework richiesta dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f3dae-110">The version of the .NET Framework needed by your application cannot be detected.</span></span>

<span data-ttu-id="f3dae-111">Per risolvere questo problema in modo che sia possibile eseguire l'applicazione, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f3dae-111">To address this issue so that you can run your application, do the following:</span></span>

1. <span data-ttu-id="f3dae-112">Scaricare lo [strumento di ripristino .NET Framework (NetFxRepairTool. exe)](https://www.microsoft.com/download/details.aspx?id=30135).</span><span class="sxs-lookup"><span data-stu-id="f3dae-112">Download the [.NET Framework Repair Tool (NetFxRepairTool.exe)](https://www.microsoft.com/download/details.aspx?id=30135).</span></span> <span data-ttu-id="f3dae-113">Lo strumento viene eseguito automaticamente al termine del download.</span><span class="sxs-lookup"><span data-stu-id="f3dae-113">The tool runs automatically when the download completes.</span></span>

1. <span data-ttu-id="f3dae-114">Se lo strumento di ripristino .NET Framework consiglia di eseguire altre operazioni, ad esempio quelle illustrate nella figura seguente, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f3dae-114">If the .NET Framework Repair Tool recommends any additional action, such as those shown in the following figure, select **Next**.</span></span>

   ![Modifiche consigliate](media/application-not-started/repair-tool-recommended-changes.png)

1. <span data-ttu-id="f3dae-116">Negli strumenti di ripristino .NET Framework viene visualizzata una finestra di dialogo illustrata nella figura seguente per indicare che le modifiche sono state completate.</span><span class="sxs-lookup"><span data-stu-id="f3dae-116">The .NET Framework Repair Tools displays a dialog box shown in the following figure to indicate that changes are complete.</span></span> <span data-ttu-id="f3dae-117">Lasciare aperta la finestra di dialogo mentre si tenta di eseguire di nuovo l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f3dae-117">Leave the dialog box open while you to try rerun your application.</span></span> <span data-ttu-id="f3dae-118">Questa operazione dovrebbe avere esito positivo se lo strumento di ripristino .NET Framework ha identificato e corretto un'installazione .NET Framework danneggiata.</span><span class="sxs-lookup"><span data-stu-id="f3dae-118">This should succeed if the .NET Framework Repair Tool has identified and corrected a corrupted .NET Framework installation.</span></span>

   ![Modifiche consigliate](media/application-not-started/repair-tool-changes-complete.png)

1. <span data-ttu-id="f3dae-120">Se l'applicazione viene eseguita correttamente, selezionare il pulsante **fine** .</span><span class="sxs-lookup"><span data-stu-id="f3dae-120">If your application runs successfully, select the **Finish** button.</span></span> <span data-ttu-id="f3dae-121">In caso contrario, selezionare il pulsante **Avanti** .</span><span class="sxs-lookup"><span data-stu-id="f3dae-121">Otherwise, select the **Next** button.</span></span>

1. <span data-ttu-id="f3dae-122">Se è stato selezionato il pulsante **Avanti** , lo strumento .NET Framework Repair Visualizza una finestra di dialogo simile alla seguente.</span><span class="sxs-lookup"><span data-stu-id="f3dae-122">If you selected the **Next** button, the .NET Framework Repair Tool displays a dialog box like the following.</span></span> <span data-ttu-id="f3dae-123">Selezionare il pulsante **fine** per inviare le informazioni di diagnostica a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f3dae-123">Select the **Finish** button to send diagnostic information to Microsoft.</span></span>

   ![Non è possibile risolvere il problema](media/application-not-started/repair-tool-no-resolution.png)

1. <span data-ttu-id="f3dae-125">Se non è ancora possibile eseguire l'applicazione, installare la versione più recente del .NET Framework supportata dalla versione di Windows, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="f3dae-125">If you still cannot run the application, install the latest version of the .NET Framework supported by your version of Windows, as shown in the following table.</span></span>

   |<span data-ttu-id="f3dae-126">Versione di Windows</span><span class="sxs-lookup"><span data-stu-id="f3dae-126">Windows version</span></span>|<span data-ttu-id="f3dae-127">Installazione .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f3dae-127">.NET Framework installation</span></span>|
   |---|---|
   |<span data-ttu-id="f3dae-128">Aggiornamento dell'anniversario di Windows 10 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="f3dae-128">Windows 10 Anniversary Update and later versions</span></span>|[<span data-ttu-id="f3dae-129">Runtime di .NET Framework 4,8</span><span class="sxs-lookup"><span data-stu-id="f3dae-129">.NET Framework 4.8 Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |<span data-ttu-id="f3dae-130">Windows 10, aggiornamento di novembre di Windows 10</span><span class="sxs-lookup"><span data-stu-id="f3dae-130">Windows 10, Windows 10 November Update</span></span>|[<span data-ttu-id="f3dae-131">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="f3dae-131">.NET Framework 4.6.2</span></span>](https://www.microsoft.com/download/details.aspx?id=53345)|
   |<span data-ttu-id="f3dae-132">Windows 8,1</span><span class="sxs-lookup"><span data-stu-id="f3dae-132">Windows 8.1</span></span>|[<span data-ttu-id="f3dae-133">Runtime di .NET Framework 4,8</span><span class="sxs-lookup"><span data-stu-id="f3dae-133">.NET Framework 4.8 Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |<span data-ttu-id="f3dae-134">Windows 8</span><span class="sxs-lookup"><span data-stu-id="f3dae-134">Windows 8</span></span>|[<span data-ttu-id="f3dae-135">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="f3dae-135">.NET Framework 4.6.1</span></span>](https://www.microsoft.com/download/details.aspx?id=49981)|
   |<span data-ttu-id="f3dae-136">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="f3dae-136">Windows 7 SP1</span></span>|[<span data-ttu-id="f3dae-137">Runtime di .NET Framework 4,8</span><span class="sxs-lookup"><span data-stu-id="f3dae-137">.NET Framework 4.8 Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |<span data-ttu-id="f3dae-138">Windows Vista SP2</span><span class="sxs-lookup"><span data-stu-id="f3dae-138">Windows Vista SP2</span></span>|[<span data-ttu-id="f3dae-139">.NET Framework 4,6</span><span class="sxs-lookup"><span data-stu-id="f3dae-139">.NET Framework 4.6</span></span>](https://www.microsoft.com/download/details.aspx?id=48130)|

   > [!NOTE]
   > <span data-ttu-id="f3dae-140">.NET Framework 4,8 è preinstallato in Windows 10 può essere aggiornato con il 2019.</span><span class="sxs-lookup"><span data-stu-id="f3dae-140">.NET Framework 4.8 is preinstalled on Windows 10 May 2019 Update.</span></span>

1. <span data-ttu-id="f3dae-141">Tentare di avviare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f3dae-141">Attempt to launch the application.</span></span>

1. <span data-ttu-id="f3dae-142">In alcuni casi, è possibile che venga visualizzata una finestra di dialogo simile alla seguente, in cui viene chiesto di installare il .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="f3dae-142">In some cases, you may see a dialog box like the following, which asks you to install the .NET Framework 3.5.</span></span> <span data-ttu-id="f3dae-143">Selezionare **scaricare e installare questa funzionalità** per installare il .NET Framework 3,5, quindi avviare di nuovo l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f3dae-143">Select **Download and install this feature** to install the .NET Framework 3.5, then launch the application again.</span></span>

   ![Non è possibile risolvere il problema](media/application-not-started/install-3-5.png)

## <a name="see-also"></a><span data-ttu-id="f3dae-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3dae-145">See also</span></span>

- [<span data-ttu-id="f3dae-146">Requisiti di sistema .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f3dae-146">.NET Framework System Requirements</span></span>](../get-started/system-requirements.md)
- [<span data-ttu-id="f3dae-147">Guida all'installazione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f3dae-147">.NET Framework installation guide</span></span>](index.md)
- [<span data-ttu-id="f3dae-148">Risolvere i problemi relativi alle installazioni e alle disinstallazioni bloccate di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f3dae-148">Troubleshoot blocked .NET Framework installations and uninstallations</span></span>](troubleshoot-blocked-installations-and-uninstallations.md)
