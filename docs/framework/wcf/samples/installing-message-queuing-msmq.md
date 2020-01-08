---
title: Installazione accodamento messaggi (MSMQ)
ms.date: 03/30/2017
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
ms.openlocfilehash: e6d6a3a2e1bc0a0c936e4b8594eab836b559e5a7
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344742"
---
# <a name="installing-message-queuing-msmq"></a><span data-ttu-id="2c3e1-102">Installazione accodamento messaggi (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="2c3e1-102">Installing Message Queuing (MSMQ)</span></span>
<span data-ttu-id="2c3e1-103">Le procedure seguenti mostrano come installare Accodamento messaggi 4.0 e Accodamento messaggi 3.0.</span><span class="sxs-lookup"><span data-stu-id="2c3e1-103">The following procedures show how to install Message Queuing 4.0 and Message Queuing 3.0.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2c3e1-104">Accodamento messaggi 4,0 non è disponibile in [!INCLUDE[wxp](../../../../includes/wxp-md.md)] e Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="2c3e1-104">Message Queuing 4.0 is not available in [!INCLUDE[wxp](../../../../includes/wxp-md.md)] and Windows Server 2003.</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-server-2008-or-windows-server-2008-r2"></a><span data-ttu-id="2c3e1-105">Per installare la versione 4.0 del sistema di accodamento dei messaggi in Windows Server 2008 o in Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="2c3e1-105">To install Message Queuing 4.0 on Windows Server 2008 or Windows Server 2008 R2</span></span>  
  
1. <span data-ttu-id="2c3e1-106">In Server Manager fare clic su **funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="2c3e1-106">In Server Manager, click **Features**.</span></span>  
  
2. <span data-ttu-id="2c3e1-107">Nel riquadro di destra in **Riepilogo funzionalità**fare clic su **Aggiungi funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="2c3e1-107">In the right-hand pane under **Features Summary**, click **Add Features**.</span></span>  
  
3. <span data-ttu-id="2c3e1-108">Nella finestra risultante espandere **Accodamento messaggi**.</span><span class="sxs-lookup"><span data-stu-id="2c3e1-108">In the resulting window, expand **Message Queuing**.</span></span>  
  
4. <span data-ttu-id="2c3e1-109">Espandere **Servizi Accodamento messaggi**.</span><span class="sxs-lookup"><span data-stu-id="2c3e1-109">Expand **Message Queuing Services**.</span></span>  
  
5. <span data-ttu-id="2c3e1-110">Fare clic su **integrazione servizi directory** (per i computer aggiunti a un dominio), quindi fare clic su **supporto http**.</span><span class="sxs-lookup"><span data-stu-id="2c3e1-110">Click **Directory Services Integration** (for computers joined to a Domain), then click **HTTP Support**.</span></span>  
  
6. <span data-ttu-id="2c3e1-111">Fare clic su **Avanti**, quindi su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="2c3e1-111">Click **Next**,then click **Install**.</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-7-or-windows-vista"></a><span data-ttu-id="2c3e1-112">Per installare la versione 4.0 del sistema di accodamento dei messaggi in Windows 7 o in windows Vista</span><span class="sxs-lookup"><span data-stu-id="2c3e1-112">To install Message Queuing 4.0 on Windows 7 or Windows Vista</span></span>  
  
1. <span data-ttu-id="2c3e1-113">Aprire il **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="2c3e1-113">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="2c3e1-114">Fare clic su **programmi** e quindi in **programmi e funzionalità**fare clic **su attivazione e disattivazione delle funzionalità Windows**.</span><span class="sxs-lookup"><span data-stu-id="2c3e1-114">Click **Programs** and then, under **Programs and Features**, click **Turn Windows Features on and off**.</span></span>  
  
3. <span data-ttu-id="2c3e1-115">Espandere Microsoft Message Queue (MSMQ) Server, espandere Componenti di base di Microsoft Message Queue (MSMQ) Server, quindi selezionare le caselle di controllo per l'installazione delle funzionalità di Accodamento messaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c3e1-115">Expand Microsoft Message Queue (MSMQ) Server, expand Microsoft Message Queue (MSMQ) Server Core, and then select the check boxes for the following Message Queuing features to install:</span></span>  
  
    - <span data-ttu-id="2c3e1-116">Integrazione dei Servizi di dominio Active Directory MSMQ (per computer aggiunti a un Dominio).</span><span class="sxs-lookup"><span data-stu-id="2c3e1-116">MSMQ Active Directory Domain Services Integration (for computers joined to a Domain).</span></span>  
  
    - <span data-ttu-id="2c3e1-117">Supporto HTTP MSMQ.</span><span class="sxs-lookup"><span data-stu-id="2c3e1-117">MSMQ HTTP Support.</span></span>  
  
4. <span data-ttu-id="2c3e1-118">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c3e1-118">Click **OK**.</span></span>  
  
5. <span data-ttu-id="2c3e1-119">Se viene richiesto di riavviare il computer, fare clic su **OK** per completare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="2c3e1-119">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
#### <a name="to-install-message-queuing-30-on-windows-xp-and-windows-server-2003"></a><span data-ttu-id="2c3e1-120">Per installare la versione 3.0 di Accodamento messaggi in Windows XP o Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="2c3e1-120">To install Message Queuing 3.0 on Windows XP and Windows Server 2003</span></span>  
  
1. <span data-ttu-id="2c3e1-121">Aprire il **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="2c3e1-121">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="2c3e1-122">Fare clic su **Aggiungi Rimuovi programmi** , quindi su **Aggiungi componenti di Windows**.</span><span class="sxs-lookup"><span data-stu-id="2c3e1-122">Click **Add Remove Programs** and then click **Add Windows Components**.</span></span>  
  
3. <span data-ttu-id="2c3e1-123">Selezionare Accodamento messaggi e fare clic su **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="2c3e1-123">Select Message Queuing and click **Details**.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="2c3e1-124">Se si esegue Windows Server 2003, selezionare Server applicazioni per accedere a Accodamento messaggi.</span><span class="sxs-lookup"><span data-stu-id="2c3e1-124">If you are running Windows Server 2003, select Application Server to access Message Queuing.</span></span>  
  
4. <span data-ttu-id="2c3e1-125">Assicurarsi che l'opzione Supporto HTTP MSMQ sia selezionata nella pagina dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="2c3e1-125">Ensure that the option MSMQ HTTP Support is selected on the details page.</span></span>  
  
5. <span data-ttu-id="2c3e1-126">Fare clic su **OK** per chiudere la pagina dei dettagli, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2c3e1-126">Click **OK** to exit the details page, and then click **Next**.</span></span> <span data-ttu-id="2c3e1-127">Completare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="2c3e1-127">Complete the installation.</span></span>  
  
6. <span data-ttu-id="2c3e1-128">Se viene richiesto di riavviare il computer, fare clic su **OK** per completare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="2c3e1-128">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c3e1-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c3e1-129">See also</span></span>

- [<span data-ttu-id="2c3e1-130">Istruzioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="2c3e1-130">Set-Up Instructions</span></span>](../../../../docs/framework/wcf/samples/set-up-instructions.md)
