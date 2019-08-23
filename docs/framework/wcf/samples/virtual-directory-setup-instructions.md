---
title: Istruzioni per la configurazione di directory virtuali
ms.date: 03/30/2017
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
ms.openlocfilehash: f755fadf6bef2bdd58fd31f3460a143b8f52eddf
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966733"
---
# <a name="virtual-directory-setup-instructions"></a><span data-ttu-id="74cbf-102">Istruzioni per la configurazione di directory virtuali</span><span class="sxs-lookup"><span data-stu-id="74cbf-102">Virtual Directory Setup Instructions</span></span>
<span data-ttu-id="74cbf-103">Gli esempi di Windows Communication Foundation (WCF) sono destinati a condividere una directory virtuale comune denominata servicemodelsamples di cui è stato eseguito il mapping alla cartella%SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="74cbf-103">The Windows Communication Foundation (WCF) samples are intended to share a common virtual directory named servicemodelsamples that is mapped to the %SystemDrive%\inetpub\wwwroot\servicemodelsamples folder.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="74cbf-104">%SystemDrive% è in genere C: o D:, a seconda della posizione dell'unità dove è installato IIS (Internet Information Services).</span><span class="sxs-lookup"><span data-stu-id="74cbf-104">%SystemDrive% is usually C: or D:, depending on the drive location where Internet Information Services (IIS) is installed.</span></span>  
  
 <span data-ttu-id="74cbf-105">È possibile eseguire i file Setupvroot. bat e Cleanupvroot. bat dalla [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) per creare la directory virtuale.</span><span class="sxs-lookup"><span data-stu-id="74cbf-105">You can run the Setupvroot.bat and Cleanupvroot.bat files from the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) to create the virtual directory.</span></span> <span data-ttu-id="74cbf-106">Se si preferisce creare la directory virtuale manualmente, utilizzare le procedure seguenti.</span><span class="sxs-lookup"><span data-stu-id="74cbf-106">If you prefer to create the virtual directory manually, use the following procedures.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="74cbf-107">Procedure</span><span class="sxs-lookup"><span data-stu-id="74cbf-107">Procedures</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-70-or-75"></a><span data-ttu-id="74cbf-108">Per creare una directory virtuale in IIS 7,0 o 7,5</span><span class="sxs-lookup"><span data-stu-id="74cbf-108">To create a virtual directory in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="74cbf-109">Dal menu **Start** fare clic su **Esegui**, quindi digitare **inetmgr** per aprire lo snap-in MMC Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="74cbf-109">From the **Start** menu, click **Run**, then type **inetmgr** to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="74cbf-110">Nel riquadro sinistro espandere il nodo con il nome del computer, quindi espandere il nodo **siti** .</span><span class="sxs-lookup"><span data-stu-id="74cbf-110">In the left pane, expand the node with the computer's name, and then expand the **Sites** node.</span></span>  
  
3. <span data-ttu-id="74cbf-111">Fare clic con il pulsante destro del mouse su **sito Web predefinito**e selezionare **Aggiungi applicazione** per aprire la **finestra Aggiungi applicazione**.</span><span class="sxs-lookup"><span data-stu-id="74cbf-111">Right-click **Default Web Site**, and then select **Add Application** to open the **Add Application window**.</span></span>  
  
4. <span data-ttu-id="74cbf-112">Nella finestra di digitare `servicemodelsamples` come alias per la directory virtuale che si sta creando.</span><span class="sxs-lookup"><span data-stu-id="74cbf-112">In the window, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5. <span data-ttu-id="74cbf-113">Creare la directory seguente: %SystemDrive%\inetpub\wwwroot\servicemodelsamples</span><span class="sxs-lookup"><span data-stu-id="74cbf-113">Create the following directory: %SystemDrive%\inetpub\wwwroot\servicemodelsamples</span></span>  
  
6. <span data-ttu-id="74cbf-114">Impostare il percorso fisico su %SystemDrive%\inetpub\wwwroot\\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="74cbf-114">Set the physical path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  <span data-ttu-id="74cbf-115">Molti degli esempi WCF copiano file eseguibili di servizi in questo percorso quando vengono generati.</span><span class="sxs-lookup"><span data-stu-id="74cbf-115">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
7. <span data-ttu-id="74cbf-116">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="74cbf-116">Click **OK**.</span></span> <span data-ttu-id="74cbf-117">L'applicazione Web è stata creata per gli esempi WCF.</span><span class="sxs-lookup"><span data-stu-id="74cbf-117">The Web application is now created for the WCF samples.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="74cbf-118">Questa attività deve essere eseguita solo una volta, poiché tutti gli esempi WCF utilizzano la stessa applicazione Web servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="74cbf-118">This task must be performed only once, because all of the WCF samples use the same servicemodelsamples Web application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="74cbf-119">Ai fini di questa documentazione, il termine `virtual directory` è sinonimo di `Web application`.</span><span class="sxs-lookup"><span data-stu-id="74cbf-119">For the purpose of this documentation, the term `virtual directory` is synonymous with `Web application`.</span></span>  
  
     <span data-ttu-id="74cbf-120">Oltre a creare la directory virtuale, è inoltre necessario impostare le proprietà per consentire l'esecuzione dei servizi WCF.</span><span class="sxs-lookup"><span data-stu-id="74cbf-120">In addition to creating the virtual directory, you must also set its properties to enable WCF services to run.</span></span> <span data-ttu-id="74cbf-121">Di seguito sono riportate informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="74cbf-121">See below for details.</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-51-or-60"></a><span data-ttu-id="74cbf-122">Per creare una directory virtuale in IIS 5.1 o 6.0</span><span class="sxs-lookup"><span data-stu-id="74cbf-122">To create a virtual directory in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="74cbf-123">Aprire una finestra del prompt dei comandi `start inetmgr` e digitare per aprire lo snap-in MMC Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="74cbf-123">Open a command prompt window and type `start inetmgr` to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="74cbf-124">Nel riquadro sinistro espandere il nodo con il nome del computer, quindi espandere il nodo **siti Web** .</span><span class="sxs-lookup"><span data-stu-id="74cbf-124">In the left pane, expand the node with the computer's name, and then expand the **Web Sites** node.</span></span>  
  
3. <span data-ttu-id="74cbf-125">Fare clic con il pulsante destro del mouse su **sito Web predefinito** e selezionare **nuovo, directory virtuale** per aprire la creazione guidata directory virtuale.</span><span class="sxs-lookup"><span data-stu-id="74cbf-125">Right-click **Default Web Site** and select **New, Virtual Directory** to open the Virtual Directory Creation wizard.</span></span>  
  
4. <span data-ttu-id="74cbf-126">Nella procedura guidata digitare `servicemodelsamples` come alias per la directory virtuale che si sta creando.</span><span class="sxs-lookup"><span data-stu-id="74cbf-126">In the wizard, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5. <span data-ttu-id="74cbf-127">Impostare il percorso su %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="74cbf-127">Set the path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span> <span data-ttu-id="74cbf-128">Molti degli esempi WCF copiano file eseguibili di servizi in questo percorso quando vengono generati.</span><span class="sxs-lookup"><span data-stu-id="74cbf-128">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
6. <span data-ttu-id="74cbf-129">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="74cbf-129">Click **Next**.</span></span>  
  
7. <span data-ttu-id="74cbf-130">Per impostazione predefinita, le caselle di controllo seguenti sono selezionate:</span><span class="sxs-lookup"><span data-stu-id="74cbf-130">By default, the following check boxes are selected:</span></span>  
  
    - <span data-ttu-id="74cbf-131">**Read**</span><span class="sxs-lookup"><span data-stu-id="74cbf-131">**Read**</span></span>  
  
    - <span data-ttu-id="74cbf-132">**Esegui script (ad esempio, ASP)**</span><span class="sxs-lookup"><span data-stu-id="74cbf-132">**Run scripts (such as ASP)**</span></span>  
  
8. <span data-ttu-id="74cbf-133">Fare clic su **Avanti**e quindi su **fine** per completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="74cbf-133">Click **Next**, and then click **Finish** to complete the wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="74cbf-134">Questa attività deve essere eseguita solo una volta poiché tutti gli esempi WCF utilizzano la stessa directory virtuale servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="74cbf-134">This task must be performed only once because all of the WCF samples use the same servicemodelsamples virtual directory.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-70-or-75"></a><span data-ttu-id="74cbf-135">Per impostare proprietà aggiuntive della directory virtuale in IIS 7,0 o 7,5</span><span class="sxs-lookup"><span data-stu-id="74cbf-135">To set additional virtual directory properties in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="74cbf-136">Fare clic sul nodo servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="74cbf-136">Click the servicemodelsamples node.</span></span> <span data-ttu-id="74cbf-137">Lungo la parte inferiore della finestra sono elencate due visualizzazioni.</span><span class="sxs-lookup"><span data-stu-id="74cbf-137">Along the bottom of the window, two views are listed.</span></span> <span data-ttu-id="74cbf-138">Selezionare **visualizzazione funzionalità** se non è già selezionata.</span><span class="sxs-lookup"><span data-stu-id="74cbf-138">Select **Features View** if it isn’t already selected.</span></span>  
  
2. <span data-ttu-id="74cbf-139">Fare doppio clic sulla voce per l' **esplorazione directory**.</span><span class="sxs-lookup"><span data-stu-id="74cbf-139">Double-click the entry for **Directory Browsing**.</span></span>  
  
3. <span data-ttu-id="74cbf-140">Nel riquadro azioni selezionare l'opzione **Abilita** .</span><span class="sxs-lookup"><span data-stu-id="74cbf-140">In the Actions pane, select the **Enable** option.</span></span> <span data-ttu-id="74cbf-141">In questo modo sarà possibile accedere alla directory della directory utilizzando Internet Explorer che facilita l’esecuzione del debug di un servizio.</span><span class="sxs-lookup"><span data-stu-id="74cbf-141">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
 <span data-ttu-id="74cbf-142">Infine, è necessario impostare le proprietà di sicurezza della cartella servicemodelsamples per renderla accessibile ad altri.</span><span class="sxs-lookup"><span data-stu-id="74cbf-142">Finally, you must set the security properties of the servicemodelsamples folder to allow it to be accessed by others.</span></span> <span data-ttu-id="74cbf-143">Di seguito sono riportate informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="74cbf-143">See below for details.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-51-or-60"></a><span data-ttu-id="74cbf-144">Per impostare proprietà aggiuntive della directory virtuale in IIS 5.1 o 6.0</span><span class="sxs-lookup"><span data-stu-id="74cbf-144">To set additional virtual directory properties in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="74cbf-145">Fare clic con il pulsante destro del mouse sul nodo servicemodelsamples, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="74cbf-145">Right-click the servicemodelsamples node and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="74cbf-146">Per impostazione predefinita, le caselle di controllo seguenti sono selezionate:</span><span class="sxs-lookup"><span data-stu-id="74cbf-146">By default, the following check boxes are selected:</span></span>  
  
    - <span data-ttu-id="74cbf-147">**Read**</span><span class="sxs-lookup"><span data-stu-id="74cbf-147">**Read**</span></span>  
  
    - <span data-ttu-id="74cbf-148">**Log visite**</span><span class="sxs-lookup"><span data-stu-id="74cbf-148">**Log visits**</span></span>  
  
    - <span data-ttu-id="74cbf-149">**Indicizza questa risorsa**</span><span class="sxs-lookup"><span data-stu-id="74cbf-149">**Index this resource**</span></span>  
  
3. <span data-ttu-id="74cbf-150">Selezionare la casella di controllo **esplorazione directory** .</span><span class="sxs-lookup"><span data-stu-id="74cbf-150">Select the **Directory browsing** check box.</span></span> <span data-ttu-id="74cbf-151">In questo modo sarà possibile accedere alla directory della directory utilizzando Internet Explorer che facilita l’esecuzione del debug di un servizio.</span><span class="sxs-lookup"><span data-stu-id="74cbf-151">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-70-or-75"></a><span data-ttu-id="74cbf-152">Per impostare le proprietà di sicurezza della cartella in IIS 7,0 o 7,5</span><span class="sxs-lookup"><span data-stu-id="74cbf-152">To set security properties of the folder in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="74cbf-153">Passare a %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="74cbf-153">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2. <span data-ttu-id="74cbf-154">Fare clic con il pulsante destro del mouse sulla cartella servicemodelsamples e scegliere **Condividi** o **Condividi con**.</span><span class="sxs-lookup"><span data-stu-id="74cbf-154">Right-click the servicemodelsamples folder and click **Share** or **Share With**.</span></span>  
  
3. <span data-ttu-id="74cbf-155">Fare clic sulla freccia verso il basso a sinistra del pulsante **Aggiungi** .</span><span class="sxs-lookup"><span data-stu-id="74cbf-155">Click the down arrow to the left of the **Add** button.</span></span>  
  
4. <span data-ttu-id="74cbf-156">Selezionare la voce **trova** .</span><span class="sxs-lookup"><span data-stu-id="74cbf-156">Select the **Find** entry.</span></span> <span data-ttu-id="74cbf-157">Verrà visualizzata la finestra **Selezione utenti o gruppi** .</span><span class="sxs-lookup"><span data-stu-id="74cbf-157">The **Select Users or Groups** window opens.</span></span>  
  
5. <span data-ttu-id="74cbf-158">Scegliere **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="74cbf-158">Click **Advanced**.</span></span>  
  
6. <span data-ttu-id="74cbf-159">Fare clic su **percorsi**.</span><span class="sxs-lookup"><span data-stu-id="74cbf-159">Click **Locations**.</span></span> <span data-ttu-id="74cbf-160">La finestra **percorsi** è ora aperta.</span><span class="sxs-lookup"><span data-stu-id="74cbf-160">The **Locations** window is now open.</span></span>  
  
7. <span data-ttu-id="74cbf-161">Selezionare la voce per il computer utilizzato.</span><span class="sxs-lookup"><span data-stu-id="74cbf-161">Select the entry for the computer being used.</span></span> <span data-ttu-id="74cbf-162">È importante selezionare il computer locale e non una voce per qualsiasi dominio o reti elencati.</span><span class="sxs-lookup"><span data-stu-id="74cbf-162">It is important to select the local computer and not an entry for any domains or networks that are listed.</span></span> <span data-ttu-id="74cbf-163">Dopo aver selezionato il computer, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="74cbf-163">After you have selected the computer, click **OK**.</span></span>  
  
8. <span data-ttu-id="74cbf-164">Fare clic su **trova ora**.</span><span class="sxs-lookup"><span data-stu-id="74cbf-164">Click **Find Now**.</span></span> <span data-ttu-id="74cbf-165">Nei risultati di ricerca vengono inseriti gli oggetti associati al computer locale.</span><span class="sxs-lookup"><span data-stu-id="74cbf-165">This populates the search results with objects associated with the local computer.</span></span>  
  
9. <span data-ttu-id="74cbf-166">Trovare la voce **IIS_IUSRS** nella colonna **nome (nome distinto relativo)** .</span><span class="sxs-lookup"><span data-stu-id="74cbf-166">Find the **IIS_IUSRS** entry in the **Name (Relative Distinguished Name)** column.</span></span> <span data-ttu-id="74cbf-167">Selezionare la voce e fare clic su **OK** per chiudere la finestra dei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="74cbf-167">Select that entry and click **OK** to close the search results window.</span></span>  
  
10. <span data-ttu-id="74cbf-168">Fare clic su **OK** per chiudere la finestra **Selezione utenti o gruppi** .</span><span class="sxs-lookup"><span data-stu-id="74cbf-168">Click **OK** to close the **Select Users or Groups** window.</span></span>  
  
11. <span data-ttu-id="74cbf-169">Fare clic su **Condividi** per salvare in modo permanente le modifiche.</span><span class="sxs-lookup"><span data-stu-id="74cbf-169">Click **Share** to persist the changes.</span></span>  
  
12. <span data-ttu-id="74cbf-170">Una volta completate le modifiche per abilitare la condivisione, fare clic su **Completato** per chiudere la finestra **Condivisione File**.</span><span class="sxs-lookup"><span data-stu-id="74cbf-170">After the changes to enable sharing are complete, click **Done** to close the **File Sharing** window.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-51-or-60"></a><span data-ttu-id="74cbf-171">Per impostare le proprietà di sicurezza della cartella in IIS 5.1 o 6.0</span><span class="sxs-lookup"><span data-stu-id="74cbf-171">To set security properties of the folder in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="74cbf-172">Passare a %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="74cbf-172">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2. <span data-ttu-id="74cbf-173">Fare clic con il pulsante destro del mouse sulla cartella **servicemodelsamples** , quindi scegliere **condivisione e sicurezza.**</span><span class="sxs-lookup"><span data-stu-id="74cbf-173">Right-click the **servicemodelsamples** folder and then click **Sharing and Security.**</span></span>  
  
3. <span data-ttu-id="74cbf-174">Fare clic sulla scheda **Sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="74cbf-174">Click the **Security** tab.</span></span>  
  
4. <span data-ttu-id="74cbf-175">Se si utilizza IIS 6,0, nella casella **nome gruppo o utente** verificare se è elencato l' **account Internet Guest** .</span><span class="sxs-lookup"><span data-stu-id="74cbf-175">If you are using IIS 6.0, in the **Group or user names** box, check whether **Internet Guest Account** is listed.</span></span>  
  
     <span data-ttu-id="74cbf-176">Se non è elencato:</span><span class="sxs-lookup"><span data-stu-id="74cbf-176">If it is not listed:</span></span>  
  
    1. <span data-ttu-id="74cbf-177">Fare clic sul pulsante **Start** e scegliere **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="74cbf-177">Click **Start** and then click **Control Panel**.</span></span>  
  
    2. <span data-ttu-id="74cbf-178">Se l'icona **account utente** non viene visualizzata, fare clic su **passa alla visualizzazione categoria**.</span><span class="sxs-lookup"><span data-stu-id="74cbf-178">If you do not see the **User Accounts** icon, click **Switch to Category View**.</span></span>  
  
    3. <span data-ttu-id="74cbf-179">Fare clic sull'icona **account utente** .</span><span class="sxs-lookup"><span data-stu-id="74cbf-179">Click the **User Accounts** icon.</span></span>  
  
    4. <span data-ttu-id="74cbf-180">In "o selezionare un'icona del pannello di controllo" fare clic su **account utente**.</span><span class="sxs-lookup"><span data-stu-id="74cbf-180">Under "or pick a Control Panel icon," click **User Accounts**.</span></span>  
  
    5. <span data-ttu-id="74cbf-181">Nella finestra di dialogo **account utente** fare clic sulla scheda **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="74cbf-181">In the **User Accounts** dialog box, click the **Advanced** tab.</span></span>  
  
    6. <span data-ttu-id="74cbf-182">Scegliere **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="74cbf-182">Click **Advanced**.</span></span>  
  
    7. <span data-ttu-id="74cbf-183">Nella finestra di dialogo **utenti e gruppi locali** fare clic per espandere la cartella **utenti** .</span><span class="sxs-lookup"><span data-stu-id="74cbf-183">In the **Local Users and Groups** dialog box, click to expand the **Users** folder.</span></span>  
  
    8. <span data-ttu-id="74cbf-184">Nel riquadro destro fare doppio clic su **account Internet Guest**.</span><span class="sxs-lookup"><span data-stu-id="74cbf-184">In the right pane, double-click **Internet Guest Account**.</span></span>  
  
    9. <span data-ttu-id="74cbf-185">Nella finestra di dialogo **Proprietà** copiare il nome utilizzato come account Internet Guest.</span><span class="sxs-lookup"><span data-stu-id="74cbf-185">In the **Properties** dialog box, copy the name used as the Internet guest account.</span></span> <span data-ttu-id="74cbf-186">Per impostazione predefinita, il nome inizia con “USR_” seguito dal nome del computer.</span><span class="sxs-lookup"><span data-stu-id="74cbf-186">By default, the name begins with "USR_" followed by the name of the computer.</span></span>  
  
    10. <span data-ttu-id="74cbf-187">Chiudere la finestra di dialogo **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="74cbf-187">Close the **Properties** dialog box.</span></span>  
  
    11. <span data-ttu-id="74cbf-188">Chiudere la finestra **di dialogo utenti e gruppi locali** .</span><span class="sxs-lookup"><span data-stu-id="74cbf-188">Close the **Local Users and Groups** dialog box.</span></span>  
  
    12. <span data-ttu-id="74cbf-189">Chiudere la finestra di dialogo **account utente** .</span><span class="sxs-lookup"><span data-stu-id="74cbf-189">Close the **User Accounts** dialog box.</span></span>  
  
    13. <span data-ttu-id="74cbf-190">Chiudere la finestra di dialogo altri **account utente** .</span><span class="sxs-lookup"><span data-stu-id="74cbf-190">Close the other **User Accounts** dialog box.</span></span>  
  
    14. <span data-ttu-id="74cbf-191">Nella scheda **sicurezza** della finestra di dialogo **Proprietà servicemodelsamples** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="74cbf-191">In the **servicemodelsamples Properties** dialog box, on the **Security** tab, click **Add**.</span></span>  
  
    15. <span data-ttu-id="74cbf-192">Digitare il nome del computer seguito da una barra rovesciata, quindi incollare il nome dell'account utente Internet, ad esempio,\\nomecomputer% InternetGuestAccountName%</span><span class="sxs-lookup"><span data-stu-id="74cbf-192">Type the name of the computer followed by a backslash, then paste the name of the Internet user account, for example, myMachineName\\%InternetGuestAccountName%</span></span>  
  
    16. <span data-ttu-id="74cbf-193">Fare clic su **Controlla nomi** per verificare l'aggiunta.</span><span class="sxs-lookup"><span data-stu-id="74cbf-193">Click **Check Names** to verify the addition.</span></span> <span data-ttu-id="74cbf-194">Se è valido, il nome è composto di tutti caratteri maiuscoli ed è sottolineato.</span><span class="sxs-lookup"><span data-stu-id="74cbf-194">If it is valid, the name is in all capital letters and is underlined.</span></span>  
  
5. <span data-ttu-id="74cbf-195">Per IIS 6,0, verificare anche che servizio di rete sia elencato nella casella **nome gruppo o utente** .</span><span class="sxs-lookup"><span data-stu-id="74cbf-195">For IIS 6.0, also check that NETWORK SERVICE is listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="74cbf-196">Se SERVIZIO DI RETE non è elencato:</span><span class="sxs-lookup"><span data-stu-id="74cbf-196">If NETWORK SERVICE is not listed:</span></span>  
  
    1. <span data-ttu-id="74cbf-197">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="74cbf-197">Click **Add**.</span></span>  
  
    2. <span data-ttu-id="74cbf-198">Nella finestra di dialogo **Seleziona utenti o gruppi** Digitare il nome del computer seguito da una barra rovesciata.</span><span class="sxs-lookup"><span data-stu-id="74cbf-198">In the **Select Users or Groups** dialog box, type the name of the computer followed by a backslash.</span></span>  
  
    3. <span data-ttu-id="74cbf-199">Digitare **Service** dopo la barra rovesciata (senza spazio).</span><span class="sxs-lookup"><span data-stu-id="74cbf-199">Type **service** after the backslash (no space).</span></span>  
  
    4. <span data-ttu-id="74cbf-200">Fare clic su **Controlla nomi**.</span><span class="sxs-lookup"><span data-stu-id="74cbf-200">Click **Check names**.</span></span>  
  
    5. <span data-ttu-id="74cbf-201">Se vengono trovati più nomi, selezionare **servizio di rete** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="74cbf-201">If multiple names are found, select **NETWORK SERVICE** and click **OK**.</span></span>  
  
    6. <span data-ttu-id="74cbf-202">Fare clic su **OK** per chiudere la finestra di dialogo **Seleziona utenti o gruppi** .</span><span class="sxs-lookup"><span data-stu-id="74cbf-202">Click **OK** to close the **Select Users or Groups** dialog box.</span></span>  
  
6. <span data-ttu-id="74cbf-203">Se si utilizza Windows XP SP2 con IIS 5,1, verificare che sia l'account Guest Internet che ASPNET siano elencati nella casella **nome gruppo o utente** .</span><span class="sxs-lookup"><span data-stu-id="74cbf-203">If you are using Windows XP SP2 with IIS 5.1, check that both Internet Guest Account and ASPNET are listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="74cbf-204">Si noti che l'utente ASPNET può essere un membro del gruppo di sicurezza predefinito Users.</span><span class="sxs-lookup"><span data-stu-id="74cbf-204">Note that the ASPNET user may be a member of the built-in **Users** security group.</span></span> <span data-ttu-id="74cbf-205">In tal caso, se il gruppo **utenti** è elencato nella finestra di dialogo, non è necessario aggiungerlo come elemento separato all'elenco degli utenti autorizzati.</span><span class="sxs-lookup"><span data-stu-id="74cbf-205">If so, then if the **Users** group is listed in the dialog box, you do not need to add it as a separate item to the list of permitted users.</span></span>  
  
     <span data-ttu-id="74cbf-206">Per verificare se ASPNET fa parte del gruppo di sicurezza Users:</span><span class="sxs-lookup"><span data-stu-id="74cbf-206">To check if ASPNET is part of the **Users** security group:</span></span>  
  
    1. <span data-ttu-id="74cbf-207">Scegliere **Pannello di controllo**dal menu **Start** .</span><span class="sxs-lookup"><span data-stu-id="74cbf-207">On the **Start** menu, click **Control Panel**.</span></span>  
  
    2. <span data-ttu-id="74cbf-208">Fare clic sull'icona **account utente** .</span><span class="sxs-lookup"><span data-stu-id="74cbf-208">Click the **User Accounts** icon.</span></span>  
  
    3. <span data-ttu-id="74cbf-209">Nella colonna **gruppo** verificare che il valore per **ASPNET** sia "Users".</span><span class="sxs-lookup"><span data-stu-id="74cbf-209">In the **Group** column, check that the value for **ASPNET** is "Users."</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74cbf-210">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74cbf-210">See also</span></span>

- [<span data-ttu-id="74cbf-211">Istruzioni per l'hosting su Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="74cbf-211">Internet Information Service Hosting Instructions</span></span>](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)
