---
title: 'Procedura: Creare servizi Windows'
description: Per creare un servizio, usare il modello di progetto servizio Windows. Impostare la proprietà ServiceName, creare programmi di installazione ed eseguire l'override dei metodi OnStart e OnStop.
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, creating
- templates, Windows Service
ms.assetid: 0f5e2cbb-d95d-477c-b2b5-4b990e6b86ff
author: ghogen
ms.openlocfilehash: 6918225e39c15a52710fd0d56342aae869b42325
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925774"
---
# <a name="how-to-create-windows-services"></a><span data-ttu-id="ee181-104">Procedura: Creare servizi Windows</span><span class="sxs-lookup"><span data-stu-id="ee181-104">How to: Create Windows Services</span></span>
<span data-ttu-id="ee181-105">Quando si crea un servizio, è possibile usare un modello di progetto di Visual Studio denominato **Servizio Windows**.</span><span class="sxs-lookup"><span data-stu-id="ee181-105">When you create a service, you can use a Visual Studio project template called **Windows Service**.</span></span> <span data-ttu-id="ee181-106">Questo modello esegue automaticamente una buona parte del lavoro facendo riferimento alle classi e agli spazi dei nomi appropriati, impostando l'ereditarietà dalla classe di base per i servizi ed eseguendo l'override di molti metodi, quando occorre.</span><span class="sxs-lookup"><span data-stu-id="ee181-106">This template automatically does much of the work for you by referencing the appropriate classes and namespaces, setting up the inheritance from the base class for services, and overriding several of the methods you're likely to want to override.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="ee181-107">Il modello di progetto Servizi Windows non è disponibile nell'edizione Express di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ee181-107">The Windows Services project template is not available in the Express edition of Visual Studio.</span></span>  
  
 <span data-ttu-id="ee181-108">Per creare un servizio funzionale è necessario eseguire almeno le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ee181-108">At a minimum, to create a functional service you must:</span></span>  
  
- <span data-ttu-id="ee181-109">Impostare la proprietà <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>.</span><span class="sxs-lookup"><span data-stu-id="ee181-109">Set the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property.</span></span>  
  
- <span data-ttu-id="ee181-110">Creare i programmi di installazione necessari per l'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="ee181-110">Create the necessary installers for your service application.</span></span>  
  
- <span data-ttu-id="ee181-111">Eseguire l'override e specificare il codice dei metodi <xref:System.ServiceProcess.ServiceBase.OnStart%2A> e <xref:System.ServiceProcess.ServiceBase.OnStop%2A> per personalizzare il comportamento del servizio.</span><span class="sxs-lookup"><span data-stu-id="ee181-111">Override and specify code for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> methods to customize the ways in which your service behaves.</span></span>  
  
### <a name="to-create-a-windows-service-application"></a><span data-ttu-id="ee181-112">Per creare un'applicazione di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="ee181-112">To create a Windows Service application</span></span>  
  
1. <span data-ttu-id="ee181-113">Creare un progetto **Servizio Windows**.</span><span class="sxs-lookup"><span data-stu-id="ee181-113">Create a **Windows Service** project.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ee181-114">Per istruzioni sulla scrittura di un servizio senza l'uso del modello, vedere [Procedura: Scrivere servizi a livello di codice](how-to-write-services-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="ee181-114">For instructions on writing a service without using the template, see [How to: Write Services Programmatically](how-to-write-services-programmatically.md).</span></span>  
  
2. <span data-ttu-id="ee181-115">Nella finestra **Proprietà** impostare la proprietà <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> per il servizio.</span><span class="sxs-lookup"><span data-stu-id="ee181-115">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property for your service.</span></span>  
  
     <span data-ttu-id="ee181-116">![Impostare la proprietà ServiceName.](./media/windowsservice-servicename.PNG "WindowsService_ServiceName")</span><span class="sxs-lookup"><span data-stu-id="ee181-116">![Set the ServiceName property.](./media/windowsservice-servicename.PNG "WindowsService_ServiceName")</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ee181-117">Il valore della proprietà <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> deve sempre corrispondere al nome registrato nelle classi del programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="ee181-117">The value of the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property must always match the name recorded in the installer classes.</span></span> <span data-ttu-id="ee181-118">Se questa proprietà viene modificata, sarà necessario aggiornare anche la proprietà <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> delle classi del programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="ee181-118">If you change this property, you must update the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property of installer classes as well.</span></span>  
  
3. <span data-ttu-id="ee181-119">Per definire il funzionamento del servizio, impostare una delle proprietà seguenti.</span><span class="sxs-lookup"><span data-stu-id="ee181-119">Set any of the following properties to determine how your service will function.</span></span>  
  
    |<span data-ttu-id="ee181-120">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ee181-120">Property</span></span>|<span data-ttu-id="ee181-121">Impostazione</span><span class="sxs-lookup"><span data-stu-id="ee181-121">Setting</span></span>|  
    |--------------|-------------|  
    |<xref:System.ServiceProcess.ServiceBase.CanStop%2A>|<span data-ttu-id="ee181-122">`True` per indicare che il servizio accetta le richieste di interruzione dell'esecuzione; `false` per impedire l'interruzione del servizio.</span><span class="sxs-lookup"><span data-stu-id="ee181-122">`True` to indicate that the service will accept requests to stop running; `false` to prevent the service from being stopped.</span></span>|  
    |<xref:System.ServiceProcess.ServiceBase.CanShutdown%2A>|<span data-ttu-id="ee181-123">`True` per indicare che il servizio richiede una notifica alla chiusura del computer su cui viene eseguito, consentendo la chiamata alla routine <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>.</span><span class="sxs-lookup"><span data-stu-id="ee181-123">`True` to indicate that the service wants to receive notification when the computer on which it lives shuts down, enabling it to call the <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> procedure.</span></span>|  
    |<xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A>|<span data-ttu-id="ee181-124">`True` per indicare che il servizio accetta le richieste di sospensione o di ripresa dell'esecuzione; `false` per impedire la sospensione e la ripresa del servizio.</span><span class="sxs-lookup"><span data-stu-id="ee181-124">`True` to indicate that the service will accept requests to pause or to resume running; `false` to prevent the service from being paused and resumed.</span></span>|  
    |<xref:System.ServiceProcess.ServiceBase.CanHandlePowerEvent%2A>|<span data-ttu-id="ee181-125">`True` per indicare che il servizio può gestire la notifica delle variazioni dello stato di alimentazione del computer; `false` per impedire al servizio di ricevere notifica di tali modifiche.</span><span class="sxs-lookup"><span data-stu-id="ee181-125">`True` to indicate that the service can handle notification of changes to the computer's power status; `false` to prevent the service from being notified of these changes.</span></span>|  
    |<xref:System.ServiceProcess.ServiceBase.AutoLog%2A>|<span data-ttu-id="ee181-126">`True` per scrivere informazioni nel log eventi dell'applicazione quando il servizio esegue un'operazione; `false` per disabilitare questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ee181-126">`True` to write informational entries to the Application event log when your service performs an action; `false` to disable this functionality.</span></span> <span data-ttu-id="ee181-127">Per altre informazioni, vedere [Procedura: Registrare informazioni sui servizi](how-to-log-information-about-services.md).</span><span class="sxs-lookup"><span data-stu-id="ee181-127">For more information, see [How to: Log Information About Services](how-to-log-information-about-services.md).</span></span> <span data-ttu-id="ee181-128">**Nota:** Per impostazione predefinita, la proprietà <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> è impostata su `true`.</span><span class="sxs-lookup"><span data-stu-id="ee181-128">**Note:**  By default, <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> is set to `true`.</span></span>|  
  
    > [!NOTE]
    > <span data-ttu-id="ee181-129">Quando l'oggetto <xref:System.ServiceProcess.ServiceBase.CanStop%2A> o <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> è impostato su `false`, **Gestione controllo servizi** disabiliterà le opzioni di menu corrispondenti per arrestare, sospendere o continuare il servizio.</span><span class="sxs-lookup"><span data-stu-id="ee181-129">When <xref:System.ServiceProcess.ServiceBase.CanStop%2A> or <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> are set to `false`, the **Service Control Manager** will disable the corresponding menu options to stop, pause, or continue the service.</span></span>  
  
4. <span data-ttu-id="ee181-130">Accedere all'editor di codice e definire il funzionamento desiderato per le routine <xref:System.ServiceProcess.ServiceBase.OnStart%2A> e <xref:System.ServiceProcess.ServiceBase.OnStop%2A>.</span><span class="sxs-lookup"><span data-stu-id="ee181-130">Access the Code Editor and fill in the processing you want for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> procedures.</span></span>  
  
5. <span data-ttu-id="ee181-131">Eseguire l'override di eventuali altri metodi per i quali si desidera definire la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ee181-131">Override any other methods for which you want to define functionality.</span></span>  
  
6. <span data-ttu-id="ee181-132">Aggiungere i programmi di installazione necessari per l'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="ee181-132">Add the necessary installers for your service application.</span></span> <span data-ttu-id="ee181-133">Per altre informazioni, vedere [Procedura: Aggiungere programmi di installazione all'applicazione di servizio](how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="ee181-133">For more information, see [How to: Add Installers to Your Service Application](how-to-add-installers-to-your-service-application.md).</span></span>  
  
7. <span data-ttu-id="ee181-134">Compilare il progetto scegliendo **Compila soluzione** dal menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="ee181-134">Build your project by selecting **Build Solution** from the **Build** menu.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ee181-135">Non è possibile eseguire un progetto di servizio premendo F5.</span><span class="sxs-lookup"><span data-stu-id="ee181-135">Do not press F5 to run your project — you cannot run a service project in this way.</span></span>  
  
8. <span data-ttu-id="ee181-136">Installare il servizio.</span><span class="sxs-lookup"><span data-stu-id="ee181-136">Install the service.</span></span> <span data-ttu-id="ee181-137">Per altre informazioni, vedere [How to: Install and Uninstall Services](how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="ee181-137">For more information, see [How to: Install and Uninstall Services](how-to-install-and-uninstall-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee181-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee181-138">See also</span></span>

- [<span data-ttu-id="ee181-139">Introduzione alle applicazioni di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="ee181-139">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="ee181-140">Procedura: Scrivere servizi a livello di codice</span><span class="sxs-lookup"><span data-stu-id="ee181-140">How to: Write Services Programmatically</span></span>](how-to-write-services-programmatically.md)
- [<span data-ttu-id="ee181-141">Procedura: Aggiungere programmi di installazione all'applicazione di servizio</span><span class="sxs-lookup"><span data-stu-id="ee181-141">How to: Add Installers to Your Service Application</span></span>](how-to-add-installers-to-your-service-application.md)
- [<span data-ttu-id="ee181-142">Procedura: Registrare informazioni sui servizi</span><span class="sxs-lookup"><span data-stu-id="ee181-142">How to: Log Information About Services</span></span>](how-to-log-information-about-services.md)
- [<span data-ttu-id="ee181-143">Procedura: Avviare servizi</span><span class="sxs-lookup"><span data-stu-id="ee181-143">How to: Start Services</span></span>](how-to-start-services.md)
- [<span data-ttu-id="ee181-144">Procedura: Specificare il contesto di sicurezza per i servizi</span><span class="sxs-lookup"><span data-stu-id="ee181-144">How to: Specify the Security Context for Services</span></span>](how-to-specify-the-security-context-for-services.md)
- [<span data-ttu-id="ee181-145">Procedura: installare e disinstallare servizi</span><span class="sxs-lookup"><span data-stu-id="ee181-145">How to: Install and Uninstall Services</span></span>](how-to-install-and-uninstall-services.md)
- [<span data-ttu-id="ee181-146">Procedura dettagliata: creazione di un'applicazione di servizio Windows in Progettazione componenti</span><span class="sxs-lookup"><span data-stu-id="ee181-146">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
