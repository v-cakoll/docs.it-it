---
title: 'Procedura: aggiungere programmi di installazione all''applicazione di servizio'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, deploying
- installation components, adding to services
- installers, adding to services
- Windows Service applications, adding installers
- services, adding installers
- ServiceInstaller class, adding installers to services
- ServiceProcessInstaller class, adding installers to services
ms.assetid: 8b698e9a-b88e-4f44-ae45-e0c5ea0ae5a8
caps.latest.revision: "14"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 15487d4311f896aa09c1c7712292058086a49b50
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-add-installers-to-your-service-application"></a><span data-ttu-id="0cde1-102">Procedura: aggiungere programmi di installazione all'applicazione di servizio</span><span class="sxs-lookup"><span data-stu-id="0cde1-102">How to: Add Installers to Your Service Application</span></span>
<span data-ttu-id="0cde1-103">Visual Studio fornisce componenti di installazione che è possono installare le risorse associate alle applicazioni di servizio.</span><span class="sxs-lookup"><span data-stu-id="0cde1-103">Visual Studio ships installation components that can install resources associated with your service applications.</span></span> <span data-ttu-id="0cde1-104">Componenti di installazione registrano un singolo servizio sul sistema in cui viene installato e Gestione controllo servizi di informare che il servizio esista.</span><span class="sxs-lookup"><span data-stu-id="0cde1-104">Installation components register an individual service on the system to which it is being installed and let the Services Control Manager know that the service exists.</span></span> <span data-ttu-id="0cde1-105">Quando si lavora con un'applicazione di servizio, è possibile selezionare un collegamento nella finestra proprietà per aggiungere automaticamente i programmi di installazione appropriati per il progetto.</span><span class="sxs-lookup"><span data-stu-id="0cde1-105">When you work with a service application, you can select a link in the Properties window to automatically add the appropriate installers to your project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0cde1-106">I valori delle proprietà per il servizio vengono copiati dalla classe di servizio per la classe installer.</span><span class="sxs-lookup"><span data-stu-id="0cde1-106">Property values for your service are copied from the service class to the installer class.</span></span> <span data-ttu-id="0cde1-107">Se si aggiornano i valori delle proprietà nella classe del servizio, essi non vengono aggiornate automaticamente nel programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="0cde1-107">If you update the property values on the service class, they are not automatically updated in the installer.</span></span>  
  
 <span data-ttu-id="0cde1-108">Quando si aggiunge un programma di installazione per il progetto, una nuova classe (che, per impostazione predefinita, denominato `ProjectInstaller`) viene creato nel progetto e le istanze della corretta installazione di componenti vengono creati all'interno di esso.</span><span class="sxs-lookup"><span data-stu-id="0cde1-108">When you add an installer to your project, a new class (which, by default, is named `ProjectInstaller`) is created in the project, and instances of the appropriate installation components are created within it.</span></span> <span data-ttu-id="0cde1-109">Questa classe funge da punto centrale per tutti i componenti di installazione dal progetto.</span><span class="sxs-lookup"><span data-stu-id="0cde1-109">This class acts as a central point for all of the installation components your project needs.</span></span> <span data-ttu-id="0cde1-110">Ad esempio, se si aggiunge un secondo servizio all'applicazione e fare clic sul collegamento Aggiungi programma di installazione, una seconda classe di installazione non viene creata; al contrario, il componente di installazione aggiuntivi necessari per il secondo servizio viene aggiunto alla classe esistente.</span><span class="sxs-lookup"><span data-stu-id="0cde1-110">For example, if you add a second service to your application and click the Add Installer link, a second installer class is not created; instead, the necessary additional installation component for the second service is added to the existing class.</span></span>  
  
 <span data-ttu-id="0cde1-111">Non è necessario codice specifico all'interno di programmi di installazione per installare correttamente i servizi.</span><span class="sxs-lookup"><span data-stu-id="0cde1-111">You do not need to do any special coding within the installers to make your services install correctly.</span></span> <span data-ttu-id="0cde1-112">Tuttavia, in alcuni casi potrebbe essere necessario modificare il contenuto dei programmi di installazione se è necessario aggiungere funzionalità speciali per il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="0cde1-112">However, you may occasionally need to modify the contents of the installers if you need to add special functionality to the installation process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0cde1-113">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="0cde1-113">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0cde1-114">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="0cde1-114">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0cde1-115">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="0cde1-115">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-installers-to-your-service-application"></a><span data-ttu-id="0cde1-116">Per aggiungere i programmi di installazione all'applicazione di servizio</span><span class="sxs-lookup"><span data-stu-id="0cde1-116">To add installers to your service application</span></span>  
  
1.  <span data-ttu-id="0cde1-117">In **Esplora**, accesso **progettazione** visualizzazione per il servizio per il quale si desidera aggiungere un componente di installazione.</span><span class="sxs-lookup"><span data-stu-id="0cde1-117">In **Solution Explorer**, access **Design** view for the service for which you want to add an installation component.</span></span>  
  
2.  <span data-ttu-id="0cde1-118">Fare clic sull'icona della finestra di progettazione per selezionare il servizio stesso, anziché il suo contenuto.</span><span class="sxs-lookup"><span data-stu-id="0cde1-118">Click the background of the designer to select the service itself, rather than any of its contents.</span></span>  
  
3.  <span data-ttu-id="0cde1-119">Con la finestra di progettazione in cui lo stato attivo, mouse e quindi fare clic su **Aggiungi programma di installazione**.</span><span class="sxs-lookup"><span data-stu-id="0cde1-119">With the designer in focus, right-click, and then click **Add Installer**.</span></span>  
  
     <span data-ttu-id="0cde1-120">Una nuova classe, `ProjectInstaller`e due componenti di installazione, <xref:System.ServiceProcess.ServiceProcessInstaller> e <xref:System.ServiceProcess.ServiceInstaller>, vengono aggiunti al progetto e i valori delle proprietà per il servizio vengono copiati i componenti.</span><span class="sxs-lookup"><span data-stu-id="0cde1-120">A new class, `ProjectInstaller`, and two installation components, <xref:System.ServiceProcess.ServiceProcessInstaller> and <xref:System.ServiceProcess.ServiceInstaller>, are added to your project, and property values for the service are copied to the components.</span></span>  
  
4.  <span data-ttu-id="0cde1-121">Fare clic sul <xref:System.ServiceProcess.ServiceInstaller> componente e verificare che il valore della <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> proprietà è impostata sullo stesso valore come il <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> proprietà del servizio stesso.</span><span class="sxs-lookup"><span data-stu-id="0cde1-121">Click the <xref:System.ServiceProcess.ServiceInstaller> component and verify that the value of the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property is set to the same value as the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property on the service itself.</span></span>  
  
5.  <span data-ttu-id="0cde1-122">Per determinare come verrà avviato il servizio, scegliere il <xref:System.ServiceProcess.ServiceInstaller> componente e impostare il <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> proprietà sul valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="0cde1-122">To determine how your service will be started, click the <xref:System.ServiceProcess.ServiceInstaller> component and set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to the appropriate value.</span></span>  
  
    |<span data-ttu-id="0cde1-123">Valore</span><span class="sxs-lookup"><span data-stu-id="0cde1-123">Value</span></span>|<span data-ttu-id="0cde1-124">Risultato</span><span class="sxs-lookup"><span data-stu-id="0cde1-124">Result</span></span>|  
    |-----------|------------|  
    |<xref:System.ServiceProcess.ServiceStartMode.Manual>|<span data-ttu-id="0cde1-125">Il servizio deve essere avviato manualmente dopo l'installazione.</span><span class="sxs-lookup"><span data-stu-id="0cde1-125">The service must be manually started after installation.</span></span> <span data-ttu-id="0cde1-126">Per ulteriori informazioni, vedere [procedura: avviare servizi](../../../docs/framework/windows-services/how-to-start-services.md).</span><span class="sxs-lookup"><span data-stu-id="0cde1-126">For more information, see [How to: Start Services](../../../docs/framework/windows-services/how-to-start-services.md).</span></span>|  
    |<xref:System.ServiceProcess.ServiceStartMode.Automatic>|<span data-ttu-id="0cde1-127">Il servizio verrà avviato automaticamente ogni volta che il riavvio del computer.</span><span class="sxs-lookup"><span data-stu-id="0cde1-127">The service will start by itself whenever the computer reboots.</span></span>|  
    |<xref:System.ServiceProcess.ServiceStartMode.Disabled>|<span data-ttu-id="0cde1-128">Impossibile avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="0cde1-128">The service cannot be started.</span></span>|  
  
6.  <span data-ttu-id="0cde1-129">Per determinare il contesto di sicurezza in cui verrà eseguito il servizio, scegliere il <xref:System.ServiceProcess.ServiceProcessInstaller> componente e impostare i valori di proprietà appropriata.</span><span class="sxs-lookup"><span data-stu-id="0cde1-129">To determine the security context in which your service will run, click the <xref:System.ServiceProcess.ServiceProcessInstaller> component and set the appropriate property values.</span></span> <span data-ttu-id="0cde1-130">Per ulteriori informazioni, vedere [procedura: specificare il contesto di sicurezza per i servizi](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md).</span><span class="sxs-lookup"><span data-stu-id="0cde1-130">For more information, see [How to: Specify the Security Context for Services](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md).</span></span>  
  
7.  <span data-ttu-id="0cde1-131">Eseguire l'override di metodi per il quale è necessario eseguire un'elaborazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="0cde1-131">Override any methods for which you need to perform custom processing.</span></span>  
  
8.  <span data-ttu-id="0cde1-132">Eseguire i passaggi da 1 a 7 per ogni servizio aggiuntive nel progetto.</span><span class="sxs-lookup"><span data-stu-id="0cde1-132">Perform steps 1 through 7 for each additional service in your project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0cde1-133">Per ogni servizio aggiuntiva nel progetto, è necessario aggiungere un ulteriore <xref:System.ServiceProcess.ServiceInstaller> componente per il progetto `ProjectInstaller` classe.</span><span class="sxs-lookup"><span data-stu-id="0cde1-133">For each additional service in your project, you must add an additional <xref:System.ServiceProcess.ServiceInstaller> component to the project's `ProjectInstaller` class.</span></span> <span data-ttu-id="0cde1-134">Il <xref:System.ServiceProcess.ServiceProcessInstaller> componente aggiunto nel passaggio 3. funziona con tutti i programmi di installazione singolo servizio nel progetto.</span><span class="sxs-lookup"><span data-stu-id="0cde1-134">The <xref:System.ServiceProcess.ServiceProcessInstaller> component added in step three works with all of the individual service installers in the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cde1-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0cde1-135">See Also</span></span>  
 [<span data-ttu-id="0cde1-136">Introduzione alle applicazioni di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="0cde1-136">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="0cde1-137">Procedura: installare e disinstallare servizi</span><span class="sxs-lookup"><span data-stu-id="0cde1-137">How to: Install and Uninstall Services</span></span>](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [<span data-ttu-id="0cde1-138">Procedura: avviare servizi</span><span class="sxs-lookup"><span data-stu-id="0cde1-138">How to: Start Services</span></span>](../../../docs/framework/windows-services/how-to-start-services.md)  
 [<span data-ttu-id="0cde1-139">Procedura: specificare il contesto di sicurezza per i servizi</span><span class="sxs-lookup"><span data-stu-id="0cde1-139">How to: Specify the Security Context for Services</span></span>](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)
