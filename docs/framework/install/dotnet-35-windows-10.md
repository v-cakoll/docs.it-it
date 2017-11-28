---
title: Installare .NET Framework 3.5 in Windows 10, Windows 8.1 e Windows 8
description: Informazioni sull'installazione di .NET Framework 3.5 in Windows 10, Windows 8.1 e Windows 8.
author: rlander
ms.author: mairaw
keywords: .NET Framework, Installare
ms.date: 05/26/2017
ms.topic: article
ms.prod: .net-framework
ms.technology: vs-ide-deployment
ms.devlang: dotnet
ms.assetid: 67cda1d5-c6g4-4eb5-93e6-4f478de07ff7
ms.openlocfilehash: 85a3cada074714c24015d90c26d94551f4f411f2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="install-the-net-framework-35-on-windows-10-windows-81-and-windows-8"></a><span data-ttu-id="71d56-104">Installare .NET Framework 3.5 in Windows 10, Windows 8.1 e Windows 8</span><span class="sxs-lookup"><span data-stu-id="71d56-104">Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8</span></span>

<span data-ttu-id="71d56-105">Può essere necessario avere .NET Framework 3.5 installato per eseguire determinate app in Windows 10, Windows 8.1 e Windows 8.</span><span class="sxs-lookup"><span data-stu-id="71d56-105">You may need the .NET Framework 3.5 to run an app on Windows 10, Windows 8.1, and Windows 8.</span></span> <span data-ttu-id="71d56-106">e si applicano anche alle versioni precedenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="71d56-106">You can also use these instructions for earlier Windows versions.</span></span>

## <a name="install-the-net-framework-35-on-demand"></a><span data-ttu-id="71d56-107">Installare .NET Framework 3.5 su richiesta</span><span class="sxs-lookup"><span data-stu-id="71d56-107">Install the .NET Framework 3.5 on Demand</span></span>

<span data-ttu-id="71d56-108">Se si prova a eseguire un'app che richiede .NET Framework 3.5 può essere visualizzata la finestra di dialogo di configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="71d56-108">You may see the following configuration dialog if you try to run an app that requires the .NET Framework 3.5.</span></span> <span data-ttu-id="71d56-109">Scegliere **Installa la funzionalità** per abilitare .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="71d56-109">Choose **Install this feature** to enable the .NET Framework 3.5.</span></span> <span data-ttu-id="71d56-110">Per questa opzione è necessaria una connessione Internet.</span><span class="sxs-lookup"><span data-stu-id="71d56-110">This option requires an Internet connection.</span></span>

![Finestra di dialogo di installazione di .NET Framework](./media/dotnet-framework-installation-dialog.jpg)

## <a name="enable-the-net-framework-35-in-control-panel"></a><span data-ttu-id="71d56-112">Abilitare .NET Framework 3.5 dal Pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="71d56-112">Enable the .NET Framework 3.5 in Control Panel</span></span>

<span data-ttu-id="71d56-113">.NET Framework 3.5 può essere abilitato dal Pannello di controllo di Windows.</span><span class="sxs-lookup"><span data-stu-id="71d56-113">You can enable the .NET Framework 3.5 through the Windows Control Panel.</span></span> <span data-ttu-id="71d56-114">Per questa opzione è necessaria una connessione Internet.</span><span class="sxs-lookup"><span data-stu-id="71d56-114">This option requires an Internet connection.</span></span>

1. <span data-ttu-id="71d56-115">Premere il tasto Windows ![Logo Windows](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg) sulla tastiera, digitare "Funzionalità Windows" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="71d56-115">Press the Windows key Windows ![Windows logo](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg) on your keyboard, type "Windows Features", and press Enter.</span></span> <span data-ttu-id="71d56-116">Viene visualizzata la finestra di dialogo **Attivazione o disattivazione delle funzionalità Windows**.</span><span class="sxs-lookup"><span data-stu-id="71d56-116">The **Turn Windows features on or off** dialog box appears.</span></span>

2. <span data-ttu-id="71d56-117">Selezionare la casella di controllo **.NET Framework 3.5 (include .NET 2.0 e 3.0)**, selezionare **OK** e riavviare il computer, se richiesto.</span><span class="sxs-lookup"><span data-stu-id="71d56-117">Select the **.NET Framework 3.5 (includes .NET 2.0 and 3.0)** check box, select **OK**, and reboot your computer if prompted.</span></span>

   ![Installazione di .NET tramite il Pannello di controllo](./media/dotnet-control-panel.png)

   <span data-ttu-id="71d56-119">Non è necessario selezionare gli elementi figlio per l'**attivazione HTTP di Windows Communication Foundation (WCF)** e per l'**attivazione non HTTP di Windows Communication Foundation (WCF)**, a meno che, in qualità di sviluppatore o amministratore del server, non si richieda questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="71d56-119">You don't need to select the child items for **Windows Communication Foundation (WCF) HTTP Activation** and **Windows Communication Foundation (WCF) Non-HTTP Activation** unless you're a developer or server administrator who requires this functionality.</span></span>
