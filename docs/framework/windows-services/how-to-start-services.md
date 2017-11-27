---
title: 'Procedura: avviare servizi'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, starting
- services, starting
ms.assetid: 9ea77955-2d96-4c3d-913c-14db7604cdad
caps.latest.revision: "16"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: e4f93da8a2a5be00d798d64caba0f54bfd71ceb2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-start-services"></a><span data-ttu-id="38f11-102">Procedura: avviare servizi</span><span class="sxs-lookup"><span data-stu-id="38f11-102">How to: Start Services</span></span>
<span data-ttu-id="38f11-103">Dopo l'installazione di un servizio, è necessario avviarlo.</span><span class="sxs-lookup"><span data-stu-id="38f11-103">After a service is installed, it must be started.</span></span> <span data-ttu-id="38f11-104">Avvio delle chiamate di <xref:System.ServiceProcess.ServiceBase.OnStart%2A> metodo nella classe del servizio.</span><span class="sxs-lookup"><span data-stu-id="38f11-104">Starting calls the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method on the service class.</span></span> <span data-ttu-id="38f11-105">In genere, il <xref:System.ServiceProcess.ServiceBase.OnStart%2A> metodo definisce le operazioni che il servizio eseguirà.</span><span class="sxs-lookup"><span data-stu-id="38f11-105">Usually, the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method defines the useful work the service will perform.</span></span> <span data-ttu-id="38f11-106">Dopo l'avvio di un servizio rimane attivo fino a quando non è sospeso o interrotto manualmente.</span><span class="sxs-lookup"><span data-stu-id="38f11-106">After a service starts, it remains active until it is manually paused or stopped.</span></span>  
  
 <span data-ttu-id="38f11-107">Servizi possono essere impostati per avviare automaticamente o manualmente.</span><span class="sxs-lookup"><span data-stu-id="38f11-107">Services can be set up to start automatically or manually.</span></span> <span data-ttu-id="38f11-108">Verrà avviato un servizio che viene avviato automaticamente quando il computer in cui è installato è stato riavviato oppure prima attivato.</span><span class="sxs-lookup"><span data-stu-id="38f11-108">A service that starts automatically will be started when the computer on which it is installed is rebooted or first turned on.</span></span> <span data-ttu-id="38f11-109">Un utente deve avviare un servizio che viene avviato manualmente.</span><span class="sxs-lookup"><span data-stu-id="38f11-109">A user must start a service that starts manually.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38f11-110">Per impostazione predefinita, i servizi creati con [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] sono impostate per l'avvio manuale.</span><span class="sxs-lookup"><span data-stu-id="38f11-110">By default, services created with [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] are set to start manually.</span></span>  
  
 <span data-ttu-id="38f11-111">Esistono diversi modi, è possibile avviare manualmente un servizio, ovvero da **Esplora Server**, dal **Gestione controllo servizi**, o dal codice utilizzando un componente denominato il <xref:System.ServiceProcess.ServiceController>.</span><span class="sxs-lookup"><span data-stu-id="38f11-111">There are several ways you can manually start a service — from **Server Explorer**, from the **Services Control Manager**, or from code using a component called the <xref:System.ServiceProcess.ServiceController>.</span></span>  
  
 <span data-ttu-id="38f11-112">Impostare il <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> proprietà la <xref:System.ServiceProcess.ServiceInstaller> classe per determinare se un servizio deve essere avviato manualmente o automaticamente.</span><span class="sxs-lookup"><span data-stu-id="38f11-112">You set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property on the <xref:System.ServiceProcess.ServiceInstaller> class to determine whether a service should be started manually or automatically.</span></span>  
  
### <a name="to-specify-how-a-service-should-start"></a><span data-ttu-id="38f11-113">Per specificare la modalità in cui deve iniziare un servizio</span><span class="sxs-lookup"><span data-stu-id="38f11-113">To specify how a service should start</span></span>  
  
1.  <span data-ttu-id="38f11-114">Dopo aver creato il servizio, aggiungere i programmi di installazione necessari per tale.</span><span class="sxs-lookup"><span data-stu-id="38f11-114">After creating your service, add the necessary installers for it.</span></span> <span data-ttu-id="38f11-115">Per ulteriori informazioni, vedere [procedura: aggiungere programmi di installazione per l'applicazione di servizio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="38f11-115">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
2.  <span data-ttu-id="38f11-116">Nella finestra di progettazione, fare clic sul programma di installazione per il servizio in uso.</span><span class="sxs-lookup"><span data-stu-id="38f11-116">In the designer, click the service installer for the service you are working with.</span></span>  
  
3.  <span data-ttu-id="38f11-117">Nel **proprietà** finestra, impostare il <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> proprietà su uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="38f11-117">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to one of the following:</span></span>  
  
    |<span data-ttu-id="38f11-118">Per avviare il servizio</span><span class="sxs-lookup"><span data-stu-id="38f11-118">To have your service install</span></span>|<span data-ttu-id="38f11-119">Impostare questo valore</span><span class="sxs-lookup"><span data-stu-id="38f11-119">Set this value</span></span>|  
    |----------------------------------|--------------------|  
    |<span data-ttu-id="38f11-120">Quando si riavvia il computer</span><span class="sxs-lookup"><span data-stu-id="38f11-120">When the computer is restarted</span></span>|<span data-ttu-id="38f11-121">**Automatico**</span><span class="sxs-lookup"><span data-stu-id="38f11-121">**Automatic**</span></span>|  
    |<span data-ttu-id="38f11-122">Avvio del servizio da parte di un'azione esplicita dell'utente</span><span class="sxs-lookup"><span data-stu-id="38f11-122">When an explicit user action starts the service</span></span>|<span data-ttu-id="38f11-123">**Manuale**</span><span class="sxs-lookup"><span data-stu-id="38f11-123">**Manual**</span></span>|  
  
    > [!TIP]
    >  <span data-ttu-id="38f11-124">Per impedire che il servizio venga avviato, è possibile impostare il <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> proprietà **disabilitato**.</span><span class="sxs-lookup"><span data-stu-id="38f11-124">To prevent your service from being started at all, you can set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to **Disabled**.</span></span> <span data-ttu-id="38f11-125">Se si desidera riavviare un server più volte e si desidera risparmiare tempo evitando i servizi che normalmente inizia avvio, è possibile farlo.</span><span class="sxs-lookup"><span data-stu-id="38f11-125">You might do this if you are going to reboot a server several times and want to save time by preventing the services that would normally start from starting up.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="38f11-126">Queste e altre proprietà può essere modificato dopo l'installazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="38f11-126">These and other properties can be changed after your service is installed.</span></span>  
  
     <span data-ttu-id="38f11-127">Esistono diversi modi, è possibile avviare un servizio che ha relativo <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> processo impostata su **manuale** : da **Esplora Server**, dal **Gestione controllo servizi di Windows**, o dal codice.</span><span class="sxs-lookup"><span data-stu-id="38f11-127">There are several ways you can start a service that has its <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> process set to **Manual** — from **Server Explorer**, from the **Windows Services Control Manager**, or from code.</span></span> <span data-ttu-id="38f11-128">È importante notare che non tutti questi metodi viene avviato effettivamente il servizio nel contesto del **Gestione controllo servizi**; **Esplora server** e metodi a livello di codice di avvio del servizio modificano effettivamente il controller.</span><span class="sxs-lookup"><span data-stu-id="38f11-128">It is important to note that not all of these methods actually start the service in the context of the **Services Control Manager**; **Server Explorer** and programmatic methods of starting the service actually manipulate the controller.</span></span>  
  
### <a name="to-manually-start-a-service-from-server-explorer"></a><span data-ttu-id="38f11-129">Per avviare manualmente un servizio da Esplora Server</span><span class="sxs-lookup"><span data-stu-id="38f11-129">To manually start a service from Server Explorer</span></span>  
  
1.  <span data-ttu-id="38f11-130">In **Esplora Server**, aggiungere il server desiderato, se non è già elencato.</span><span class="sxs-lookup"><span data-stu-id="38f11-130">In **Server Explorer**, add the server you want if it is not already listed.</span></span> <span data-ttu-id="38f11-131">Per ulteriori informazioni, vedere Procedura: accedere e inizializzare Esplora Server-Esplora Database.</span><span class="sxs-lookup"><span data-stu-id="38f11-131">For more information, see How to: Access and Initialize Server Explorer-Database Explorer.</span></span>  
  
2.  <span data-ttu-id="38f11-132">Espandere il **servizi** nodo, quindi individuare il servizio che si desidera avviare.</span><span class="sxs-lookup"><span data-stu-id="38f11-132">Expand the **Services** node, and then locate the service you want to start.</span></span>  
  
3.  <span data-ttu-id="38f11-133">Il nome del servizio di mouse e scegliere **avviare**.</span><span class="sxs-lookup"><span data-stu-id="38f11-133">Right-click the name of the service, and click **Start**.</span></span>  
  
### <a name="to-manually-start-a-service-from-services-control-manager"></a><span data-ttu-id="38f11-134">Per avviare manualmente un servizio da Gestione controllo servizi</span><span class="sxs-lookup"><span data-stu-id="38f11-134">To manually start a service from Services Control Manager</span></span>  
  
1.  <span data-ttu-id="38f11-135">Aprire il **Gestione controllo servizi** effettuando una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="38f11-135">Open the **Services Control Manager** by doing one of the following:</span></span>  
  
    -   <span data-ttu-id="38f11-136">In Windows XP e 2000 Professional, fare doppio clic su **risorse del Computer** sul desktop e quindi fare clic su **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="38f11-136">In Windows XP and 2000 Professional, right-click **My Computer** on the desktop, and then click **Manage**.</span></span> <span data-ttu-id="38f11-137">Nella finestra di dialogo che viene visualizzato, espandere il **servizi e applicazioni** nodo.</span><span class="sxs-lookup"><span data-stu-id="38f11-137">In the dialog box that appears, expand the **Services and Applications** node.</span></span>  
  
         <span data-ttu-id="38f11-138">\- oppure -</span><span class="sxs-lookup"><span data-stu-id="38f11-138">\- or -</span></span>  
  
    -   <span data-ttu-id="38f11-139">In Windows Server 2003 e Windows 2000 Server, fare clic su **avviare**, scegliere **programmi**, fare clic su **strumenti di amministrazione**, quindi fare clic su **servizi**.</span><span class="sxs-lookup"><span data-stu-id="38f11-139">In Windows Server 2003 and Windows 2000 Server, click **Start**, point to **Programs**, click **Administrative Tools**, and then click **Services**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="38f11-140">In Windows NT versione 4.0, è possibile aprire questa finestra di dialogo **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="38f11-140">In Windows NT version 4.0, you can open this dialog box from **Control Panel**.</span></span>  
  
     <span data-ttu-id="38f11-141">Viene visualizzato il servizio nel **servizi** sezione della finestra.</span><span class="sxs-lookup"><span data-stu-id="38f11-141">You should now see your service listed in the **Services** section of the window.</span></span>  
  
2.  <span data-ttu-id="38f11-142">Selezionare il servizio nell'elenco, pulsante destro del mouse e quindi fare clic su **avviare**.</span><span class="sxs-lookup"><span data-stu-id="38f11-142">Select your service in the list, right-click it, and then click **Start**.</span></span>  
  
### <a name="to-manually-start-a-service-from-code"></a><span data-ttu-id="38f11-143">Per avviare manualmente un servizio da codice</span><span class="sxs-lookup"><span data-stu-id="38f11-143">To manually start a service from code</span></span>  
  
1.  <span data-ttu-id="38f11-144">Creare un'istanza di <xref:System.ServiceProcess.ServiceController> classe e configurarlo per interagire con il servizio che si desidera amministrare.</span><span class="sxs-lookup"><span data-stu-id="38f11-144">Create an instance of the <xref:System.ServiceProcess.ServiceController> class, and configure it to interact with the service you want to administer.</span></span>  
  
2.  <span data-ttu-id="38f11-145">Chiamare il metodo <xref:System.ServiceProcess.ServiceController.Start%2A> per avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="38f11-145">Call the <xref:System.ServiceProcess.ServiceController.Start%2A> method to start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38f11-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38f11-146">See Also</span></span>  
 [<span data-ttu-id="38f11-147">Introduzione alle applicazioni di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="38f11-147">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="38f11-148">Procedura: creare servizi Windows</span><span class="sxs-lookup"><span data-stu-id="38f11-148">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [<span data-ttu-id="38f11-149">Procedura: aggiungere programmi di installazione all'applicazione di servizio</span><span class="sxs-lookup"><span data-stu-id="38f11-149">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)
