---
title: Installare .NET Framework 3.5 in Windows 10, Windows 8.1 e Windows 8
description: Informazioni sull'installazione di .NET Framework 3.5 in Windows 10, Windows 8.1 e Windows 8.
author: rlander
ms.author: mairaw
ms.date: 11/27/2017
ms.topic: article
ms.prod: .net-framework
ms.workload:
- dotnet
ms.openlocfilehash: e81008eca3019860789db548d40998a7a7565d31
ms.sourcegitcommit: cec0525b2121c36198379525e69aa5388266db5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2018
---
# <a name="install-the-net-framework-35-on-windows-10-windows-81-and-windows-8"></a><span data-ttu-id="14ddc-103">Installare .NET Framework 3.5 in Windows 10, Windows 8.1 e Windows 8</span><span class="sxs-lookup"><span data-stu-id="14ddc-103">Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8</span></span>

<span data-ttu-id="14ddc-104">Può essere necessario avere .NET Framework 3.5 installato per eseguire determinate app in Windows 10, Windows 8.1 e Windows 8.</span><span class="sxs-lookup"><span data-stu-id="14ddc-104">You may need the .NET Framework 3.5 to run an app on Windows 10, Windows 8.1, and Windows 8.</span></span> <span data-ttu-id="14ddc-105">e si applicano anche alle versioni precedenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="14ddc-105">You can also use these instructions for earlier Windows versions.</span></span>

## <a name="install-the-net-framework-35-on-demand"></a><span data-ttu-id="14ddc-106">Installare .NET Framework 3.5 su richiesta</span><span class="sxs-lookup"><span data-stu-id="14ddc-106">Install the .NET Framework 3.5 on Demand</span></span>

<span data-ttu-id="14ddc-107">Se si prova a eseguire un'app che richiede .NET Framework 3.5 può essere visualizzata la finestra di dialogo di configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="14ddc-107">You may see the following configuration dialog if you try to run an app that requires the .NET Framework 3.5.</span></span> <span data-ttu-id="14ddc-108">Scegliere **Installa la funzionalità** per abilitare .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="14ddc-108">Choose **Install this feature** to enable the .NET Framework 3.5.</span></span> <span data-ttu-id="14ddc-109">Per questa opzione è necessaria una connessione Internet.</span><span class="sxs-lookup"><span data-stu-id="14ddc-109">This option requires an Internet connection.</span></span>

![Finestra di dialogo di installazione di .NET Framework](./media/dotnet-framework-installation-dialog.jpg)

## <a name="enable-the-net-framework-35-in-control-panel"></a><span data-ttu-id="14ddc-111">Abilitare .NET Framework 3.5 dal Pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="14ddc-111">Enable the .NET Framework 3.5 in Control Panel</span></span>

<span data-ttu-id="14ddc-112">.NET Framework 3.5 può essere abilitato dal Pannello di controllo di Windows.</span><span class="sxs-lookup"><span data-stu-id="14ddc-112">You can enable the .NET Framework 3.5 through the Windows Control Panel.</span></span> <span data-ttu-id="14ddc-113">Per questa opzione è necessaria una connessione Internet.</span><span class="sxs-lookup"><span data-stu-id="14ddc-113">This option requires an Internet connection.</span></span>

1. <span data-ttu-id="14ddc-114">Premere il tasto Windows ![Logo Windows](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg) sulla tastiera, digitare "Funzionalità Windows" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="14ddc-114">Press the Windows key Windows ![Windows logo](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg) on your keyboard, type "Windows Features", and press Enter.</span></span> <span data-ttu-id="14ddc-115">Viene visualizzata la finestra di dialogo **Attivazione o disattivazione delle funzionalità Windows**.</span><span class="sxs-lookup"><span data-stu-id="14ddc-115">The **Turn Windows features on or off** dialog box appears.</span></span>

2. <span data-ttu-id="14ddc-116">Selezionare la casella di controllo **.NET Framework 3.5 (include .NET 2.0 e 3.0)**, selezionare **OK** e riavviare il computer, se richiesto.</span><span class="sxs-lookup"><span data-stu-id="14ddc-116">Select the **.NET Framework 3.5 (includes .NET 2.0 and 3.0)** check box, select **OK**, and reboot your computer if prompted.</span></span>

   ![Installazione di .NET tramite il Pannello di controllo](./media/dotnet-control-panel.png)

   <span data-ttu-id="14ddc-118">Non è necessario selezionare gli elementi figlio per l'**attivazione HTTP di Windows Communication Foundation (WCF)** e per l'**attivazione non HTTP di Windows Communication Foundation (WCF)**, a meno che, in qualità di sviluppatore o amministratore del server, non si richieda questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="14ddc-118">You don't need to select the child items for **Windows Communication Foundation (WCF) HTTP Activation** and **Windows Communication Foundation (WCF) Non-HTTP Activation** unless you're a developer or server administrator who requires this functionality.</span></span>

## <a name="troubleshoot-the-installation-of-the-net-framework-35"></a><span data-ttu-id="14ddc-119">Risolvere i problemi relativi all'installazione di .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="14ddc-119">Troubleshoot the installation of the .NET Framework 3.5</span></span>

<span data-ttu-id="14ddc-120">Durante l'installazione può verificarsi un errore 0x800f0906, 0x800f0907, 0x800f081f o 0x800F0922. In tal caso, vedere [Errore di installazione di .NET Framework 3.5: 0x800f0906, 0x800f0907 o 0x800f081f](https://support.microsoft.com/help/2734782/net-framework-3-5-installation-error-0x800f0906--0x800f081f--0x800f09) per informazioni su come risolvere questi problemi.</span><span class="sxs-lookup"><span data-stu-id="14ddc-120">During installation, you may encounter error 0x800f0906, 0x800f0907, 0x800f081f, or 0x800F0922, in which case refer to [.NET Framework 3.5 installation error: 0x800f0906, 0x800f0907, or 0x800f081f](https://support.microsoft.com/help/2734782/net-framework-3-5-installation-error-0x800f0906--0x800f081f--0x800f09) to see how to resolve these issues.</span></span>

<span data-ttu-id="14ddc-121">Se uno dei metodi illustrati nell'articolo precedente non riesce o non è presente una connessione Internet, è necessario usare il supporto di installazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="14ddc-121">If any of the methods discussed in the previous article fail or if you don't have an Internet connection, it's necessary to use your Windows installation media.</span></span> <span data-ttu-id="14ddc-122">Per altre informazioni, vedere [Deploy .NET Framework 3.5 by using Deployment Image Servicing and Management (DISM)](/windows-hardware/manufacture/desktop/deploy-net-framework-35-by-using-deployment-image-servicing-and-management--dism) (Distribuire .NET Framework 3.5 usando Gestione e manutenzione immagini distribuzione).</span><span class="sxs-lookup"><span data-stu-id="14ddc-122">For more information, see [Deploy .NET Framework 3.5 by using Deployment Image Servicing and Management (DISM)](/windows-hardware/manufacture/desktop/deploy-net-framework-35-by-using-deployment-image-servicing-and-management--dism).</span></span> <span data-ttu-id="14ddc-123">Se il supporto di installazione non è disponibile, vedere [Creare supporti di installazione per Windows](https://support.microsoft.com/help/15088/windows-create-installation-media).</span><span class="sxs-lookup"><span data-stu-id="14ddc-123">If you don't have the installation media, see [Create installation media for Windows](https://support.microsoft.com/help/15088/windows-create-installation-media).</span></span>
