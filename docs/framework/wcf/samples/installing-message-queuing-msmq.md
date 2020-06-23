---
title: Installazione accodamento messaggi (MSMQ)
description: Informazioni su come installare Accodamento messaggi 4,0 e Accodamento messaggi 3,0 da usare con gli esempi WFC come parte di una procedura di installazione singola.
ms.date: 03/30/2017
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
ms.openlocfilehash: 0d0cb87b40b1cb11eb7692c2fa1e890ec815b13d
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244465"
---
# <a name="installing-message-queuing-msmq"></a><span data-ttu-id="334cd-103">Installazione accodamento messaggi (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="334cd-103">Installing Message Queuing (MSMQ)</span></span>
<span data-ttu-id="334cd-104">Le procedure seguenti mostrano come installare Accodamento messaggi 4.0 e Accodamento messaggi 3.0.</span><span class="sxs-lookup"><span data-stu-id="334cd-104">The following procedures show how to install Message Queuing 4.0 and Message Queuing 3.0.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="334cd-105">Accodamento messaggi 4,0 non è disponibile in Windows XP e Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="334cd-105">Message Queuing 4.0 is not available in Windows XP and Windows Server 2003.</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-server-2008-or-windows-server-2008-r2"></a><span data-ttu-id="334cd-106">Per installare la versione 4.0 del sistema di accodamento dei messaggi in Windows Server 2008 o in Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="334cd-106">To install Message Queuing 4.0 on Windows Server 2008 or Windows Server 2008 R2</span></span>  
  
1. <span data-ttu-id="334cd-107">In Server Manager fare clic su **funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="334cd-107">In Server Manager, click **Features**.</span></span>  
  
2. <span data-ttu-id="334cd-108">Nel riquadro di destra in **Riepilogo funzionalità**fare clic su **Aggiungi funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="334cd-108">In the right-hand pane under **Features Summary**, click **Add Features**.</span></span>  
  
3. <span data-ttu-id="334cd-109">Nella finestra risultante espandere **Accodamento messaggi**.</span><span class="sxs-lookup"><span data-stu-id="334cd-109">In the resulting window, expand **Message Queuing**.</span></span>  
  
4. <span data-ttu-id="334cd-110">Espandere **Servizi Accodamento messaggi**.</span><span class="sxs-lookup"><span data-stu-id="334cd-110">Expand **Message Queuing Services**.</span></span>  
  
5. <span data-ttu-id="334cd-111">Fare clic su **integrazione servizi directory** (per i computer aggiunti a un dominio), quindi fare clic su **supporto http**.</span><span class="sxs-lookup"><span data-stu-id="334cd-111">Click **Directory Services Integration** (for computers joined to a Domain), then click **HTTP Support**.</span></span>  
  
6. <span data-ttu-id="334cd-112">Fare clic su **Avanti**, quindi su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="334cd-112">Click **Next**,then click **Install**.</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-7-or-windows-vista"></a><span data-ttu-id="334cd-113">Per installare la versione 4.0 del sistema di accodamento dei messaggi in Windows 7 o in windows Vista</span><span class="sxs-lookup"><span data-stu-id="334cd-113">To install Message Queuing 4.0 on Windows 7 or Windows Vista</span></span>  
  
1. <span data-ttu-id="334cd-114">Aprire il **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="334cd-114">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="334cd-115">Fare clic su **programmi** e quindi in **programmi e funzionalità**fare clic **su attivazione e disattivazione delle funzionalità Windows**.</span><span class="sxs-lookup"><span data-stu-id="334cd-115">Click **Programs** and then, under **Programs and Features**, click **Turn Windows Features on and off**.</span></span>  
  
3. <span data-ttu-id="334cd-116">Espandere il server di accodamento messaggi Microsoft (MSMQ), espandere il server di base di accodamento messaggi Microsoft (MSMQ) e quindi selezionare le caselle di controllo per l’installazione delle funzionalità di Accodamento messaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="334cd-116">Expand Microsoft Message Queue (MSMQ) Server, expand Microsoft Message Queue (MSMQ) Server Core, and then select the check boxes for the following Message Queuing features to install:</span></span>  
  
    - <span data-ttu-id="334cd-117">Integrazione dei Servizi di dominio Active Directory MSMQ (per computer aggiunti a un Dominio).</span><span class="sxs-lookup"><span data-stu-id="334cd-117">MSMQ Active Directory Domain Services Integration (for computers joined to a Domain).</span></span>  
  
    - <span data-ttu-id="334cd-118">Supporto HTTP MSMQ.</span><span class="sxs-lookup"><span data-stu-id="334cd-118">MSMQ HTTP Support.</span></span>  
  
4. <span data-ttu-id="334cd-119">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="334cd-119">Click **OK**.</span></span>  
  
5. <span data-ttu-id="334cd-120">Se viene richiesto di riavviare il computer, fare clic su **OK** per completare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="334cd-120">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
#### <a name="to-install-message-queuing-30-on-windows-xp-and-windows-server-2003"></a><span data-ttu-id="334cd-121">Per installare la versione 3.0 di Accodamento messaggi in Windows XP o Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="334cd-121">To install Message Queuing 3.0 on Windows XP and Windows Server 2003</span></span>  
  
1. <span data-ttu-id="334cd-122">Aprire il **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="334cd-122">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="334cd-123">Fare clic su **Aggiungi Rimuovi programmi** , quindi su **Aggiungi componenti di Windows**.</span><span class="sxs-lookup"><span data-stu-id="334cd-123">Click **Add Remove Programs** and then click **Add Windows Components**.</span></span>  
  
3. <span data-ttu-id="334cd-124">Selezionare Accodamento messaggi e fare clic su **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="334cd-124">Select Message Queuing and click **Details**.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="334cd-125">Se si esegue Windows Server 2003, selezionare Server applicazioni per accedere a Accodamento messaggi.</span><span class="sxs-lookup"><span data-stu-id="334cd-125">If you are running Windows Server 2003, select Application Server to access Message Queuing.</span></span>  
  
4. <span data-ttu-id="334cd-126">Assicurarsi che l'opzione Supporto HTTP MSMQ sia selezionata nella pagina dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="334cd-126">Ensure that the option MSMQ HTTP Support is selected on the details page.</span></span>  
  
5. <span data-ttu-id="334cd-127">Fare clic su **OK** per chiudere la pagina dei dettagli, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="334cd-127">Click **OK** to exit the details page, and then click **Next**.</span></span> <span data-ttu-id="334cd-128">Completare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="334cd-128">Complete the installation.</span></span>  
  
6. <span data-ttu-id="334cd-129">Se viene richiesto di riavviare il computer, fare clic su **OK** per completare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="334cd-129">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="334cd-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="334cd-130">See also</span></span>

- [<span data-ttu-id="334cd-131">Istruzioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="334cd-131">Set-Up Instructions</span></span>](set-up-instructions.md)
