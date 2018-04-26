---
title: Installare .NET Framework 3.5 in Windows 10, Windows 8.1 e Windows 8
description: Informazioni sull'installazione di .NET Framework 3.5 in Windows 10, Windows 8.1 e Windows 8.
author: rlander
ms.author: mairaw
ms.date: 03/30/2018
ms.topic: article
ms.prod: .net-framework
ms.workload:
- dotnet
ms.openlocfilehash: 09c4f81da76bb6608c3e579c442cf686ffab1688
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2018
---
# <a name="install-the-net-framework-35-on-windows-10-windows-81-and-windows-8"></a><span data-ttu-id="0718c-103">Installare .NET Framework 3.5 in Windows 10, Windows 8.1 e Windows 8</span><span class="sxs-lookup"><span data-stu-id="0718c-103">Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8</span></span>

<span data-ttu-id="0718c-104">Può essere necessario avere .NET Framework 3.5 installato per eseguire determinate app in Windows 10, Windows 8.1 e Windows 8.</span><span class="sxs-lookup"><span data-stu-id="0718c-104">You may need the .NET Framework 3.5 to run an app on Windows 10, Windows 8.1, and Windows 8.</span></span> <span data-ttu-id="0718c-105">e si applicano anche alle versioni precedenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="0718c-105">You can also use these instructions for earlier Windows versions.</span></span>

## <a name="install-the-net-framework-35-on-demand"></a><span data-ttu-id="0718c-106">Installare .NET Framework 3.5 su richiesta</span><span class="sxs-lookup"><span data-stu-id="0718c-106">Install the .NET Framework 3.5 on Demand</span></span>

<span data-ttu-id="0718c-107">Se si prova a eseguire un'app che richiede .NET Framework 3.5 può essere visualizzata la finestra di dialogo di configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="0718c-107">You may see the following configuration dialog if you try to run an app that requires the .NET Framework 3.5.</span></span> <span data-ttu-id="0718c-108">Scegliere **Installa la funzionalità** per abilitare .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="0718c-108">Choose **Install this feature** to enable the .NET Framework 3.5.</span></span> <span data-ttu-id="0718c-109">Per questa opzione è necessaria una connessione Internet.</span><span class="sxs-lookup"><span data-stu-id="0718c-109">This option requires an Internet connection.</span></span>

![Finestra di dialogo di installazione di .NET Framework](./media/dotnet-framework-installation-dialog.jpg)

### <a name="why-am-i-getting-this-pop-up"></a><span data-ttu-id="0718c-111">Perché viene visualizzato questo popup?</span><span class="sxs-lookup"><span data-stu-id="0718c-111">Why am I getting this pop-up?</span></span>

<span data-ttu-id="0718c-112">.NET Framework è creato da Microsoft e offre un ambiente per l'esecuzione di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="0718c-112">The .NET Framework is created by Microsoft and provides an environment for running applications.</span></span> <span data-ttu-id="0718c-113">Sono disponibili diverse versioni.</span><span class="sxs-lookup"><span data-stu-id="0718c-113">There are different versions available.</span></span> <span data-ttu-id="0718c-114">Molte società sviluppano app da eseguire con .NET Framework e queste app sono destinate a una versione specifica.</span><span class="sxs-lookup"><span data-stu-id="0718c-114">Many companies develop their apps to run using the .NET Framework, and these apps target a specific version.</span></span> <span data-ttu-id="0718c-115">Se viene visualizzato questo popup, si sta tentando di eseguire un'applicazione che richiede .NET Framework versione 3.5, ma tale versione non è installata nel sistema in uso.</span><span class="sxs-lookup"><span data-stu-id="0718c-115">If you see this pop-up, you're trying to run an application that requires the .NET Framework version 3.5, but that version is not installed on your system.</span></span>

## <a name="enable-the-net-framework-35-in-control-panel"></a><span data-ttu-id="0718c-116">Abilitare .NET Framework 3.5 dal Pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="0718c-116">Enable the .NET Framework 3.5 in Control Panel</span></span>

<span data-ttu-id="0718c-117">.NET Framework 3.5 può essere abilitato dal Pannello di controllo di Windows.</span><span class="sxs-lookup"><span data-stu-id="0718c-117">You can enable the .NET Framework 3.5 through the Windows Control Panel.</span></span> <span data-ttu-id="0718c-118">Per questa opzione è necessaria una connessione Internet.</span><span class="sxs-lookup"><span data-stu-id="0718c-118">This option requires an Internet connection.</span></span>

1. <span data-ttu-id="0718c-119">Premere il tasto Windows ![Logo Windows](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg) sulla tastiera, digitare "Funzionalità Windows" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="0718c-119">Press the Windows key Windows ![Windows logo](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg) on your keyboard, type "Windows Features", and press Enter.</span></span> <span data-ttu-id="0718c-120">Viene visualizzata la finestra di dialogo **Attivazione o disattivazione delle funzionalità Windows**.</span><span class="sxs-lookup"><span data-stu-id="0718c-120">The **Turn Windows features on or off** dialog box appears.</span></span>

2. <span data-ttu-id="0718c-121">Selezionare la casella di controllo **.NET Framework 3.5 (include .NET 2.0 e 3.0)**, selezionare **OK** e riavviare il computer, se richiesto.</span><span class="sxs-lookup"><span data-stu-id="0718c-121">Select the **.NET Framework 3.5 (includes .NET 2.0 and 3.0)** check box, select **OK**, and reboot your computer if prompted.</span></span>

   ![Installazione di .NET tramite il Pannello di controllo](./media/dotnet-control-panel.png)

   <span data-ttu-id="0718c-123">Non è necessario selezionare gli elementi figlio per l'**attivazione HTTP di Windows Communication Foundation (WCF)** e per l'**attivazione non HTTP di Windows Communication Foundation (WCF)**, a meno che, in qualità di sviluppatore o amministratore del server, non si richieda questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="0718c-123">You don't need to select the child items for **Windows Communication Foundation (WCF) HTTP Activation** and **Windows Communication Foundation (WCF) Non-HTTP Activation** unless you're a developer or server administrator who requires this functionality.</span></span>

## <a name="troubleshoot-the-installation-of-the-net-framework-35"></a><span data-ttu-id="0718c-124">Risolvere i problemi relativi all'installazione di .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="0718c-124">Troubleshoot the installation of the .NET Framework 3.5</span></span>

<span data-ttu-id="0718c-125">Durante l'installazione può verificarsi un errore 0x800f0906, 0x800f0907, 0x800f081f o 0x800F0922. In tal caso, vedere [Errore di installazione di .NET Framework 3.5: 0x800f0906, 0x800f0907 o 0x800f081f](https://support.microsoft.com/help/2734782/net-framework-3-5-installation-error-0x800f0906--0x800f081f--0x800f09) per informazioni su come risolvere questi problemi.</span><span class="sxs-lookup"><span data-stu-id="0718c-125">During installation, you may encounter error 0x800f0906, 0x800f0907, 0x800f081f, or 0x800F0922, in which case refer to [.NET Framework 3.5 installation error: 0x800f0906, 0x800f0907, or 0x800f081f](https://support.microsoft.com/help/2734782/net-framework-3-5-installation-error-0x800f0906--0x800f081f--0x800f09) to see how to resolve these issues.</span></span>

<span data-ttu-id="0718c-126">Se il problema di installazione persiste o se non è disponibile una connessione a Internet, è possibile tentare l'installazione usando il supporto di installazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="0718c-126">If you still can't resolve your installation issue or you don't have an Internet connection, you can try installing it using your Windows installation media.</span></span> <span data-ttu-id="0718c-127">Per altre informazioni, vedere [Deploy .NET Framework 3.5 by using Deployment Image Servicing and Management (DISM)](/windows-hardware/manufacture/desktop/deploy-net-framework-35-by-using-deployment-image-servicing-and-management--dism) (Distribuire .NET Framework 3.5 usando Gestione e manutenzione immagini distribuzione).</span><span class="sxs-lookup"><span data-stu-id="0718c-127">For more information, see [Deploy .NET Framework 3.5 by using Deployment Image Servicing and Management (DISM)](/windows-hardware/manufacture/desktop/deploy-net-framework-35-by-using-deployment-image-servicing-and-management--dism).</span></span> <span data-ttu-id="0718c-128">Se il supporto di installazione non è disponibile, vedere [Creare supporti di installazione per Windows](https://support.microsoft.com/help/15088/windows-create-installation-media).</span><span class="sxs-lookup"><span data-stu-id="0718c-128">If you don't have the installation media, see [Create installation media for Windows](https://support.microsoft.com/help/15088/windows-create-installation-media).</span></span>
