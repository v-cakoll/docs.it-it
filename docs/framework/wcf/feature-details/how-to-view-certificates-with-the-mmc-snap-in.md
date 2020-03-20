---
title: 'Procedura: visualizzare i certificati con lo snap-in MMC'
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 35048c24e838c513909fae8bedcba287001f5cef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184775"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a><span data-ttu-id="ad4e9-102">Procedura: visualizzare i certificati con lo snap-in MMC</span><span class="sxs-lookup"><span data-stu-id="ad4e9-102">How to: View certificates with the MMC snap-in</span></span>
<span data-ttu-id="ad4e9-103">Quando si crea un client o un servizio sicuro, è possibile usare un [certificato](working-with-certificates.md) come credenziale.</span><span class="sxs-lookup"><span data-stu-id="ad4e9-103">When you create a secure client or service, you can use a [certificate](working-with-certificates.md) as the credential.</span></span> <span data-ttu-id="ad4e9-104">Ad esempio, un tipo comune di credenziale è il <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> certificato X.509, creato con il metodo .</span><span class="sxs-lookup"><span data-stu-id="ad4e9-104">For example, a common type of credential is the X.509 certificate, which you create with the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="ad4e9-105">Esistono tre diversi tipi di archivi certificati che è possibile esaminare con Microsoft Management Console (MMC) nei sistemi Windows:</span><span class="sxs-lookup"><span data-stu-id="ad4e9-105">There are three different types of certificate stores that you can examine with the Microsoft Management Console (MMC) on Windows systems:</span></span>

- <span data-ttu-id="ad4e9-106">Computer locale: l'archivio è locale per il dispositivo e globale per tutti gli utenti del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ad4e9-106">Local computer: The store is local to the device and global to all users on the device.</span></span>

- <span data-ttu-id="ad4e9-107">Utente corrente: l'archivio è locale all'account utente corrente nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ad4e9-107">Current user: The store is local to the current user account on the device.</span></span>

- <span data-ttu-id="ad4e9-108">Account del servizio: l'archivio è locale per un determinato servizio nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ad4e9-108">Service account: The store is local to a particular service on the device.</span></span>

## <a name="view-certificates-in-the-mmc-snap-in"></a><span data-ttu-id="ad4e9-109">Visualizzare i certificati nello snap-in MMC</span><span class="sxs-lookup"><span data-stu-id="ad4e9-109">View certificates in the MMC snap-in</span></span>

<span data-ttu-id="ad4e9-110">Nella procedura seguente viene illustrato come esaminare gli archivi nel dispositivo locale per trovare un certificato appropriato:</span><span class="sxs-lookup"><span data-stu-id="ad4e9-110">The following procedure demonstrates how to examine the stores on your local device to find an appropriate certificate:</span></span>
  
1. <span data-ttu-id="ad4e9-111">Selezionare **Esegui** dal menu **Start,** quindi immettere *mmc*.</span><span class="sxs-lookup"><span data-stu-id="ad4e9-111">Select **Run** from the **Start** menu, and then enter *mmc*.</span></span>

    <span data-ttu-id="ad4e9-112">Viene visualizzata la console MMC.</span><span class="sxs-lookup"><span data-stu-id="ad4e9-112">The MMC appears.</span></span>
  
2. <span data-ttu-id="ad4e9-113">Dal menu **File,** selezionare **Aggiungi/Rimuovi snap-in**.</span><span class="sxs-lookup"><span data-stu-id="ad4e9-113">From the **File** menu, select **Add/Remove Snap In**.</span></span>

    <span data-ttu-id="ad4e9-114">Viene visualizzata la finestra **Aggiungi o rimuovi snap-in.**</span><span class="sxs-lookup"><span data-stu-id="ad4e9-114">The **Add or Remove Snap-ins** window appears.</span></span>
  
3. <span data-ttu-id="ad4e9-115">Nell'elenco **Snap-in disponibili** scegliere **Certificati**, quindi **selezionare Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ad4e9-115">From the **Available snap-ins** list, choose **Certificates**, then select **Add**.</span></span>  

    ![Aggiungi snap-in certificati](./media/mmc-add-certificate-snap-in.png)
  
4. <span data-ttu-id="ad4e9-117">Nella finestra **dello snap-in Certificati** selezionare **Account computer**, quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ad4e9-117">In the **Certificates snap-in** window, select **Computer account**, and then select **Next**.</span></span>
  
    <span data-ttu-id="ad4e9-118">Facoltativamente, è possibile selezionare **Account utente** personale per l'utente corrente o Account **del servizio** per un determinato servizio.</span><span class="sxs-lookup"><span data-stu-id="ad4e9-118">Optionally, you can select **My user account** for the current user or **Service account** for a particular service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ad4e9-119">Se non sei un amministratore del tuo dispositivo, puoi gestire i certificati solo per il tuo account utente.</span><span class="sxs-lookup"><span data-stu-id="ad4e9-119">If you're not an administrator for your device, you can manage certificates only for your user account.</span></span>
  
5. <span data-ttu-id="ad4e9-120">Nella finestra **Seleziona computer** lasciare selezionata l'opzione **Computer locale** e quindi selezionare **Fine**.</span><span class="sxs-lookup"><span data-stu-id="ad4e9-120">In the **Select Computer** window, leave **Local computer** selected, and then select **Finish**.</span></span>  
  
6. <span data-ttu-id="ad4e9-121">Nella finestra **Aggiungi o rimuovi snap-in** selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="ad4e9-121">In the **Add or Remove Snap-in** window, select **OK**.</span></span>  
  
    ![Aggiungi snap-in certificati](./media/mmc-certificate-snap-in-selected.png)

7. <span data-ttu-id="ad4e9-123">Facoltativo: dal menu **File,** selezionare **Salva** o **Salva con nome** per salvare il file della console MMC per un utilizzo successivo.</span><span class="sxs-lookup"><span data-stu-id="ad4e9-123">Optional: From the **File** menu, select **Save** or **Save As** to save the MMC console file for later use.</span></span>  

8. <span data-ttu-id="ad4e9-124">Per visualizzare i certificati nello snap-in MMC, selezionare **Radice console** nel riquadro sinistro, quindi espandere **Certificati (computer locale)**.</span><span class="sxs-lookup"><span data-stu-id="ad4e9-124">To view your certificates in the MMC snap-in, select **Console Root** in the left pane, then expand **Certificates (Local Computer)**.</span></span>

    <span data-ttu-id="ad4e9-125">Viene visualizzato un elenco di directory per ogni tipo di certificato.</span><span class="sxs-lookup"><span data-stu-id="ad4e9-125">A list of directories for each type of certificate appears.</span></span> <span data-ttu-id="ad4e9-126">Da ogni directory dei certificati è possibile visualizzarne, esportarne, importarne ed eliminarli.</span><span class="sxs-lookup"><span data-stu-id="ad4e9-126">From each certificate directory, you can view, export, import, and delete its certificates.</span></span>

## <a name="view-certificates-with-the-certificate-manager-tool"></a><span data-ttu-id="ad4e9-127">Visualizzare i certificati con lo strumento Gestione certificati</span><span class="sxs-lookup"><span data-stu-id="ad4e9-127">View certificates with the Certificate Manager tool</span></span>

<span data-ttu-id="ad4e9-128">È inoltre possibile visualizzare, esportare, importare ed eliminare certificati utilizzando lo strumento Gestione certificati.</span><span class="sxs-lookup"><span data-stu-id="ad4e9-128">You can also view, export, import, and delete certificates by using the Certificate Manager tool.</span></span>

### <a name="to-view-certificates-for-the-local-device"></a><span data-ttu-id="ad4e9-129">Per visualizzare i certificati per il dispositivo locale</span><span class="sxs-lookup"><span data-stu-id="ad4e9-129">To view certificates for the local device</span></span>

1. <span data-ttu-id="ad4e9-130">Selezionare **Esegui** dal menu **Start** , quindi immettere *certlm.msc*.</span><span class="sxs-lookup"><span data-stu-id="ad4e9-130">Select **Run** from the **Start** menu, and then enter *certlm.msc*.</span></span>

    <span data-ttu-id="ad4e9-131">Viene visualizzato lo strumento Gestione certificati per il dispositivo locale.</span><span class="sxs-lookup"><span data-stu-id="ad4e9-131">The Certificate Manager tool for the local device appears.</span></span>
  
2. <span data-ttu-id="ad4e9-132">Per visualizzare i certificati, in **Certificati - Computer locale** nel riquadro sinistro espandere la directory per il tipo di certificato che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="ad4e9-132">To view your certificates, under **Certificates - Local Computer** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

### <a name="to-view-certificates-for-the-current-user"></a><span data-ttu-id="ad4e9-133">Per visualizzare i certificati per l'utente corrente</span><span class="sxs-lookup"><span data-stu-id="ad4e9-133">To view certificates for the current user</span></span>

1. <span data-ttu-id="ad4e9-134">Selezionare **Esegui** dal menu **Start** , quindi immettere *certmgr.msc*.</span><span class="sxs-lookup"><span data-stu-id="ad4e9-134">Select **Run** from the **Start** menu, and then enter *certmgr.msc*.</span></span>

    <span data-ttu-id="ad4e9-135">Viene visualizzato lo strumento Gestione certificati per l'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="ad4e9-135">The Certificate Manager tool for the current user appears.</span></span>
  
2. <span data-ttu-id="ad4e9-136">Per visualizzare i certificati, in **Certificati - Utente corrente** nel riquadro sinistro espandere la directory per il tipo di certificato che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="ad4e9-136">To view your certificates, under **Certificates - Current User** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad4e9-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad4e9-137">See also</span></span>

- [<span data-ttu-id="ad4e9-138">Utilizzo dei certificati</span><span class="sxs-lookup"><span data-stu-id="ad4e9-138">Working with certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="ad4e9-139">Procedura: Creare certificati temporanei da utilizzare durante lo sviluppoHow to: Create temporary certificates for use during development</span><span class="sxs-lookup"><span data-stu-id="ad4e9-139">How to: Create temporary certificates for use during development</span></span>](how-to-create-temporary-certificates-for-use-during-development.md)
- [<span data-ttu-id="ad4e9-140">Procedura: recuperare l'identificazione personale di un certificatoHow to: Retrieve the thumbprint of a certificate</span><span class="sxs-lookup"><span data-stu-id="ad4e9-140">How to: Retrieve the thumbprint of a certificate</span></span>](how-to-retrieve-the-thumbprint-of-a-certificate.md)
