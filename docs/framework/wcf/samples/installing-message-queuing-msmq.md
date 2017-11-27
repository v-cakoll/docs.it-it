---
title: Installazione accodamento messaggi (MSMQ)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 89d81a25da6494fc9cbf041ae68f2985b5c90a81
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="installing-message-queuing-msmq"></a><span data-ttu-id="a4801-102">Installazione accodamento messaggi (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="a4801-102">Installing Message Queuing (MSMQ)</span></span>
<span data-ttu-id="a4801-103">Le procedure seguenti mostrano come installare Accodamento messaggi 4.0 e Accodamento messaggi 3.0.</span><span class="sxs-lookup"><span data-stu-id="a4801-103">The following procedures show how to install Message Queuing 4.0 and Message Queuing 3.0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4801-104">La versione 4.0 del sistema di accodamento dei messaggi non è disponibile in [!INCLUDE[wxp](../../../../includes/wxp-md.md)] e [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4801-104">Message Queuing 4.0 is not available in [!INCLUDE[wxp](../../../../includes/wxp-md.md)] and [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-server-2008-or-windows-server-2008-r2"></a><span data-ttu-id="a4801-105">Per installare la versione 4.0 del sistema di accodamento dei messaggi in Windows Server 2008 o in Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="a4801-105">To install Message Queuing 4.0 on Windows Server 2008 or Windows Server 2008 R2</span></span>  
  
1.  <span data-ttu-id="a4801-106">In Server Manager, fare clic su **funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="a4801-106">In Server Manager, click **Features**.</span></span>  
  
2.  <span data-ttu-id="a4801-107">Nel riquadro destro, in **Riepilogo funzionalità**, fare clic su **Aggiungi funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="a4801-107">In the right-hand pane under **Features Summary**, click **Add Features**.</span></span>  
  
3.  <span data-ttu-id="a4801-108">Nella finestra risulta, espandere **Accodamento**.</span><span class="sxs-lookup"><span data-stu-id="a4801-108">In the resulting window, expand **Message Queuing**.</span></span>  
  
4.  <span data-ttu-id="a4801-109">Espandere **servizi di accodamento dei messaggi**.</span><span class="sxs-lookup"><span data-stu-id="a4801-109">Expand **Message Queuing Services**.</span></span>  
  
5.  <span data-ttu-id="a4801-110">Fare clic su **integrazione servizi Directory** (per i computer aggiunti a un dominio), quindi fare clic su **supporto HTTP**.</span><span class="sxs-lookup"><span data-stu-id="a4801-110">Click **Directory Services Integration** (for computers joined to a Domain), then click **HTTP Support**.</span></span>  
  
6.  <span data-ttu-id="a4801-111">Fare clic su **Avanti**, quindi fare clic su **installare**.</span><span class="sxs-lookup"><span data-stu-id="a4801-111">Click **Next**,then click **Install**.</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-7-or-windows-vista"></a><span data-ttu-id="a4801-112">Per installare la versione 4.0 del sistema di accodamento dei messaggi in Windows 7 o in windows Vista</span><span class="sxs-lookup"><span data-stu-id="a4801-112">To install Message Queuing 4.0 on Windows 7 or Windows Vista</span></span>  
  
1.  <span data-ttu-id="a4801-113">Aprire il **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="a4801-113">Open **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="a4801-114">Fare clic su **programmi** e quindi in **programmi e funzionalità**, fare clic su **funzionalità di Windows di attivare e disattivare**.</span><span class="sxs-lookup"><span data-stu-id="a4801-114">Click **Programs** and then, under **Programs and Features**, click **Turn Windows Features on and off**.</span></span>  
  
3.  <span data-ttu-id="a4801-115">Espandere il server di accodamento messaggi Microsoft (MSMQ), espandere il server di base di accodamento messaggi Microsoft (MSMQ) e quindi selezionare le caselle di controllo per l’installazione delle funzionalità di Accodamento messaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a4801-115">Expand Microsoft Message Queue (MSMQ) Server, expand Microsoft Message Queue (MSMQ) Server Core, and then select the check boxes for the following Message Queuing features to install:</span></span>  
  
    -   <span data-ttu-id="a4801-116">Integrazione dei Servizi di dominio Active Directory MSMQ (per computer aggiunti a un Dominio).</span><span class="sxs-lookup"><span data-stu-id="a4801-116">MSMQ Active Directory Domain Services Integration (for computers joined to a Domain).</span></span>  
  
    -   <span data-ttu-id="a4801-117">Supporto HTTP MSMQ.</span><span class="sxs-lookup"><span data-stu-id="a4801-117">MSMQ HTTP Support.</span></span>  
  
4.  <span data-ttu-id="a4801-118">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a4801-118">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="a4801-119">Se viene chiesto di riavviare il computer, fare clic su **OK** per completare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="a4801-119">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
#### <a name="to-install-message-queuing-30-on-windows-xp-and-windows-server-2003"></a><span data-ttu-id="a4801-120">Per installare la versione 3.0 di Accodamento messaggi in Windows XP o Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="a4801-120">To install Message Queuing 3.0 on Windows XP and Windows Server 2003</span></span>  
  
1.  <span data-ttu-id="a4801-121">Aprire il **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="a4801-121">Open **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="a4801-122">Fare clic su **Installazione applicazioni** e quindi fare clic su **Installazione componenti di Windows**.</span><span class="sxs-lookup"><span data-stu-id="a4801-122">Click **Add Remove Programs** and then click **Add Windows Components**.</span></span>  
  
3.  <span data-ttu-id="a4801-123">Selezionare il servizio Accodamento messaggi e fare clic su **dettagli**.</span><span class="sxs-lookup"><span data-stu-id="a4801-123">Select Message Queuing and click **Details**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a4801-124">Se è in esecuzione [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], selezionare Server applicazioni per accedere a Accodamento messaggi.</span><span class="sxs-lookup"><span data-stu-id="a4801-124">If you are running [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], select Application Server to access Message Queuing.</span></span>  
  
4.  <span data-ttu-id="a4801-125">Assicurarsi che l'opzione Supporto HTTP MSMQ sia selezionata nella pagina dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="a4801-125">Ensure that the option MSMQ HTTP Support is selected on the details page.</span></span>  
  
5.  <span data-ttu-id="a4801-126">Fare clic su **OK** per uscire dalla pagina dei dettagli, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a4801-126">Click **OK** to exit the details page, and then click **Next**.</span></span> <span data-ttu-id="a4801-127">Completare l’installazione.</span><span class="sxs-lookup"><span data-stu-id="a4801-127">Complete the installation.</span></span>  
  
6.  <span data-ttu-id="a4801-128">Se viene chiesto di riavviare il computer, fare clic su **OK** per completare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="a4801-128">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4801-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4801-129">See Also</span></span>  
 [<span data-ttu-id="a4801-130">Istruzioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="a4801-130">Set-Up Instructions</span></span>](../../../../docs/framework/wcf/samples/set-up-instructions.md)
