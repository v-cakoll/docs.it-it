---
title: 'Procedura: avviare servizi'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, starting
- services, starting
ms.assetid: 9ea77955-2d96-4c3d-913c-14db7604cdad
author: ghogen
manager: douge
ms.openlocfilehash: 3c8382d2e425d11dc8aa8b22e361b3cc5637744f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33516217"
---
# <a name="how-to-start-services"></a><span data-ttu-id="1bcb7-102">Procedura: avviare servizi</span><span class="sxs-lookup"><span data-stu-id="1bcb7-102">How to: Start Services</span></span>
<span data-ttu-id="1bcb7-103">Dopo l'installazione di un servizio, è necessario avviarlo.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-103">After a service is installed, it must be started.</span></span> <span data-ttu-id="1bcb7-104">Con l'avvio viene chiamato il metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> per la classe del servizio.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-104">Starting calls the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method on the service class.</span></span> <span data-ttu-id="1bcb7-105">In genere, il metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> definisce le operazioni utili che verranno eseguite dal servizio.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-105">Usually, the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method defines the useful work the service will perform.</span></span> <span data-ttu-id="1bcb7-106">Dopo l'avvio, un servizio rimane attivo fino a quando non viene sospeso o arrestato manualmente.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-106">After a service starts, it remains active until it is manually paused or stopped.</span></span>  
  
 <span data-ttu-id="1bcb7-107">I servizi possono essere configurati per l'avvio automatico o manuale.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-107">Services can be set up to start automatically or manually.</span></span> <span data-ttu-id="1bcb7-108">Un servizio con avvio automatico verrà avviato in seguito al riavvio o alla prima accensione del computer in cui è installato.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-108">A service that starts automatically will be started when the computer on which it is installed is rebooted or first turned on.</span></span> <span data-ttu-id="1bcb7-109">Un utente deve avviare un servizio con avvio manuale.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-109">A user must start a service that starts manually.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1bcb7-110">Per impostazione predefinita, i servizi creati con Visual Studio vengono impostati per l'avvio manuale.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-110">By default, services created with Visual Studio are set to start manually.</span></span>  
  
 <span data-ttu-id="1bcb7-111">Esistono diversi modi per avviare manualmente un servizio, ovvero da **Esplora server**, da **Gestione controllo servizi** o dal codice usando un componente denominato <xref:System.ServiceProcess.ServiceController>.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-111">There are several ways you can manually start a service — from **Server Explorer**, from the **Services Control Manager**, or from code using a component called the <xref:System.ServiceProcess.ServiceController>.</span></span>  
  
 <span data-ttu-id="1bcb7-112">Per determinare se un servizio deve essere avviato manualmente o automaticamente, è possibile impostare la proprietà <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> per la classe <xref:System.ServiceProcess.ServiceInstaller>.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-112">You set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property on the <xref:System.ServiceProcess.ServiceInstaller> class to determine whether a service should be started manually or automatically.</span></span>  
  
### <a name="to-specify-how-a-service-should-start"></a><span data-ttu-id="1bcb7-113">Per specificare come avviare un servizio</span><span class="sxs-lookup"><span data-stu-id="1bcb7-113">To specify how a service should start</span></span>  
  
1.  <span data-ttu-id="1bcb7-114">Dopo aver creato il servizio, aggiungere i programmi di installazione necessari.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-114">After creating your service, add the necessary installers for it.</span></span> <span data-ttu-id="1bcb7-115">Per altre informazioni, vedere [Procedura: Aggiungere programmi di installazione all'applicazione di servizio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="1bcb7-115">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
2.  <span data-ttu-id="1bcb7-116">Nella finestra di progettazione fare clic sul programma di installazione per il servizio in uso.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-116">In the designer, click the service installer for the service you are working with.</span></span>  
  
3.  <span data-ttu-id="1bcb7-117">Nella finestra **Proprietà** impostare la proprietà <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> su uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="1bcb7-117">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to one of the following:</span></span>  
  
    |<span data-ttu-id="1bcb7-118">Per installare il servizio</span><span class="sxs-lookup"><span data-stu-id="1bcb7-118">To have your service install</span></span>|<span data-ttu-id="1bcb7-119">Impostare questo valore</span><span class="sxs-lookup"><span data-stu-id="1bcb7-119">Set this value</span></span>|  
    |----------------------------------|--------------------|  
    |<span data-ttu-id="1bcb7-120">Al riavvio del computer</span><span class="sxs-lookup"><span data-stu-id="1bcb7-120">When the computer is restarted</span></span>|<span data-ttu-id="1bcb7-121">**Automatic**</span><span class="sxs-lookup"><span data-stu-id="1bcb7-121">**Automatic**</span></span>|  
    |<span data-ttu-id="1bcb7-122">Quando un'azione esplicita dell'utente avvia il servizio</span><span class="sxs-lookup"><span data-stu-id="1bcb7-122">When an explicit user action starts the service</span></span>|<span data-ttu-id="1bcb7-123">**Manual**</span><span class="sxs-lookup"><span data-stu-id="1bcb7-123">**Manual**</span></span>|  
  
    > [!TIP]
    >  <span data-ttu-id="1bcb7-124">Per impedire del tutto l'avvio del servizio, è possibile impostare la proprietà <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> su **Disabled**.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-124">To prevent your service from being started at all, you can set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to **Disabled**.</span></span> <span data-ttu-id="1bcb7-125">Ciò può essere utile se si prevede di dover riavviare un server più volte e si vuole risparmiare tempo evitando l'avvio dei servizi che verrebbero normalmente avviati.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-125">You might do this if you are going to reboot a server several times and want to save time by preventing the services that would normally start from starting up.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1bcb7-126">Queste e altre proprietà possono essere modificate dopo l'installazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-126">These and other properties can be changed after your service is installed.</span></span>  
  
     <span data-ttu-id="1bcb7-127">Esistono diversi modi per avviare un servizio con il processo <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> impostato su **Manual**, ovvero da **Esplora server**, da **Gestione controllo servizi** o dal codice.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-127">There are several ways you can start a service that has its <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> process set to **Manual** — from **Server Explorer**, from the **Windows Services Control Manager**, or from code.</span></span> <span data-ttu-id="1bcb7-128">È importante notare che non tutti questi metodi avviano effettivamente il servizio nel contesto di **Gestione controllo servizi**. **Esplora server** e i metodi a livello di codice di avvio del servizio modificano effettivamente il controller.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-128">It is important to note that not all of these methods actually start the service in the context of the **Services Control Manager**; **Server Explorer** and programmatic methods of starting the service actually manipulate the controller.</span></span>  
  
### <a name="to-manually-start-a-service-from-server-explorer"></a><span data-ttu-id="1bcb7-129">Per avviare manualmente un servizio da Esplora server</span><span class="sxs-lookup"><span data-stu-id="1bcb7-129">To manually start a service from Server Explorer</span></span>  
  
1.  <span data-ttu-id="1bcb7-130">In **Esplora server** aggiungere il server desiderato, se non è già elencato.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-130">In **Server Explorer**, add the server you want if it is not already listed.</span></span> <span data-ttu-id="1bcb7-131">Per altre informazioni, vedere Procedura: Accedere e inizializzare Esplora server-Esplora database.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-131">For more information, see How to: Access and Initialize Server Explorer-Database Explorer.</span></span>  
  
2.  <span data-ttu-id="1bcb7-132">Espandere il nodo **Servizi** e quindi individuare il servizio che si vuole avviare.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-132">Expand the **Services** node, and then locate the service you want to start.</span></span>  
  
3.  <span data-ttu-id="1bcb7-133">Fare clic con il pulsante destro del mouse sul nome del servizio e quindi scegliere **Avvia**.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-133">Right-click the name of the service, and click **Start**.</span></span>  
  
### <a name="to-manually-start-a-service-from-services-control-manager"></a><span data-ttu-id="1bcb7-134">Per avviare manualmente un servizio da Gestione controllo servizi</span><span class="sxs-lookup"><span data-stu-id="1bcb7-134">To manually start a service from Services Control Manager</span></span>  
  
1.  <span data-ttu-id="1bcb7-135">Aprire **Gestione controllo servizi** eseguendo una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1bcb7-135">Open the **Services Control Manager** by doing one of the following:</span></span>  
  
    -   <span data-ttu-id="1bcb7-136">In Windows XP e 2000 Professional fare clic con il pulsante destro del mouse su **Risorse del computer** e quindi scegliere **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-136">In Windows XP and 2000 Professional, right-click **My Computer** on the desktop, and then click **Manage**.</span></span> <span data-ttu-id="1bcb7-137">Nella finestra di dialogo visualizzata espandere il nodo **Servizi e applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-137">In the dialog box that appears, expand the **Services and Applications** node.</span></span>  
  
         <span data-ttu-id="1bcb7-138">\- oppure -</span><span class="sxs-lookup"><span data-stu-id="1bcb7-138">\- or -</span></span>  
  
    -   <span data-ttu-id="1bcb7-139">In Windows Server 2003 e Windows 2000 Server fare clic su **Start**, scegliere **Programmi**, fare clic su **Strumenti di amministrazione** e quindi fare clic su **Servizi**.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-139">In Windows Server 2003 and Windows 2000 Server, click **Start**, point to **Programs**, click **Administrative Tools**, and then click **Services**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="1bcb7-140">In Windows NT versione 4.0 è possibile aprire questa finestra di dialogo dal **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-140">In Windows NT version 4.0, you can open this dialog box from **Control Panel**.</span></span>  
  
     <span data-ttu-id="1bcb7-141">Il servizio dovrebbe essere a questo punto elencato nella sezione **Servizi** della finestra.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-141">You should now see your service listed in the **Services** section of the window.</span></span>  
  
2.  <span data-ttu-id="1bcb7-142">Fare clic con il pulsante destro del mouse sul servizio dopo averlo selezionato nell'elenco e quindi scegliere **Avvia**.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-142">Select your service in the list, right-click it, and then click **Start**.</span></span>  
  
### <a name="to-manually-start-a-service-from-code"></a><span data-ttu-id="1bcb7-143">Per avviare manualmente un servizio da codice</span><span class="sxs-lookup"><span data-stu-id="1bcb7-143">To manually start a service from code</span></span>  
  
1.  <span data-ttu-id="1bcb7-144">Creare un'istanza della classe <xref:System.ServiceProcess.ServiceController> e configurarla per interagire con il servizio che si vuole amministrare.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-144">Create an instance of the <xref:System.ServiceProcess.ServiceController> class, and configure it to interact with the service you want to administer.</span></span>  
  
2.  <span data-ttu-id="1bcb7-145">Chiamare il metodo <xref:System.ServiceProcess.ServiceController.Start%2A> per avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="1bcb7-145">Call the <xref:System.ServiceProcess.ServiceController.Start%2A> method to start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bcb7-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bcb7-146">See Also</span></span>  
 [<span data-ttu-id="1bcb7-147">Introduzione alle applicazioni di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="1bcb7-147">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="1bcb7-148">Procedura: creare servizi Windows</span><span class="sxs-lookup"><span data-stu-id="1bcb7-148">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [<span data-ttu-id="1bcb7-149">Procedura: aggiungere programmi di installazione all'applicazione di servizio</span><span class="sxs-lookup"><span data-stu-id="1bcb7-149">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)
