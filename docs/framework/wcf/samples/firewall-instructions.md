---
title: Istruzioni del firewall
ms.date: 03/30/2017
ms.assetid: a7dc429f-65ac-4faf-974a-77d5fb977fe1
ms.openlocfilehash: e2c4dd8e784599a5e110e7454d9d0e709cbc5776
ms.sourcegitcommit: 8c99457955fc31785b36b3330c4ab6ce7984a7ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/29/2019
ms.locfileid: "75544786"
---
# <a name="firewall-instructions"></a><span data-ttu-id="21ee1-102">Istruzioni del firewall</span><span class="sxs-lookup"><span data-stu-id="21ee1-102">Firewall Instructions</span></span>
<span data-ttu-id="21ee1-103">È necessario abilitare più porte o programmi nel firewall in modo che gli esempi di Windows Communication Foundation (WCF) possano funzionare.</span><span class="sxs-lookup"><span data-stu-id="21ee1-103">You must enable several ports or programs in the firewall so that the Windows Communication Foundation (WCF) samples can function.</span></span> <span data-ttu-id="21ee1-104">In molti degli esempi la comunicano avviene tramite le porte comprese nell'intervallo 8000-8003 e la porta 9000.</span><span class="sxs-lookup"><span data-stu-id="21ee1-104">Many of the samples communicate by using ports in the range 8000-8003, and port 9000.</span></span> <span data-ttu-id="21ee1-105">Il firewall viene attivato per impostazione predefinita e impedisce l'accesso a queste porte.</span><span class="sxs-lookup"><span data-stu-id="21ee1-105">The firewall is turned on by default and prevents access to these ports.</span></span> <span data-ttu-id="21ee1-106">Per abilitare il firewall per gli esempi, completare una delle procedure descritte di seguito, a seconda dei requisiti e dell’ambiente di sicurezza:</span><span class="sxs-lookup"><span data-stu-id="21ee1-106">To enable the firewall for the samples, complete one of the following procedures, depending on your requirements and security environment:</span></span>  
  
- <span data-ttu-id="21ee1-107">Opzione 1: abilitazione degli esempi in modo interattivo durante l’esecuzione.</span><span class="sxs-lookup"><span data-stu-id="21ee1-107">Option 1: Interactively enable samples while running.</span></span> <span data-ttu-id="21ee1-108">Non apportare nessuna modifica alla configurazione del firewall in anticipo e procedere con l’avvio e l’esecuzione degli esempi.</span><span class="sxs-lookup"><span data-stu-id="21ee1-108">Make no advance changes to your firewall configuration and proceed to start building and running the samples.</span></span> <span data-ttu-id="21ee1-109">Quando viene eseguito un esempio, viene visualizzata una finestra di dialogo **avviso di sicurezza di Windows** .</span><span class="sxs-lookup"><span data-stu-id="21ee1-109">When a sample is run, a **Windows Security Alert** dialog box appears.</span></span> <span data-ttu-id="21ee1-110">Il programma di esempio in questione può essere quindi aggiunto, in modo interattivo, a un elenco sbloccato.</span><span class="sxs-lookup"><span data-stu-id="21ee1-110">The sample program in question can then be added interactively to an unblocked list.</span></span> <span data-ttu-id="21ee1-111">Questa procedura può richiedere il riavvio dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="21ee1-111">With this procedure, you may have to then restart the sample.</span></span>  
  
- <span data-ttu-id="21ee1-112">Opzione 2: abilitazione dei programmi di esempio in anticipo.</span><span class="sxs-lookup"><span data-stu-id="21ee1-112">Option 2: Enable sample programs in advance.</span></span> <span data-ttu-id="21ee1-113">Avviare l'applet del **Pannello di controllo Windows Firewall** e abilitare i programmi di esempio che si intende eseguire.</span><span class="sxs-lookup"><span data-stu-id="21ee1-113">Start the **Windows Firewall Control Panel** applet and enable the sample programs you plan to run.</span></span> <span data-ttu-id="21ee1-114">Per creare file eseguibili, è necessario prima compilare i programmi.</span><span class="sxs-lookup"><span data-stu-id="21ee1-114">You must build the programs first so the executable files exist.</span></span> <span data-ttu-id="21ee1-115">Informazioni più dettagliate sono descritte nella procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="21ee1-115">You can find more detailed instructions in the following procedure.</span></span>  
  
- <span data-ttu-id="21ee1-116">Opzione 3: abilitazione dell’intervallo delle porte in anticipo.</span><span class="sxs-lookup"><span data-stu-id="21ee1-116">Option 3: Enable a port range in advance.</span></span> <span data-ttu-id="21ee1-117">Avviare l' **Windows Firewall** applet del **Pannello di controllo** e abilitare le porte 80, 443, 8000-8003 e 9000, utilizzate dagli esempi.</span><span class="sxs-lookup"><span data-stu-id="21ee1-117">Start the **Windows Firewall** **Control Panel** applet and enable ports 80, 443, 8000-8003 and 9000, which are used by the samples.</span></span> <span data-ttu-id="21ee1-118">Informazioni più dettagliate sono descritte nella procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="21ee1-118">You can find more detailed instructions in the following procedure.</span></span> <span data-ttu-id="21ee1-119">Questa opzione è meno sicura rispetto alle altre in quanto consente a qualsiasi programma di utilizzare queste porte, non solo agli esempi.</span><span class="sxs-lookup"><span data-stu-id="21ee1-119">This option is less secure than the others because it allows any program to use these ports, not just the samples.</span></span>  
  
 <span data-ttu-id="21ee1-120">In caso di dubbi su quale procedura utilizzare, scegliere la prima opzione.</span><span class="sxs-lookup"><span data-stu-id="21ee1-120">If you are unsure of which procedure to use, choose the first option.</span></span> <span data-ttu-id="21ee1-121">Se si sta eseguendo un firewall di un altro fornitore, potrebbe essere necessario apportare modifiche simili.</span><span class="sxs-lookup"><span data-stu-id="21ee1-121">If you are running a firewall from another vendor, you might need to make similar changes.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="21ee1-122">La modifica della configurazione del firewall influisce sulla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="21ee1-122">Changing your firewall configuration affects your security.</span></span> <span data-ttu-id="21ee1-123">È consigliabile registrare le modifiche apportate e rimuoverle una volta completate le operazioni con gli esempi.</span><span class="sxs-lookup"><span data-stu-id="21ee1-123">It is recommended that you record the changes you make and remove them when you are finished working with the samples.</span></span>  
  
### <a name="to-enable-samples-programs-in-advance"></a><span data-ttu-id="21ee1-124">Abilitazione dei programmi di esempio in anticipo.</span><span class="sxs-lookup"><span data-stu-id="21ee1-124">To enable samples programs in advance</span></span>  
  
1. <span data-ttu-id="21ee1-125">Compilare l'esempio.</span><span class="sxs-lookup"><span data-stu-id="21ee1-125">Build the sample.</span></span>  
  
2. <span data-ttu-id="21ee1-126">Fare clic sul pulsante **Start**, scegliere **esegui**e digitare `firewall.cpl`.</span><span class="sxs-lookup"><span data-stu-id="21ee1-126">Click **Start**, click **Run**, and type `firewall.cpl`.</span></span> <span data-ttu-id="21ee1-127">Verrà visualizzata l'applet del **Pannello di controllo Windows Firewall** .</span><span class="sxs-lookup"><span data-stu-id="21ee1-127">This opens the **Windows Firewall Control Panel** applet.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="21ee1-128">Per modificare le impostazioni del firewall ed eseguire gli esempi che richiedono la possibilità di comunicare con Windows Firewall, è necessario disporre delle autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="21ee1-128">You must have permission to change the Firewall settings to run samples that require the ability to communicate through the Windows Firewall.</span></span> <span data-ttu-id="21ee1-129">Se alcune impostazioni del firewall non sono disponibili e il computer è connesso a un dominio, è possibile che queste impostazioni vengano controllate dall'amministratore di sistema tramite Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="21ee1-129">If some firewall settings are unavailable and your computer is connected to a domain, your system administrator might be controlling these settings through Group Policy.</span></span>  
  
3. <span data-ttu-id="21ee1-130">Completare uno dei passaggi operativi specifici seguente per consentire a un programma l'accesso con Windows Firewall:</span><span class="sxs-lookup"><span data-stu-id="21ee1-130">Complete one of the following operating specific steps to allow a program through the Windows Firewall:</span></span>  
  
    - <span data-ttu-id="21ee1-131">In Windows 7 o Windows Server 2008 R2 fare clic su **Consenti programma o funzionalità tramite Windows Firewall**.</span><span class="sxs-lookup"><span data-stu-id="21ee1-131">On Windows 7 or Windows Server 2008 r2, click **Allow a program or feature through Windows Firewall**.</span></span> <span data-ttu-id="21ee1-132">Fare clic su **Cambia impostazioni**, Consenti **un altro programma...** .</span><span class="sxs-lookup"><span data-stu-id="21ee1-132">Click **Change Settings**, Allow **Another Program…**.</span></span>  
  
    - <span data-ttu-id="21ee1-133">In Windows Vista o Windows Server 2008, fare clic su **Consenti programma tramite Windows Firewall**.</span><span class="sxs-lookup"><span data-stu-id="21ee1-133">On Windows Vista or Windows Server 2008, click **Allow a program through Windows Firewall**.</span></span>  
  
4. <span data-ttu-id="21ee1-134">Nella scheda **eccezioni** fare clic su **Aggiungi programma**.</span><span class="sxs-lookup"><span data-stu-id="21ee1-134">On the **Exceptions** tab, click **Add Program**.</span></span>  
  
5. <span data-ttu-id="21ee1-135">Fare clic sul pulsante **Sfoglia** e selezionare il file eseguibile dell'esempio che si intende eseguire.</span><span class="sxs-lookup"><span data-stu-id="21ee1-135">Click the **Browse** button and select the executable file of the sample you plan to run.</span></span>  
  
6. <span data-ttu-id="21ee1-136">Ripetere i passaggi 4 e 5 fino a quando non sono stati aggiunti i file eseguibili di tutti gli esempi che si prevede di eseguire.</span><span class="sxs-lookup"><span data-stu-id="21ee1-136">Repeat steps 4 and 5 until you have added the executable files of all the samples you plan to run.</span></span>  
  
7. <span data-ttu-id="21ee1-137">Fare clic su **OK** per chiudere l'applet del firewall.</span><span class="sxs-lookup"><span data-stu-id="21ee1-137">Click **OK** to close the firewall applet.</span></span>  
  
### <a name="to-enable-a-port-range-in-advance"></a><span data-ttu-id="21ee1-138">Abilitazione di un intervallo delle porte in anticipo.</span><span class="sxs-lookup"><span data-stu-id="21ee1-138">To enable a port range in advance</span></span>  
  
1. <span data-ttu-id="21ee1-139">Fare clic sul pulsante **Start**, scegliere **esegui**e digitare `firewall.cpl`.</span><span class="sxs-lookup"><span data-stu-id="21ee1-139">Click **Start**, click **Run**, and type `firewall.cpl`.</span></span> <span data-ttu-id="21ee1-140">Verrà visualizzata l'applet del **Pannello di controllo Windows Firewall** .</span><span class="sxs-lookup"><span data-stu-id="21ee1-140">This opens the **Windows Firewall Control Panel** applet.</span></span>  
  
2. <span data-ttu-id="21ee1-141">In Windows 7 o Windows Server 2008 R2 attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="21ee1-141">On Windows 7 or Windows Server 2008 R2, follow these steps.</span></span>  
  
    1. <span data-ttu-id="21ee1-142">Fare clic su **Impostazioni avanzate** nella colonna a sinistra della finestra di Windows Firewall.</span><span class="sxs-lookup"><span data-stu-id="21ee1-142">Click **Advanced settings** in the left column of the Windows Firewall window.</span></span>  
  
    2. <span data-ttu-id="21ee1-143">Fare clic su **regole in ingresso** nella colonna a sinistra.</span><span class="sxs-lookup"><span data-stu-id="21ee1-143">Click **Inbound Rules** in the left column.</span></span>  
  
    3. <span data-ttu-id="21ee1-144">Fare clic su **nuove regole** nella colonna a destra.</span><span class="sxs-lookup"><span data-stu-id="21ee1-144">Click **New Rules** in the right column.</span></span>  
  
    4. <span data-ttu-id="21ee1-145">Selezionare **porta** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="21ee1-145">Select **Port** and click **next**.</span></span>  
  
    5. <span data-ttu-id="21ee1-146">Selezionare **TCP** e immettere `8000, 8001, 8002, 8003, 9000, 80, 443` nel campo **porte locali specifiche** .</span><span class="sxs-lookup"><span data-stu-id="21ee1-146">Select **TCP** and enter `8000, 8001, 8002, 8003, 9000, 80, 443` in the **Specific local ports** field.</span></span>  
  
    6. <span data-ttu-id="21ee1-147">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="21ee1-147">Click **Next**.</span></span>  
  
    7. <span data-ttu-id="21ee1-148">Selezionare **Consenti la connessione**e fare clic su **Avanti** .</span><span class="sxs-lookup"><span data-stu-id="21ee1-148">Select **Allow the connection**, and click **Next** .</span></span>  
  
    8. <span data-ttu-id="21ee1-149">Selezionare **dominio** e **privato**e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="21ee1-149">Select **Domain** and **Private**, and click **Next**.</span></span>  
  
    9. <span data-ttu-id="21ee1-150">Assegnare alla regola il nome `WCF-WF 4.0 Samples`, quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="21ee1-150">Name this rule `WCF-WF 4.0 Samples`, and click **Finish**.</span></span>  
  
    10. <span data-ttu-id="21ee1-151">Fare clic su **regole in uscita** e ripetere i passaggi da c a h.</span><span class="sxs-lookup"><span data-stu-id="21ee1-151">Click **Outbound Rules** and repeat steps c to h.</span></span>  
  
3. <span data-ttu-id="21ee1-152">In Windows Vista o Windows Server 2008, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="21ee1-152">On Windows Vista or Windows Server 2008, follow these steps.</span></span>  
  
    1. <span data-ttu-id="21ee1-153">Fare clic su **Consenti programma con Windows Firewall**.</span><span class="sxs-lookup"><span data-stu-id="21ee1-153">Click **Allow a program through Windows Firewall**.</span></span>  
  
    2. <span data-ttu-id="21ee1-154">Nella scheda **eccezioni** fare clic su **Aggiungi porta**.</span><span class="sxs-lookup"><span data-stu-id="21ee1-154">On the **Exceptions** tab, click **Add Port**.</span></span>  
  
    3. <span data-ttu-id="21ee1-155">Immettere un nome, immettere 8000 come numero di porta e selezionare l'opzione **TCP** .</span><span class="sxs-lookup"><span data-stu-id="21ee1-155">Enter a name, enter 8000 as the port number, and select the **TCP** option.</span></span>  
  
    4. <span data-ttu-id="21ee1-156">Fare clic sul pulsante **Cambia ambito** , selezionare l'opzione solo **rete** (subnet) e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="21ee1-156">Click the **Change Scope** button, select the **My Network** (subnet) only option, and click **OK**.</span></span>  
  
    5. <span data-ttu-id="21ee1-157">Ripetere i passaggi da B a D per le porte 8001, 8002, 8003, 9000, 80 e 443.</span><span class="sxs-lookup"><span data-stu-id="21ee1-157">Repeat steps b to d for ports 8001, 8002, 8003, 9000, 80, and 443.</span></span>  
  
4. <span data-ttu-id="21ee1-158">Fare clic su **OK** per chiudere l'applet del firewall.</span><span class="sxs-lookup"><span data-stu-id="21ee1-158">Click **OK** to close the firewall applet.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="21ee1-159">Rimuovere qualsiasi eccezione del firewall una volta completate le operazioni con gli esempi.</span><span class="sxs-lookup"><span data-stu-id="21ee1-159">Remove any firewall exceptions when you are finished working with the samples.</span></span> <span data-ttu-id="21ee1-160">A tale scopo, aprire l' **Windows Firewall** applet del pannello di controllo e rimuovere tutti i programmi o le voci di porta aggiunti dalle procedure precedenti.</span><span class="sxs-lookup"><span data-stu-id="21ee1-160">To do so, open the **Windows Firewall Control Panel** applet and remove any programs or port entries that were added by the previous procedures.</span></span>
