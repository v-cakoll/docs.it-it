---
title: 'Procedura: Visualizzare i certificati con lo snap-in MMC'
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 69f79b64250ff46524e7b4720d13351774875a3f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972720"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a><span data-ttu-id="33606-102">Procedura: Visualizzare i certificati con lo snap-in MMC</span><span class="sxs-lookup"><span data-stu-id="33606-102">How to: View certificates with the MMC snap-in</span></span>
<span data-ttu-id="33606-103">Quando si crea un client protetto o un servizio, è possibile usare una [certificato](working-with-certificates.md) come le credenziali.</span><span class="sxs-lookup"><span data-stu-id="33606-103">When you create a secure client or service, you can use a [certificate](working-with-certificates.md) as the credential.</span></span> <span data-ttu-id="33606-104">Ad esempio, un tipo comune di credenziale è il certificato X.509 che si crea con la <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> (metodo).</span><span class="sxs-lookup"><span data-stu-id="33606-104">For example, a common type of credential is the X.509 certificate, which you create with the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> method.</span></span> 

<span data-ttu-id="33606-105">Esistono tre diversi tipi di archivi di certificati che è possibile esaminare con Microsoft Management Console (MMC) nei sistemi Windows:</span><span class="sxs-lookup"><span data-stu-id="33606-105">There are three different types of certificate stores that you can examine with the Microsoft Management Console (MMC) on Windows systems:</span></span>

- <span data-ttu-id="33606-106">Computer locale: L'archivio è locale per il dispositivo e globali per tutti gli utenti del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="33606-106">Local computer: The store is local to the device and global to all users on the device.</span></span>

- <span data-ttu-id="33606-107">Utente corrente: L'archivio è locale all'account utente corrente nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="33606-107">Current user: The store is local to the current user account on the device.</span></span>

- <span data-ttu-id="33606-108">Account del servizio: L'archivio è locale rispetto a un determinato servizio nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="33606-108">Service account: The store is local to a particular service on the device.</span></span>

## <a name="view-certificates-in-the-mmc-snap-in"></a><span data-ttu-id="33606-109">Visualizzare i certificati nello snap-in MMC</span><span class="sxs-lookup"><span data-stu-id="33606-109">View certificates in the MMC snap-in</span></span> 

<span data-ttu-id="33606-110">La procedura seguente viene illustrato come esaminare gli archivi nel dispositivo locale per trovare un certificato appropriato:</span><span class="sxs-lookup"><span data-stu-id="33606-110">The following procedure demonstrates how to examine the stores on your local device to find an appropriate certificate:</span></span> 
  
1. <span data-ttu-id="33606-111">Selezionare **eseguiti** dalle **avviare** dal menu e quindi immettere *mmc*.</span><span class="sxs-lookup"><span data-stu-id="33606-111">Select **Run** from the **Start** menu, and then enter *mmc*.</span></span> 

    <span data-ttu-id="33606-112">Verrà visualizzata la finestra di MMC.</span><span class="sxs-lookup"><span data-stu-id="33606-112">The MMC appears.</span></span> 
  
2. <span data-ttu-id="33606-113">Dal **File** dal menu **Aggiungi/Rimuovi snap-In**.</span><span class="sxs-lookup"><span data-stu-id="33606-113">From the **File** menu, select **Add/Remove Snap In**.</span></span> 
    
    <span data-ttu-id="33606-114">Il **Aggiungi o Rimuovi Snap-in** verrà visualizzata la finestra.</span><span class="sxs-lookup"><span data-stu-id="33606-114">The **Add or Remove Snap-ins** window appears.</span></span>
  
3. <span data-ttu-id="33606-115">Dal **snap-in disponibili** casella di riepilogo **certificati**, quindi selezionare **Add**.</span><span class="sxs-lookup"><span data-stu-id="33606-115">From the **Available snap-ins** list, choose **Certificates**, then select **Add**.</span></span>  

    ![Aggiungere lo snap-in certificati](./media/mmc-add-certificate-snap-in.png)
  
4. <span data-ttu-id="33606-117">Nel **snap-in certificati** finestra, seleziona **account Computer**e quindi selezionare **Next**.</span><span class="sxs-lookup"><span data-stu-id="33606-117">In the **Certificates snap-in** window, select **Computer account**, and then select **Next**.</span></span> 
  
    <span data-ttu-id="33606-118">Facoltativamente, è possibile selezionare **account dell'utente** per l'utente corrente oppure **account del servizio** per un determinato servizio.</span><span class="sxs-lookup"><span data-stu-id="33606-118">Optionally, you can select **My user account** for the current user or **Service account** for a particular service.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="33606-119">Se non si ha un amministratore per il dispositivo, è possibile gestire i certificati solo per l'account utente.</span><span class="sxs-lookup"><span data-stu-id="33606-119">If you're not an administrator for your device, you can manage certificates only for your user account.</span></span>
  
5. <span data-ttu-id="33606-120">Nel **seleziona Computer** finestra, lasciare **computer locale** selezionata e quindi selezionare **fine**.</span><span class="sxs-lookup"><span data-stu-id="33606-120">In the **Select Computer** window, leave **Local computer** selected, and then select **Finish**.</span></span>  
  
6. <span data-ttu-id="33606-121">Nel **Aggiungi o Rimuovi Snap-in** finestra, seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="33606-121">In the **Add or Remove Snap-in** window, select **OK**.</span></span>  
  
    ![Aggiungere lo snap-in certificati](./media/mmc-certificate-snap-in-selected.png)

7. <span data-ttu-id="33606-123">Facoltative: Dal **File** dal menu **salvare** oppure **Salva con nome** per salvare il file di console MMC per un uso successivo.</span><span class="sxs-lookup"><span data-stu-id="33606-123">Optional: From the **File** menu, select **Save** or **Save As** to save the MMC console file for later use.</span></span>  

8. <span data-ttu-id="33606-124">Per visualizzare i certificati nello snap-in MMC, selezionare **radice Console** nel riquadro sinistro, quindi espandere **certificati (Computer locale)**.</span><span class="sxs-lookup"><span data-stu-id="33606-124">To view your certificates in the MMC snap-in, select **Console Root** in the left pane, then expand **Certificates (Local Computer)**.</span></span>

    <span data-ttu-id="33606-125">Viene visualizzato un elenco di directory per ogni tipo di certificato.</span><span class="sxs-lookup"><span data-stu-id="33606-125">A list of directories for each type of certificate appears.</span></span> <span data-ttu-id="33606-126">Dalla directory ogni certificato, è possibile visualizzare, esportare, importare ed eliminare i propri certificati.</span><span class="sxs-lookup"><span data-stu-id="33606-126">From each certificate directory, you can view, export, import, and delete its certificates.</span></span>

## <a name="view-certificates-with-the-certificate-manager-tool"></a><span data-ttu-id="33606-127">Visualizzare i certificati con lo strumento di gestione certificati</span><span class="sxs-lookup"><span data-stu-id="33606-127">View certificates with the Certificate Manager tool</span></span>

<span data-ttu-id="33606-128">È anche possibile visualizzare, esportare, importare ed eliminare certificati utilizzando lo strumento di gestione certificati.</span><span class="sxs-lookup"><span data-stu-id="33606-128">You can also view, export, import, and delete certificates by using the Certificate Manager tool.</span></span>

### <a name="to-view-certificates-for-the-local-device"></a><span data-ttu-id="33606-129">Per visualizzare i certificati per il dispositivo locale</span><span class="sxs-lookup"><span data-stu-id="33606-129">To view certificates for the local device</span></span>

1. <span data-ttu-id="33606-130">Selezionare **eseguiti** dalle **avviare** dal menu e quindi immettere *certlm. msc*.</span><span class="sxs-lookup"><span data-stu-id="33606-130">Select **Run** from the **Start** menu, and then enter *certlm.msc*.</span></span> 

    <span data-ttu-id="33606-131">Viene visualizzato lo strumento di gestione certificati per il dispositivo locale.</span><span class="sxs-lookup"><span data-stu-id="33606-131">The Certificate Manager tool for the local device appears.</span></span> 
  
2. <span data-ttu-id="33606-132">Per visualizzare i certificati, in **certificati - Computer locale** nel riquadro sinistro, espandere la directory per il tipo di certificato che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="33606-132">To view your certificates, under **Certificates - Local Computer** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

### <a name="to-view-certificates-for-the-current-user"></a><span data-ttu-id="33606-133">Per visualizzare i certificati per l'utente corrente</span><span class="sxs-lookup"><span data-stu-id="33606-133">To view certificates for the current user</span></span>

1. <span data-ttu-id="33606-134">Selezionare **eseguiti** dalle **avviare** dal menu e quindi immettere *Certmgr. msc*.</span><span class="sxs-lookup"><span data-stu-id="33606-134">Select **Run** from the **Start** menu, and then enter *certmgr.msc*.</span></span> 

    <span data-ttu-id="33606-135">Viene visualizzato lo strumento di gestione certificati per l'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="33606-135">The Certificate Manager tool for the current user appears.</span></span> 
  
2. <span data-ttu-id="33606-136">Per visualizzare i certificati, in **certificati - utente corrente** nel riquadro sinistro, espandere la directory per il tipo di certificato che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="33606-136">To view your certificates, under **Certificates - Current User** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

## <a name="see-also"></a><span data-ttu-id="33606-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33606-137">See also</span></span>

- [<span data-ttu-id="33606-138">Utilizzo dei certificati</span><span class="sxs-lookup"><span data-stu-id="33606-138">Working with certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="33606-139">Procedura: Creare certificati temporanei da usare durante lo sviluppo</span><span class="sxs-lookup"><span data-stu-id="33606-139">How to: Create temporary certificates for use during development</span></span>](how-to-create-temporary-certificates-for-use-during-development.md)
- [<span data-ttu-id="33606-140">Procedura: Recuperare l'identificazione personale di un certificato</span><span class="sxs-lookup"><span data-stu-id="33606-140">How to: Retrieve the thumbprint of a certificate</span></span>](how-to-retrieve-the-thumbprint-of-a-certificate.md)
