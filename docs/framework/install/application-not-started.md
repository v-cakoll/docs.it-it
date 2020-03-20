---
title: Risoluzione dei problemi 'Impossibile riavviare l'applicazione'
description: Informazioni su come eseguire se viene visualizzata la finestra di dialogo "Impossibile iniziare l'applicazione".
ms.date: 09/05/2019
ms.openlocfilehash: 864c6ea23e9a048f060eee39d904bd4377be5084
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "76965906"
---
# <a name="troubleshooting-a-this-application-could-not-be-started-error-message"></a><span data-ttu-id="033c3-103">Risoluzione dei problemi relativi a un messaggio di errore "Impossibile utilizzare l'applicazione"</span><span class="sxs-lookup"><span data-stu-id="033c3-103">Troubleshooting a 'This application could not be started' error message</span></span>

<span data-ttu-id="033c3-104">Le applicazioni sviluppate per .NET Framework richiedono in genere l'installazione di una versione specifica di .NET Framework nel sistema.</span><span class="sxs-lookup"><span data-stu-id="033c3-104">Applications that are developed for the .NET Framework typically require that a specific version of the .NET Framework be installed on your system.</span></span> <span data-ttu-id="033c3-105">In alcuni casi, è possibile tentare di eseguire un'applicazione senza una versione installata o la versione prevista di .NET Framework presente.</span><span class="sxs-lookup"><span data-stu-id="033c3-105">In some cases, you may attempt to run an application without either an installed version or the expected version of the .NET Framework present.</span></span> <span data-ttu-id="033c3-106">Questo spesso produce una finestra di dialogo di errore simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="033c3-106">This often produces an error dialog box like the following:</span></span>

![Impossibile avviare l'applicazione](media/application-not-started/app-could-not-be-started.png)

<span data-ttu-id="033c3-108">Ciò indica in genere una delle seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="033c3-108">This typically indicates one of the following conditions:</span></span>

- <span data-ttu-id="033c3-109">Un'installazione di .NET Framework nel sistema è danneggiata.</span><span class="sxs-lookup"><span data-stu-id="033c3-109">A .NET Framework installation on your system has become corrupted.</span></span>

- <span data-ttu-id="033c3-110">La versione di .NET Framework necessaria per l'applicazione non può essere rilevata.</span><span class="sxs-lookup"><span data-stu-id="033c3-110">The version of the .NET Framework needed by your application cannot be detected.</span></span>

<span data-ttu-id="033c3-111">Per risolvere questo problema in modo da poter eseguire l'applicazione, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="033c3-111">To address this issue so that you can run your application, do the following:</span></span>

1. <span data-ttu-id="033c3-112">Scaricare lo strumento di ripristino di [.NET Framework (NetFxRepairTool.exe)](https://www.microsoft.com/download/details.aspx?id=30135).</span><span class="sxs-lookup"><span data-stu-id="033c3-112">Download the [.NET Framework Repair Tool (NetFxRepairTool.exe)](https://www.microsoft.com/download/details.aspx?id=30135).</span></span> <span data-ttu-id="033c3-113">Lo strumento viene eseguito automaticamente al termine del download.</span><span class="sxs-lookup"><span data-stu-id="033c3-113">The tool runs automatically when the download completes.</span></span>

1. <span data-ttu-id="033c3-114">Se lo strumento di ripristino di .NET Framework consiglia un'azione aggiuntiva, ad esempio quelle illustrate nella figura seguente, selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="033c3-114">If the .NET Framework Repair Tool recommends any additional action, such as those shown in the following figure, select **Next**.</span></span>

   ![Modifiche consigliate](media/application-not-started/repair-tool-recommended-changes.png)

1. <span data-ttu-id="033c3-116">Gli strumenti di ripristino di .NET Framework visualizzano una finestra di dialogo illustrata nella figura seguente per indicare che le modifiche sono state completate.</span><span class="sxs-lookup"><span data-stu-id="033c3-116">The .NET Framework Repair Tools displays a dialog box shown in the following figure to indicate that changes are complete.</span></span> <span data-ttu-id="033c3-117">Lasciare aperta la finestra di dialogo mentre si tenta di eseguire nuovamente l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="033c3-117">Leave the dialog box open while you to try rerun your application.</span></span> <span data-ttu-id="033c3-118">Questa operazione dovrebbe avere esito positivo se lo strumento di ripristino di .NET Framework ha identificato e corretto un'installazione danneggiata di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="033c3-118">This should succeed if the .NET Framework Repair Tool has identified and corrected a corrupted .NET Framework installation.</span></span>

   ![Modifiche consigliate](media/application-not-started/repair-tool-changes-complete.png)

1. <span data-ttu-id="033c3-120">Se l'applicazione viene eseguita correttamente, selezionare il pulsante **Fine.**</span><span class="sxs-lookup"><span data-stu-id="033c3-120">If your application runs successfully, select the **Finish** button.</span></span> <span data-ttu-id="033c3-121">In caso contrario, selezionare il pulsante **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="033c3-121">Otherwise, select the **Next** button.</span></span>

1. <span data-ttu-id="033c3-122">Se è stato selezionato il pulsante **Avanti,** lo strumento di ripristino di .NET Framework visualizza una finestra di dialogo simile alla seguente.</span><span class="sxs-lookup"><span data-stu-id="033c3-122">If you selected the **Next** button, the .NET Framework Repair Tool displays a dialog box like the following.</span></span> <span data-ttu-id="033c3-123">Selezionare il pulsante Fine per inviare informazioni diagnostiche a Microsoft.Select the **Finish** button to send diagnostic information to Microsoft.</span><span class="sxs-lookup"><span data-stu-id="033c3-123">Select the **Finish** button to send diagnostic information to Microsoft.</span></span>

   ![Impossibile risolvere il problema](media/application-not-started/repair-tool-no-resolution.png)

1. <span data-ttu-id="033c3-125">Se non è ancora possibile eseguire l'applicazione, installare la versione più recente di .NET Framework supportata dalla versione di Windows in uso, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="033c3-125">If you still cannot run the application, install the latest version of the .NET Framework supported by your version of Windows, as shown in the following table.</span></span>

   |<span data-ttu-id="033c3-126">Versione di Windows</span><span class="sxs-lookup"><span data-stu-id="033c3-126">Windows version</span></span>|<span data-ttu-id="033c3-127">Installazione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="033c3-127">.NET Framework installation</span></span>|
   |---|---|
   |<span data-ttu-id="033c3-128">Aggiornamento dell'anniversario di Windows 10 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="033c3-128">Windows 10 Anniversary Update and later versions</span></span>|[<span data-ttu-id="033c3-129">Runtime di .NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="033c3-129">.NET Framework 4.8 Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |<span data-ttu-id="033c3-130">Windows 10, Windows 10 Novembre Aggiornamento</span><span class="sxs-lookup"><span data-stu-id="033c3-130">Windows 10, Windows 10 November Update</span></span>|[<span data-ttu-id="033c3-131">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="033c3-131">.NET Framework 4.6.2</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net462)|
   |<span data-ttu-id="033c3-132">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="033c3-132">Windows 8.1</span></span>|[<span data-ttu-id="033c3-133">Runtime di .NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="033c3-133">.NET Framework 4.8 Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |<span data-ttu-id="033c3-134">Windows 8</span><span class="sxs-lookup"><span data-stu-id="033c3-134">Windows 8</span></span>|[<span data-ttu-id="033c3-135">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="033c3-135">.NET Framework 4.6.1</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net461)|
   |<span data-ttu-id="033c3-136">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="033c3-136">Windows 7 SP1</span></span>|[<span data-ttu-id="033c3-137">Runtime di .NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="033c3-137">.NET Framework 4.8 Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |<span data-ttu-id="033c3-138">Windows Vista SP2</span><span class="sxs-lookup"><span data-stu-id="033c3-138">Windows Vista SP2</span></span>|[<span data-ttu-id="033c3-139">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="033c3-139">.NET Framework 4.6</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net46)|

   > [!NOTE]
   > <span data-ttu-id="033c3-140">.NET Framework 4.8 è preinstallato su Windows 10 maggio 2019 aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="033c3-140">.NET Framework 4.8 is preinstalled on Windows 10 May 2019 Update.</span></span>

1. <span data-ttu-id="033c3-141">Tentare di avviare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="033c3-141">Attempt to launch the application.</span></span>

1. <span data-ttu-id="033c3-142">In alcuni casi, è possibile che venga visualizzata una finestra di dialogo simile alla seguente, che richiede di installare .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="033c3-142">In some cases, you may see a dialog box like the following, which asks you to install the .NET Framework 3.5.</span></span> <span data-ttu-id="033c3-143">Selezionare **Scarica e installa questa funzionalità** per installare .NET Framework 3.5, quindi avviare nuovamente l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="033c3-143">Select **Download and install this feature** to install the .NET Framework 3.5, then launch the application again.</span></span>

   ![Impossibile risolvere il problema](media/application-not-started/install-3-5.png)

## <a name="see-also"></a><span data-ttu-id="033c3-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="033c3-145">See also</span></span>

- [<span data-ttu-id="033c3-146">Requisiti di sistema di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="033c3-146">.NET Framework System Requirements</span></span>](../get-started/system-requirements.md)
- [<span data-ttu-id="033c3-147">Guida all'installazione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="033c3-147">.NET Framework installation guide</span></span>](index.md)
- [<span data-ttu-id="033c3-148">Risolvere i problemi relativi alle installazioni e alle disinstallazioni bloccate di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="033c3-148">Troubleshoot blocked .NET Framework installations and uninstallations</span></span>](troubleshoot-blocked-installations-and-uninstallations.md)
