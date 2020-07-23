---
title: 'Procedura: Avviare servizi'
description: Scopri diversi modi per avviare i servizi. Dopo l'installazione di un servizio, è necessario avviarlo. L'avvio chiama il metodo OnStart sulla classe del servizio.
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, starting
- services, starting
ms.assetid: 9ea77955-2d96-4c3d-913c-14db7604cdad
author: ghogen
ms.openlocfilehash: 4a2f9b291e60b12b1465fbb6bbbd1604572359a7
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925722"
---
# <a name="how-to-start-services"></a><span data-ttu-id="cae54-105">Procedura: Avviare servizi</span><span class="sxs-lookup"><span data-stu-id="cae54-105">How to: Start Services</span></span>

<span data-ttu-id="cae54-106">Dopo l'installazione di un servizio, è necessario avviarlo.</span><span class="sxs-lookup"><span data-stu-id="cae54-106">After a service is installed, it must be started.</span></span> <span data-ttu-id="cae54-107">Con l'avvio viene chiamato il metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> per la classe del servizio.</span><span class="sxs-lookup"><span data-stu-id="cae54-107">Starting calls the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method on the service class.</span></span> <span data-ttu-id="cae54-108">In genere, il metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> definisce le operazioni utili che verranno eseguite dal servizio.</span><span class="sxs-lookup"><span data-stu-id="cae54-108">Usually, the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method defines the useful work the service will perform.</span></span> <span data-ttu-id="cae54-109">Dopo l'avvio, un servizio rimane attivo fino a quando non viene sospeso o arrestato manualmente.</span><span class="sxs-lookup"><span data-stu-id="cae54-109">After a service starts, it remains active until it is manually paused or stopped.</span></span>

<span data-ttu-id="cae54-110">I servizi possono essere configurati per l'avvio automatico o manuale.</span><span class="sxs-lookup"><span data-stu-id="cae54-110">Services can be set up to start automatically or manually.</span></span> <span data-ttu-id="cae54-111">Un servizio con avvio automatico verrà avviato in seguito al riavvio o alla prima accensione del computer in cui è installato.</span><span class="sxs-lookup"><span data-stu-id="cae54-111">A service that starts automatically will be started when the computer on which it is installed is rebooted or first turned on.</span></span> <span data-ttu-id="cae54-112">Un utente deve avviare un servizio con avvio manuale.</span><span class="sxs-lookup"><span data-stu-id="cae54-112">A user must start a service that starts manually.</span></span>

> [!NOTE]
> <span data-ttu-id="cae54-113">Per impostazione predefinita, i servizi creati con Visual Studio vengono impostati per l'avvio manuale.</span><span class="sxs-lookup"><span data-stu-id="cae54-113">By default, services created with Visual Studio are set to start manually.</span></span>

<span data-ttu-id="cae54-114">Esistono diversi modi per avviare manualmente un servizio, ovvero da **Esplora server**, da **Gestione controllo servizi** o dal codice usando un componente denominato <xref:System.ServiceProcess.ServiceController>.</span><span class="sxs-lookup"><span data-stu-id="cae54-114">There are several ways you can manually start a service — from **Server Explorer**, from the **Services Control Manager**, or from code using a component called the <xref:System.ServiceProcess.ServiceController>.</span></span>

<span data-ttu-id="cae54-115">Per determinare se un servizio deve essere avviato manualmente o automaticamente, è possibile impostare la proprietà <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> per la classe <xref:System.ServiceProcess.ServiceInstaller>.</span><span class="sxs-lookup"><span data-stu-id="cae54-115">You set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property on the <xref:System.ServiceProcess.ServiceInstaller> class to determine whether a service should be started manually or automatically.</span></span>

### <a name="to-specify-how-a-service-should-start"></a><span data-ttu-id="cae54-116">Per specificare come avviare un servizio</span><span class="sxs-lookup"><span data-stu-id="cae54-116">To specify how a service should start</span></span>

1. <span data-ttu-id="cae54-117">Dopo aver creato il servizio, aggiungere i programmi di installazione necessari.</span><span class="sxs-lookup"><span data-stu-id="cae54-117">After creating your service, add the necessary installers for it.</span></span> <span data-ttu-id="cae54-118">Per altre informazioni, vedere [Procedura: Aggiungere programmi di installazione all'applicazione di servizio](how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="cae54-118">For more information, see [How to: Add Installers to Your Service Application](how-to-add-installers-to-your-service-application.md).</span></span>

2. <span data-ttu-id="cae54-119">Nella finestra di progettazione fare clic sul programma di installazione per il servizio in uso.</span><span class="sxs-lookup"><span data-stu-id="cae54-119">In the designer, click the service installer for the service you are working with.</span></span>

3. <span data-ttu-id="cae54-120">Nella finestra **Proprietà** impostare la proprietà <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> su uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="cae54-120">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to one of the following:</span></span>

    |<span data-ttu-id="cae54-121">Per installare il servizio</span><span class="sxs-lookup"><span data-stu-id="cae54-121">To have your service install</span></span>|<span data-ttu-id="cae54-122">Impostare questo valore</span><span class="sxs-lookup"><span data-stu-id="cae54-122">Set this value</span></span>|
    |----------------------------------|--------------------|
    |<span data-ttu-id="cae54-123">Al riavvio del computer</span><span class="sxs-lookup"><span data-stu-id="cae54-123">When the computer is restarted</span></span>|<span data-ttu-id="cae54-124">**Automatico**</span><span class="sxs-lookup"><span data-stu-id="cae54-124">**Automatic**</span></span>|
    |<span data-ttu-id="cae54-125">Quando un'azione esplicita dell'utente avvia il servizio</span><span class="sxs-lookup"><span data-stu-id="cae54-125">When an explicit user action starts the service</span></span>|<span data-ttu-id="cae54-126">**Manuale**</span><span class="sxs-lookup"><span data-stu-id="cae54-126">**Manual**</span></span>|

    > [!TIP]
    > <span data-ttu-id="cae54-127">Per impedire del tutto l'avvio del servizio, è possibile impostare la proprietà <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> su **Disabled**.</span><span class="sxs-lookup"><span data-stu-id="cae54-127">To prevent your service from being started at all, you can set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to **Disabled**.</span></span> <span data-ttu-id="cae54-128">Ciò può essere utile se si prevede di dover riavviare un server più volte e si vuole risparmiare tempo evitando l'avvio dei servizi che verrebbero normalmente avviati.</span><span class="sxs-lookup"><span data-stu-id="cae54-128">You might do this if you are going to reboot a server several times and want to save time by preventing the services that would normally start from starting up.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cae54-129">Queste e altre proprietà possono essere modificate dopo l'installazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="cae54-129">These and other properties can be changed after your service is installed.</span></span>

    <span data-ttu-id="cae54-130">Esistono diversi modi per avviare un servizio con il processo <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> impostato su **Manual**, ovvero da **Esplora server**, da **Gestione controllo servizi** o dal codice.</span><span class="sxs-lookup"><span data-stu-id="cae54-130">There are several ways you can start a service that has its <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> process set to **Manual** — from **Server Explorer**, from the **Windows Services Control Manager**, or from code.</span></span> <span data-ttu-id="cae54-131">È importante notare che non tutti questi metodi avviano effettivamente il servizio nel contesto di **Gestione controllo servizi**. **Esplora server** e i metodi a livello di codice di avvio del servizio modificano effettivamente il controller.</span><span class="sxs-lookup"><span data-stu-id="cae54-131">It is important to note that not all of these methods actually start the service in the context of the **Services Control Manager**; **Server Explorer** and programmatic methods of starting the service actually manipulate the controller.</span></span>

### <a name="to-manually-start-a-service-from-server-explorer"></a><span data-ttu-id="cae54-132">Per avviare manualmente un servizio da Esplora server</span><span class="sxs-lookup"><span data-stu-id="cae54-132">To manually start a service from Server Explorer</span></span>

1. <span data-ttu-id="cae54-133">In **Esplora server** aggiungere il server desiderato, se non è già elencato.</span><span class="sxs-lookup"><span data-stu-id="cae54-133">In **Server Explorer**, add the server you want if it is not already listed.</span></span> <span data-ttu-id="cae54-134">Per altre informazioni, vedere Procedura: Accedere e inizializzare Esplora server-Esplora database.</span><span class="sxs-lookup"><span data-stu-id="cae54-134">For more information, see How to: Access and Initialize Server Explorer-Database Explorer.</span></span>

2. <span data-ttu-id="cae54-135">Espandere il nodo **Servizi** e quindi individuare il servizio che si vuole avviare.</span><span class="sxs-lookup"><span data-stu-id="cae54-135">Expand the **Services** node, and then locate the service you want to start.</span></span>

3. <span data-ttu-id="cae54-136">Fare clic con il pulsante destro del mouse sul nome del servizio e quindi scegliere **Avvia**.</span><span class="sxs-lookup"><span data-stu-id="cae54-136">Right-click the name of the service, and click **Start**.</span></span>

### <a name="to-manually-start-a-service-from-services-control-manager"></a><span data-ttu-id="cae54-137">Per avviare manualmente un servizio da Gestione controllo servizi</span><span class="sxs-lookup"><span data-stu-id="cae54-137">To manually start a service from Services Control Manager</span></span>

1. <span data-ttu-id="cae54-138">Aprire **Gestione controllo servizi** eseguendo una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cae54-138">Open the **Services Control Manager** by doing one of the following:</span></span>

    - <span data-ttu-id="cae54-139">In Windows XP e 2000 Professional fare clic con il pulsante destro del mouse su **Risorse del computer** e quindi scegliere **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="cae54-139">In Windows XP and 2000 Professional, right-click **My Computer** on the desktop, and then click **Manage**.</span></span> <span data-ttu-id="cae54-140">Nella finestra di dialogo visualizzata espandere il nodo **Servizi e applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="cae54-140">In the dialog box that appears, expand the **Services and Applications** node.</span></span>

      <span data-ttu-id="cae54-141">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="cae54-141">\- or -</span></span>

    - <span data-ttu-id="cae54-142">In Windows Server 2003 e Windows 2000 Server fare clic su **Start**, scegliere **Programmi**, fare clic su **Strumenti di amministrazione** e quindi fare clic su **Servizi**.</span><span class="sxs-lookup"><span data-stu-id="cae54-142">In Windows Server 2003 and Windows 2000 Server, click **Start**, point to **Programs**, click **Administrative Tools**, and then click **Services**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="cae54-143">In Windows NT versione 4.0 è possibile aprire questa finestra di dialogo dal **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="cae54-143">In Windows NT version 4.0, you can open this dialog box from **Control Panel**.</span></span>

    <span data-ttu-id="cae54-144">Il servizio dovrebbe essere a questo punto elencato nella sezione **Servizi** della finestra.</span><span class="sxs-lookup"><span data-stu-id="cae54-144">You should now see your service listed in the **Services** section of the window.</span></span>

2. <span data-ttu-id="cae54-145">Fare clic con il pulsante destro del mouse sul servizio dopo averlo selezionato nell'elenco e quindi scegliere **Avvia**.</span><span class="sxs-lookup"><span data-stu-id="cae54-145">Select your service in the list, right-click it, and then click **Start**.</span></span>

### <a name="to-manually-start-a-service-from-code"></a><span data-ttu-id="cae54-146">Per avviare manualmente un servizio da codice</span><span class="sxs-lookup"><span data-stu-id="cae54-146">To manually start a service from code</span></span>

1. <span data-ttu-id="cae54-147">Creare un'istanza della classe <xref:System.ServiceProcess.ServiceController> e configurarla per interagire con il servizio che si vuole amministrare.</span><span class="sxs-lookup"><span data-stu-id="cae54-147">Create an instance of the <xref:System.ServiceProcess.ServiceController> class, and configure it to interact with the service you want to administer.</span></span>

2. <span data-ttu-id="cae54-148">Chiamare il metodo <xref:System.ServiceProcess.ServiceController.Start%2A> per avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="cae54-148">Call the <xref:System.ServiceProcess.ServiceController.Start%2A> method to start the service.</span></span>

## <a name="see-also"></a><span data-ttu-id="cae54-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cae54-149">See also</span></span>

- [<span data-ttu-id="cae54-150">Introduzione alle applicazioni di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="cae54-150">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="cae54-151">Procedura: Creare servizi Windows</span><span class="sxs-lookup"><span data-stu-id="cae54-151">How to: Create Windows Services</span></span>](how-to-create-windows-services.md)
- [<span data-ttu-id="cae54-152">Procedura: Aggiungere programmi di installazione all'applicazione di servizio</span><span class="sxs-lookup"><span data-stu-id="cae54-152">How to: Add Installers to Your Service Application</span></span>](how-to-add-installers-to-your-service-application.md)
