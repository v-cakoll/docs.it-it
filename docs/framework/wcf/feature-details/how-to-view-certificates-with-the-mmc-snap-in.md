---
title: 'Procedura: visualizzare certificati con lo snap-in MMC'
description: Un client o un servizio WCF sicuro può utilizzare un certificato come credenziale. Informazioni sui tipi di archivi certificati che è possibile esaminare tramite il plug-in MMC.
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: e63034e48ae836f67f89b454829f7196c94610cd
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246675"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a><span data-ttu-id="64385-104">Procedura: visualizzare certificati con lo snap-in MMC</span><span class="sxs-lookup"><span data-stu-id="64385-104">How to: View certificates with the MMC snap-in</span></span>
<span data-ttu-id="64385-105">Quando si crea un client o un servizio protetto, è possibile usare un [certificato](working-with-certificates.md) come credenziale.</span><span class="sxs-lookup"><span data-stu-id="64385-105">When you create a secure client or service, you can use a [certificate](working-with-certificates.md) as the credential.</span></span> <span data-ttu-id="64385-106">Ad esempio, un tipo comune di credenziale è il certificato X. 509, creato con il <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="64385-106">For example, a common type of credential is the X.509 certificate, which you create with the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="64385-107">Sono disponibili tre diversi tipi di archivi certificati che è possibile esaminare con Microsoft Management Console (MMC) nei sistemi Windows:</span><span class="sxs-lookup"><span data-stu-id="64385-107">There are three different types of certificate stores that you can examine with the Microsoft Management Console (MMC) on Windows systems:</span></span>

- <span data-ttu-id="64385-108">Computer locale: l'archivio è locale per il dispositivo e globale per tutti gli utenti del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="64385-108">Local computer: The store is local to the device and global to all users on the device.</span></span>

- <span data-ttu-id="64385-109">Utente corrente: l'archivio è locale per l'account utente corrente nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="64385-109">Current user: The store is local to the current user account on the device.</span></span>

- <span data-ttu-id="64385-110">Account del servizio: l'archivio è locale per un servizio specifico nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="64385-110">Service account: The store is local to a particular service on the device.</span></span>

## <a name="view-certificates-in-the-mmc-snap-in"></a><span data-ttu-id="64385-111">Visualizzare i certificati nello snap-in MMC</span><span class="sxs-lookup"><span data-stu-id="64385-111">View certificates in the MMC snap-in</span></span>

<span data-ttu-id="64385-112">La procedura seguente illustra come esaminare gli archivi sul dispositivo locale per trovare un certificato appropriato:</span><span class="sxs-lookup"><span data-stu-id="64385-112">The following procedure demonstrates how to examine the stores on your local device to find an appropriate certificate:</span></span>
  
1. <span data-ttu-id="64385-113">Selezionare **Esegui** dal menu **Start** , quindi immettere *MMC*.</span><span class="sxs-lookup"><span data-stu-id="64385-113">Select **Run** from the **Start** menu, and then enter *mmc*.</span></span>

    <span data-ttu-id="64385-114">Viene visualizzata la console MMC.</span><span class="sxs-lookup"><span data-stu-id="64385-114">The MMC appears.</span></span>
  
2. <span data-ttu-id="64385-115">Scegliere **Aggiungi/Rimuovi snap-in**dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="64385-115">From the **File** menu, select **Add/Remove Snap In**.</span></span>

    <span data-ttu-id="64385-116">Verrà visualizzata la finestra **Aggiungi o Rimuovi snap-** in.</span><span class="sxs-lookup"><span data-stu-id="64385-116">The **Add or Remove Snap-ins** window appears.</span></span>
  
3. <span data-ttu-id="64385-117">Dall'elenco **snap-in disponibili** scegliere **certificati**, quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="64385-117">From the **Available snap-ins** list, choose **Certificates**, then select **Add**.</span></span>  

    ![Aggiungi snap-in certificati](./media/mmc-add-certificate-snap-in.png)
  
4. <span data-ttu-id="64385-119">Nella finestra **snap-in certificati** selezionare **account computer**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="64385-119">In the **Certificates snap-in** window, select **Computer account**, and then select **Next**.</span></span>
  
    <span data-ttu-id="64385-120">Facoltativamente, è possibile selezionare l' **account utente** per l'account utente o del **servizio** corrente per un servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="64385-120">Optionally, you can select **My user account** for the current user or **Service account** for a particular service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="64385-121">Se non si è un amministratore del dispositivo, è possibile gestire i certificati solo per l'account utente.</span><span class="sxs-lookup"><span data-stu-id="64385-121">If you're not an administrator for your device, you can manage certificates only for your user account.</span></span>
  
5. <span data-ttu-id="64385-122">Nella finestra **Seleziona computer** lasciare selezionata l'opzione **computer locale** e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="64385-122">In the **Select Computer** window, leave **Local computer** selected, and then select **Finish**.</span></span>  
  
6. <span data-ttu-id="64385-123">Nella finestra **Aggiungi o Rimuovi snap-in** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="64385-123">In the **Add or Remove Snap-in** window, select **OK**.</span></span>  
  
    ![Aggiungi snap-in certificati](./media/mmc-certificate-snap-in-selected.png)

7. <span data-ttu-id="64385-125">Facoltativo: dal menu **file** selezionare **Salva** o Salva con **nome** per salvare il file della console MMC per un uso successivo.</span><span class="sxs-lookup"><span data-stu-id="64385-125">Optional: From the **File** menu, select **Save** or **Save As** to save the MMC console file for later use.</span></span>  

8. <span data-ttu-id="64385-126">Per visualizzare i certificati nello snap-in MMC, selezionare **radice console** nel riquadro sinistro, quindi espandere **certificati (computer locale)**.</span><span class="sxs-lookup"><span data-stu-id="64385-126">To view your certificates in the MMC snap-in, select **Console Root** in the left pane, then expand **Certificates (Local Computer)**.</span></span>

    <span data-ttu-id="64385-127">Viene visualizzato un elenco di directory per ogni tipo di certificato.</span><span class="sxs-lookup"><span data-stu-id="64385-127">A list of directories for each type of certificate appears.</span></span> <span data-ttu-id="64385-128">Da ogni directory dei certificati è possibile visualizzare, esportare, importare ed eliminare i relativi certificati.</span><span class="sxs-lookup"><span data-stu-id="64385-128">From each certificate directory, you can view, export, import, and delete its certificates.</span></span>

## <a name="view-certificates-with-the-certificate-manager-tool"></a><span data-ttu-id="64385-129">Visualizzare i certificati con lo strumento Gestione certificati</span><span class="sxs-lookup"><span data-stu-id="64385-129">View certificates with the Certificate Manager tool</span></span>

<span data-ttu-id="64385-130">È inoltre possibile visualizzare, esportare, importare ed eliminare certificati utilizzando lo strumento Gestione certificati.</span><span class="sxs-lookup"><span data-stu-id="64385-130">You can also view, export, import, and delete certificates by using the Certificate Manager tool.</span></span>

### <a name="to-view-certificates-for-the-local-device"></a><span data-ttu-id="64385-131">Per visualizzare i certificati per il dispositivo locale</span><span class="sxs-lookup"><span data-stu-id="64385-131">To view certificates for the local device</span></span>

1. <span data-ttu-id="64385-132">Selezionare **Esegui** dal menu **Start** , quindi immettere *certlm. msc*.</span><span class="sxs-lookup"><span data-stu-id="64385-132">Select **Run** from the **Start** menu, and then enter *certlm.msc*.</span></span>

    <span data-ttu-id="64385-133">Viene visualizzato lo strumento Gestione certificati per il dispositivo locale.</span><span class="sxs-lookup"><span data-stu-id="64385-133">The Certificate Manager tool for the local device appears.</span></span>
  
2. <span data-ttu-id="64385-134">Per visualizzare i certificati, in **certificati-computer locale** nel riquadro sinistro, espandere la directory per il tipo di certificato che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="64385-134">To view your certificates, under **Certificates - Local Computer** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

### <a name="to-view-certificates-for-the-current-user"></a><span data-ttu-id="64385-135">Per visualizzare i certificati per l'utente corrente</span><span class="sxs-lookup"><span data-stu-id="64385-135">To view certificates for the current user</span></span>

1. <span data-ttu-id="64385-136">Selezionare **Esegui** dal menu **Start** , quindi immettere *certmgr. msc*.</span><span class="sxs-lookup"><span data-stu-id="64385-136">Select **Run** from the **Start** menu, and then enter *certmgr.msc*.</span></span>

    <span data-ttu-id="64385-137">Viene visualizzato lo strumento Gestione certificati per l'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="64385-137">The Certificate Manager tool for the current user appears.</span></span>
  
2. <span data-ttu-id="64385-138">Per visualizzare i certificati, in **certificati-utente corrente** nel riquadro sinistro, espandere la directory per il tipo di certificato che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="64385-138">To view your certificates, under **Certificates - Current User** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

## <a name="see-also"></a><span data-ttu-id="64385-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64385-139">See also</span></span>

- [<span data-ttu-id="64385-140">Utilizzo dei certificati</span><span class="sxs-lookup"><span data-stu-id="64385-140">Working with certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="64385-141">Procedura: creare certificati temporanei da usare durante lo sviluppo</span><span class="sxs-lookup"><span data-stu-id="64385-141">How to: Create temporary certificates for use during development</span></span>](how-to-create-temporary-certificates-for-use-during-development.md)
- [<span data-ttu-id="64385-142">Procedura: recuperare l'identificazione personale di un certificato</span><span class="sxs-lookup"><span data-stu-id="64385-142">How to: Retrieve the thumbprint of a certificate</span></span>](how-to-retrieve-the-thumbprint-of-a-certificate.md)
