---
title: Istruzioni per l'hosting su IIS (Internet Information Services)
ms.date: 03/30/2017
ms.assetid: 959a21c8-9d9d-4757-b255-4e57793ae9d6
ms.openlocfilehash: 226b47bfd90dc4cffb0a364a804016043cc25d02
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929117"
---
# <a name="internet-information-service-hosting-instructions"></a><span data-ttu-id="83adf-102">Istruzioni per l'hosting su IIS (Internet Information Services)</span><span class="sxs-lookup"><span data-stu-id="83adf-102">Internet Information Service Hosting Instructions</span></span>
<span data-ttu-id="83adf-103">Per eseguire gli esempi ospitati su Internet Information Services (IIS) è necessario assicurarsi che IIS sia installato correttamente e sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="83adf-103">To run the samples that are hosted by Internet Information Services (IIS), you must make sure that IIS is properly installed and is running.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-server-2008-r2"></a><span data-ttu-id="83adf-104">Installazione di IIS versione 7.5 in Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="83adf-104">To install IIS version 7.5 on Windows Server 2008 R2</span></span>  
  
1. <span data-ttu-id="83adf-105">In **Server Manager**selezionare **ruoli.**</span><span class="sxs-lookup"><span data-stu-id="83adf-105">From **Server Manager**, select **Roles.**</span></span> <span data-ttu-id="83adf-106">In **Riepilogo ruoli**fare clic su **Aggiungi ruoli**.</span><span class="sxs-lookup"><span data-stu-id="83adf-106">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2. <span data-ttu-id="83adf-107">Fare clic su **Avanti** per visualizzare la finestra di dialogo **Selezione ruoli server** .</span><span class="sxs-lookup"><span data-stu-id="83adf-107">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3. <span data-ttu-id="83adf-108">Selezionare **server applicazioni** dall'elenco **ruoli** , quindi fare clic due volte su **Avanti** per visualizzare la finestra di dialogo **Selezione servizi ruolo** per il ruolo server applicazioni.</span><span class="sxs-lookup"><span data-stu-id="83adf-108">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4. <span data-ttu-id="83adf-109">Selezionare la casella di controllo **server Web (IIS)** .</span><span class="sxs-lookup"><span data-stu-id="83adf-109">Select the **Web Server (IIS)** check box.</span></span> <span data-ttu-id="83adf-110">Se viene richiesto di installare servizi ruolo e funzionalità aggiuntivi, fare clic su **Aggiungi funzionalità necessarie**.</span><span class="sxs-lookup"><span data-stu-id="83adf-110">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="83adf-111">Fare clic due volte su **Avanti** per visualizzare la finestra di dialogo **Selezione servizi ruolo** per il ruolo server Web (IIS).</span><span class="sxs-lookup"><span data-stu-id="83adf-111">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5. <span data-ttu-id="83adf-112">Espandere **strumenti di gestione**, quindi espandere **compatibilità di gestione con IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="83adf-112">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="83adf-113">Selezionare **strumenti di script di IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="83adf-113">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="83adf-114">Se viene richiesto di installare servizi ruolo e funzionalità aggiuntivi, fare clic su **Aggiungi servizi ruolo necessari**.</span><span class="sxs-lookup"><span data-stu-id="83adf-114">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="83adf-115">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="83adf-115">Click **Next**.</span></span>  
  
6. <span data-ttu-id="83adf-116">Se il riepilogo delle selezioni è corretto, fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="83adf-116">If the summary of selections is correct, click **Install**.</span></span>  
  
7. <span data-ttu-id="83adf-117">Al termine dell'installazione, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="83adf-117">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-7"></a><span data-ttu-id="83adf-118">Per installare IIS versione 7.5 in Windows 7</span><span class="sxs-lookup"><span data-stu-id="83adf-118">To install IIS version 7.5 on Windows 7</span></span>  
  
1. <span data-ttu-id="83adf-119">Fare clic sul pulsante **Start**, quindi scegliere **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="83adf-119">Click **Start**, and then click **Control Panel**.</span></span>  
  
2. <span data-ttu-id="83adf-120">Aprire il gruppo **programmi** .</span><span class="sxs-lookup"><span data-stu-id="83adf-120">Open the **Programs** group.</span></span>  
  
3. <span data-ttu-id="83adf-121">In **programmi e funzionalità**fare clic **su attivazione o disattivazione delle funzionalità Windows**.</span><span class="sxs-lookup"><span data-stu-id="83adf-121">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4. <span data-ttu-id="83adf-122">Viene visualizzata la finestra di dialogo **controllo dell'account utente** .</span><span class="sxs-lookup"><span data-stu-id="83adf-122">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="83adf-123">Scegliere **Continua**.</span><span class="sxs-lookup"><span data-stu-id="83adf-123">Click **Continue**.</span></span>  
  
5. <span data-ttu-id="83adf-124">Verrà visualizzata la finestra di dialogo **funzionalità Windows** .</span><span class="sxs-lookup"><span data-stu-id="83adf-124">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="83adf-125">Espandere l'elemento denominato **Internet Information Services**.</span><span class="sxs-lookup"><span data-stu-id="83adf-125">Expand the item labeled **Internet Information Services**.</span></span>  
  
6. <span data-ttu-id="83adf-126">Espandere l'elemento denominato **World Wide Web Services**.</span><span class="sxs-lookup"><span data-stu-id="83adf-126">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7. <span data-ttu-id="83adf-127">Espandere l'elemento funzionalità di **sviluppo dell'applicazione**.</span><span class="sxs-lookup"><span data-stu-id="83adf-127">Expand the item labeled **Application Development Features**.</span></span>  
  
8. <span data-ttu-id="83adf-128">Verificare che gli elementi seguenti siano selezionati:</span><span class="sxs-lookup"><span data-stu-id="83adf-128">Make sure the following items are selected:</span></span>  
  
    1. <span data-ttu-id="83adf-129">**Estendibilità .NET**</span><span class="sxs-lookup"><span data-stu-id="83adf-129">**.NET Extensibility**</span></span>  
  
    2. <span data-ttu-id="83adf-130">**ASP.NET 2.0**</span><span class="sxs-lookup"><span data-stu-id="83adf-130">**ASP.NET**</span></span>  
  
    3. <span data-ttu-id="83adf-131">**Estensioni ISAPI**</span><span class="sxs-lookup"><span data-stu-id="83adf-131">**ISAPI Extensions**</span></span>  
  
    4. <span data-ttu-id="83adf-132">**Filtri ISAPI**</span><span class="sxs-lookup"><span data-stu-id="83adf-132">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="83adf-133">Nell'elemento denominato **World Wide Web Services**espandere **funzionalità HTTP comuni**.</span><span class="sxs-lookup"><span data-stu-id="83adf-133">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
10. <span data-ttu-id="83adf-134">Verificare che sia selezionato **contenuto statico** .</span><span class="sxs-lookup"><span data-stu-id="83adf-134">Make sure **Static Content** is selected.</span></span>  
  
11. <span data-ttu-id="83adf-135">Nell'elemento denominato **World Wide Web Services**espandere **sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="83adf-135">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
12. <span data-ttu-id="83adf-136">Assicurarsi che sia selezionata **l'opzione autenticazione di Windows** .</span><span class="sxs-lookup"><span data-stu-id="83adf-136">Make sure that **Windows Authentication** is selected.</span></span>  
  
13. <span data-ttu-id="83adf-137">Nella directory **Internet Information Services** espandere l'elemento **strumenti di gestione Web**, quindi selezionare **console di gestione IIS**.</span><span class="sxs-lookup"><span data-stu-id="83adf-137">Under the **Internet Information Services** directory, expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
14. <span data-ttu-id="83adf-138">Espandere l'elemento compatibilità di **gestione con IIS 6**, quindi selezionare **strumenti di script di IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="83adf-138">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="83adf-139">Nella directory **Internet Information Services** espandere l'elemento con etichetta **Microsoft .NET Framework 3.5.1**, quindi selezionare **Windows Communication Foundation attivazione http**.</span><span class="sxs-lookup"><span data-stu-id="83adf-139">Under the **Internet Information Services** directory, expand the item labeled **Microsoft .NET Framework 3.5.1**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="83adf-140">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="83adf-140">Click **OK**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-server-2008"></a><span data-ttu-id="83adf-141">Installazione di IIS versione 7.0 in Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="83adf-141">To install IIS version 7.0 on Windows Server 2008</span></span>  
  
1. <span data-ttu-id="83adf-142">In **Server Manager**selezionare **ruoli**.</span><span class="sxs-lookup"><span data-stu-id="83adf-142">From **Server Manager**, select **Roles**.</span></span> <span data-ttu-id="83adf-143">In **Riepilogo ruoli**fare clic su **Aggiungi ruoli**.</span><span class="sxs-lookup"><span data-stu-id="83adf-143">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2. <span data-ttu-id="83adf-144">Fare clic su **Avanti** per visualizzare la finestra di dialogo **Selezione ruoli server** .</span><span class="sxs-lookup"><span data-stu-id="83adf-144">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3. <span data-ttu-id="83adf-145">Selezionare **server applicazioni** dall'elenco **ruoli** , quindi fare clic due volte su **Avanti** per visualizzare la finestra di dialogo **Selezione servizi ruolo** per il ruolo server applicazioni.</span><span class="sxs-lookup"><span data-stu-id="83adf-145">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4. <span data-ttu-id="83adf-146">Selezionare la casella di controllo **server Web (IIS)** .</span><span class="sxs-lookup"><span data-stu-id="83adf-146">Select **Web Server (IIS)** check box.</span></span> <span data-ttu-id="83adf-147">Se viene richiesto di installare servizi ruolo e funzionalità aggiuntivi, fare clic su **Aggiungi funzionalità necessarie**.</span><span class="sxs-lookup"><span data-stu-id="83adf-147">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="83adf-148">Fare clic due volte su **Avanti** per visualizzare la finestra di dialogo **Selezione servizi ruolo** per il ruolo server Web (IIS).</span><span class="sxs-lookup"><span data-stu-id="83adf-148">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5. <span data-ttu-id="83adf-149">Espandere **strumenti di gestione**, quindi espandere **compatibilità di gestione con IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="83adf-149">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="83adf-150">Selezionare **strumenti di script di IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="83adf-150">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="83adf-151">Se viene richiesto di installare servizi ruolo e funzionalità aggiuntivi, fare clic su **Aggiungi servizi ruolo necessari**.</span><span class="sxs-lookup"><span data-stu-id="83adf-151">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="83adf-152">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="83adf-152">Click **Next**.</span></span>  
  
6. <span data-ttu-id="83adf-153">Se il riepilogo delle selezioni è corretto, fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="83adf-153">If the summary of selections is correct, click **Install**.</span></span>  
  
7. <span data-ttu-id="83adf-154">Al termine dell'installazione, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="83adf-154">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-vista"></a><span data-ttu-id="83adf-155">Per installare IIS sulla versione 7.0 in Windows Vista</span><span class="sxs-lookup"><span data-stu-id="83adf-155">To install IIS version 7.0 on Windows Vista</span></span>  
  
1. <span data-ttu-id="83adf-156">Fare clic sul pulsante Start, quindi scegliere Pannello di controllo.</span><span class="sxs-lookup"><span data-stu-id="83adf-156">Click Start, and then click Control Panel.</span></span>  
  
2. <span data-ttu-id="83adf-157">Selezionare il gruppo **programmi** .</span><span class="sxs-lookup"><span data-stu-id="83adf-157">Select the **Programs** group.</span></span>  
  
3. <span data-ttu-id="83adf-158">In **programmi e funzionalità**fare clic **su attivazione o disattivazione delle funzionalità Windows**.</span><span class="sxs-lookup"><span data-stu-id="83adf-158">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4. <span data-ttu-id="83adf-159">Viene visualizzata la finestra di dialogo **controllo dell'account utente** .</span><span class="sxs-lookup"><span data-stu-id="83adf-159">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="83adf-160">Scegliere **Continua**.</span><span class="sxs-lookup"><span data-stu-id="83adf-160">Click **Continue**.</span></span>  
  
5. <span data-ttu-id="83adf-161">Verrà visualizzata la finestra di dialogo **funzionalità Windows** .</span><span class="sxs-lookup"><span data-stu-id="83adf-161">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="83adf-162">Espandere l'elemento denominato **Internet Information Services**.</span><span class="sxs-lookup"><span data-stu-id="83adf-162">Expand the item labeled **Internet Information Services**.</span></span>  
  
6. <span data-ttu-id="83adf-163">Espandere l'elemento denominato **World Wide Web Services**.</span><span class="sxs-lookup"><span data-stu-id="83adf-163">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7. <span data-ttu-id="83adf-164">Espandere l'elemento funzionalità di **sviluppo dell'applicazione**.</span><span class="sxs-lookup"><span data-stu-id="83adf-164">Expand the item labeled **Application Development Features**.</span></span>  
  
8. <span data-ttu-id="83adf-165">Verificare che gli elementi seguenti siano selezionati:</span><span class="sxs-lookup"><span data-stu-id="83adf-165">Make sure the following items are selected:</span></span>  
  
    1. <span data-ttu-id="83adf-166">**Estendibilità .NET**</span><span class="sxs-lookup"><span data-stu-id="83adf-166">**.NET Extensibility**</span></span>  
  
    2. <span data-ttu-id="83adf-167">**ASP.NET 2.0**</span><span class="sxs-lookup"><span data-stu-id="83adf-167">**ASP.NET**</span></span>  
  
    3. <span data-ttu-id="83adf-168">**Estensioni ISAPI**</span><span class="sxs-lookup"><span data-stu-id="83adf-168">**ISAPI Extensions**</span></span>  
  
    4. <span data-ttu-id="83adf-169">**Filtri ISAPI**</span><span class="sxs-lookup"><span data-stu-id="83adf-169">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="83adf-170">Espandere l'elemento strumenti di **gestione Web**, quindi selezionare Console di **Gestione IIS**.</span><span class="sxs-lookup"><span data-stu-id="83adf-170">Expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
10. <span data-ttu-id="83adf-171">Nell'elemento denominato **World Wide Web Services**espandere **funzionalità HTTP comuni**.</span><span class="sxs-lookup"><span data-stu-id="83adf-171">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
11. <span data-ttu-id="83adf-172">Verificare che sia selezionato **contenuto statico** .</span><span class="sxs-lookup"><span data-stu-id="83adf-172">Make sure **Static Content** is selected.</span></span>  
  
12. <span data-ttu-id="83adf-173">Nell'elemento denominato **World Wide Web Services**espandere **sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="83adf-173">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
13. <span data-ttu-id="83adf-174">Assicurarsi che sia selezionata **l'autenticazione di Windows** .</span><span class="sxs-lookup"><span data-stu-id="83adf-174">Make sure **Windows Authentication** is selected.</span></span>  
  
14. <span data-ttu-id="83adf-175">Espandere l'elemento compatibilità di **gestione con IIS 6**, quindi selezionare **strumenti di script di IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="83adf-175">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="83adf-176">Espandere l'elemento con etichetta **Microsoft .NET Framework 3,0**, quindi selezionare **Windows Communication Foundation attivazione http**.</span><span class="sxs-lookup"><span data-stu-id="83adf-176">Expand the item labeled **Microsoft .NET Framework 3.0**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="83adf-177">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="83adf-177">Click **OK**.</span></span>  
  
### <a name="to-install-iis-version-60-on-windows-server-2003"></a><span data-ttu-id="83adf-178">Per installare IIS versione 6.0 in Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="83adf-178">To install IIS version 6.0 on Windows Server 2003</span></span>  
  
1. <span data-ttu-id="83adf-179">In **Gestisci il server**fare clic su **Aggiungi o Rimuovi un ruolo**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="83adf-179">From **Manage Your Server**, click **Add or remove a role**, and then click **Next**.</span></span>  
  
2. <span data-ttu-id="83adf-180">Selezionare **server applicazioni (IIS, ASP.NET)** nell'elenco **ruolo server** , quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="83adf-180">Select **Application server (IIS, ASP.NET)** from the **Server Role** list, and then click **Next**.</span></span>  
  
3. <span data-ttu-id="83adf-181">Selezionare la casella di controllo **abilita ASP.NET** , quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="83adf-181">Select **Enable ASP.NET** check box, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="83adf-182">Se il riepilogo delle selezioni è corretto, fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="83adf-182">If the summary of selections is correct, click Next.</span></span>  
  
### <a name="to-install-iis-version-51-on-windows-xp-with-service-pack-2-and-service-pack-3-installed"></a><span data-ttu-id="83adf-183">Per installare IIS versione 5.1 in Windows XP con Service Pack 2 e Service Pack 3 installati</span><span class="sxs-lookup"><span data-stu-id="83adf-183">To install IIS version 5.1 on Windows XP with Service Pack 2 and Service Pack 3 installed</span></span>  
  
1. <span data-ttu-id="83adf-184">Nel pannello di controllo, fare clic su **Installazione applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="83adf-184">In Control Panel, click **Add or Remove Programs**.</span></span>  
  
2. <span data-ttu-id="83adf-185">Nella finestra di dialogo **Installazione applicazioni** fare clic su **Aggiungi/Rimuovi componenti di Windows**.</span><span class="sxs-lookup"><span data-stu-id="83adf-185">In the **Add or Remove Programs** dialog box, click **Add/Remove Windows Components**.</span></span>  
  
3. <span data-ttu-id="83adf-186">Nella **procedura guidata componenti di Windows**selezionare la casella di controllo **Internet Information Services (IIS)** , quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="83adf-186">In the **Windows Components Wizard**, select the **Internet Information Services (IIS)** check box, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="83adf-187">Se viene visualizzata la finestra di dialogo **file necessari** , inserire il disco di installazione del sistema operativo, passare alla cartella i386, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="83adf-187">If the **Files Needed** dialog box is displayed, insert your operating system installation disc, browse to the i386 folder, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="83adf-188">Al termine dell'installazione, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="83adf-188">When installation completes, click **Finish**.</span></span>  
  
6. <span data-ttu-id="83adf-189">Chiudere la finestra di dialogo **Installazione applicazioni** e quindi chiudere il **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="83adf-189">Close the **Add or Remove Programs** dialog box, and then close **Control Panel**.</span></span>  
  
### <a name="to-verify-the-installation-of-iis-and-aspnet"></a><span data-ttu-id="83adf-190">Per verificare l'installazione di IIS e ASP.NET</span><span class="sxs-lookup"><span data-stu-id="83adf-190">To verify the installation of IIS and ASP.NET</span></span>  
  
1. <span data-ttu-id="83adf-191">Salvare il file HTML trovato alla fine di questo argomento nella directory radice \InetPub\wwwroot e rinominarlo Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="83adf-191">Save the HTML file found at the end of this topic in the root \InetPub\wwwroot directory and name it Default.aspx.</span></span>  
  
2. <span data-ttu-id="83adf-192">Aprire una finestra di browser.</span><span class="sxs-lookup"><span data-stu-id="83adf-192">Open a browser window.</span></span>  
  
3. <span data-ttu-id="83adf-193">Digitare `http://localhost/Default.aspx` nella casella Address, quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="83adf-193">Type `http://localhost/Default.aspx` in the address box, and then press ENTER.</span></span>  
  
4. <span data-ttu-id="83adf-194">Dovrebbe venire visualizzata una pagina Web contenente il testo "Hello World".</span><span class="sxs-lookup"><span data-stu-id="83adf-194">A Web page with the text "Hello World" should appear.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="83adf-195">Ogni volta che si installa una nuova versione del .NET Framework, è necessario ripetere la registrazione di aspnet_isapi come estensione del servizio Web per IIS.</span><span class="sxs-lookup"><span data-stu-id="83adf-195">Each time you install a new version of the .NET Framework, you must re-register aspnet_isapi as a Web service extension for IIS.</span></span> <span data-ttu-id="83adf-196">A tale scopo, eseguire il comando `aspnet_regiis –I –enable`.</span><span class="sxs-lookup"><span data-stu-id="83adf-196">To do so, issue the `aspnet_regiis –I –enable` command.</span></span>  
  
## <a name="sample-code"></a><span data-ttu-id="83adf-197">Codice di esempio</span><span class="sxs-lookup"><span data-stu-id="83adf-197">Sample Code</span></span>  
  
```xml  
<html>  
   <body>  
       <form >  
           <h3> Hello World  
           </h3>  
       </form>  
   </body>  
</html>  
```
