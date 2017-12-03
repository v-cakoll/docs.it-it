---
title: 'Procedura: ospitare un servizio WCF in un servizio Windows gestito'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 8e37363b-4dad-4fb6-907f-73c30fac1d9a
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3e8572541e0bf9ddcfb93939c177b5cb8c440b41
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-host-a-wcf-service-in-a-managed-windows-service"></a><span data-ttu-id="a7d3e-102">Procedura: ospitare un servizio WCF in un servizio Windows gestito</span><span class="sxs-lookup"><span data-stu-id="a7d3e-102">How to: Host a WCF Service in a Managed Windows Service</span></span>
<span data-ttu-id="a7d3e-103">In questo argomento vengono delineati i passaggi di base necessari per creare un servizio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ospitato da un servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-103">This topic outlines the basic steps required to create a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service that is hosted by a Windows Service.</span></span> <span data-ttu-id="a7d3e-104">Lo scenario viene abilitato dall'opzione di hosting del servizio Windows gestito che è un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con esecuzione prolungata ospitato all'esterno di Internet Information Services (IIS), in un ambiente protetto non attivato da messaggi.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-104">The scenario is enabled by the managed Windows service hosting option that is a long-running [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service hosted outside of Internet Information Services (IIS) in a secure environment that is not message activated.</span></span> <span data-ttu-id="a7d3e-105">La durata del servizio è controllata invece dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-105">The lifetime of the service is controlled instead by the operating system.</span></span> <span data-ttu-id="a7d3e-106">Questa opzione di hosting è disponibile in tutte le versioni di Windows.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-106">This hosting option is available in all versions of Windows.</span></span>  
  
 <span data-ttu-id="a7d3e-107">I servizi Windows possono essere gestiti con Microsoft.ManagementConsole.SnapIn in Microsoft Management Console (MMC) e possono essere configurati per essere avviati automaticamente all'avvio del sistema.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-107">Windows services can be managed with the Microsoft.ManagementConsole.SnapIn in Microsoft Management Console (MMC) and can be configured to start up automatically when the system boots up.</span></span> <span data-ttu-id="a7d3e-108">Questa opzione di hosting è costituita dalla registrazione del dominio dell'applicazione (AppDomain) che ospita un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] come servizio Windows gestito, in modo che la durata del processo del servizio venga controllata da Gestione controllo servizi per i servizi Windows.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-108">This hosting option consists of registering the application domain (AppDomain) that hosts a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service as a managed Windows service so that the process lifetime of the service is controlled by the Service Control Manager (SCM) for Windows services.</span></span>  
  
 <span data-ttu-id="a7d3e-109">Il codice del servizio include un'implementazione del contratto di servizio, una classe di servizio Windows e una classe del programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-109">The service code includes a service implementation of the service contract, a Windows Service class, and an installer class.</span></span> <span data-ttu-id="a7d3e-110">La classe di implementazione del servizio, `CalculatorService`, è un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7d3e-110">The service implementation class, `CalculatorService`, is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="a7d3e-111">`CalculatorWindowsService` è un servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-111">The `CalculatorWindowsService` is a Windows service.</span></span> <span data-ttu-id="a7d3e-112">Per essere qualificata come servizio Windows, la classe eredita da `ServiceBase` e implementa i metodi `OnStart` e `OnStop`.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-112">To qualify as a Windows service, the class inherits from `ServiceBase` and implements the `OnStart` and `OnStop` methods.</span></span> <span data-ttu-id="a7d3e-113">In `OnStart`, viene creata e aperta una classe <xref:System.ServiceModel.ServiceHost> per il tipo `CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-113">In `OnStart`, a <xref:System.ServiceModel.ServiceHost> is created for the `CalculatorService` type and opened.</span></span> <span data-ttu-id="a7d3e-114">In `OnStop`, il servizio viene interrotto ed eliminato.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-114">In `OnStop`, the service is stopped and disposed.</span></span> <span data-ttu-id="a7d3e-115">L'host è inoltre responsabile di fornire un indirizzo di base all'host del servizio, che è stato configurato nelle impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-115">The host is also responsible for providing a base address to the service host, which has been configured in application settings.</span></span> <span data-ttu-id="a7d3e-116">La classe del programma di installazione, che eredita da <xref:System.Configuration.Install.Installer>, consente al programma di essere installato come servizio Windows dallo strumento Installutil.exe.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-116">The installer class, which inherits from <xref:System.Configuration.Install.Installer>, allows the program to be installed as a Windows service by the Installutil.exe tool.</span></span>  
  
### <a name="construct-the-service-and-provide-the-hosting-code"></a><span data-ttu-id="a7d3e-117">Costruire il servizio e fornire il codice host</span><span class="sxs-lookup"><span data-stu-id="a7d3e-117">Construct the service and provide the hosting code</span></span>  
  
1.  <span data-ttu-id="a7d3e-118">Creare un nuovo progetto Applicazione console di Visual Studio denominato "Service".</span><span class="sxs-lookup"><span data-stu-id="a7d3e-118">Create a new Visual Studio Console Application project called "Service".</span></span>  
  
2.  <span data-ttu-id="a7d3e-119">Rinominare Program.cs come Service.cs.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-119">Rename Program.cs to Service.cs.</span></span>  
  
3.  <span data-ttu-id="a7d3e-120">Modificare lo spazio dei nomi in Microsoft.ServiceModel.Samples.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-120">Change the namespace to Microsoft.ServiceModel.Samples.</span></span>  
  
4.  <span data-ttu-id="a7d3e-121">Aggiungere riferimenti agli assembly indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-121">Add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="a7d3e-122">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="a7d3e-122">System.ServiceModel.dll</span></span>  
  
    -   <span data-ttu-id="a7d3e-123">System.ServiceProcess.dll</span><span class="sxs-lookup"><span data-stu-id="a7d3e-123">System.ServiceProcess.dll</span></span>  
  
    -   <span data-ttu-id="a7d3e-124">System.Configuration.Install.dll</span><span class="sxs-lookup"><span data-stu-id="a7d3e-124">System.Configuration.Install.dll</span></span>  
  
5.  <span data-ttu-id="a7d3e-125">Aggiungere le istruzioni using seguenti a Service.cs.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-125">Add the following using statements to Service.cs.</span></span>  
  
     [!code-csharp[c_HowTo_HostInNTService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#0)]
     [!code-vb[c_HowTo_HostInNTService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#0)]  
  
6.  <span data-ttu-id="a7d3e-126">Definire il contratto di servizio `ICalculator` come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-126">Define the `ICalculator` service contract as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInNTService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#1)]
     [!code-vb[c_HowTo_HostInNTService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#1)]  
  
7.  <span data-ttu-id="a7d3e-127">Implementare il contratto di servizio in una classe denominata `CalculatorService` come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-127">Implement the service contract in a class called `CalculatorService` as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInNTService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#2)]
     [!code-vb[c_HowTo_HostInNTService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#2)]  
  
8.  <span data-ttu-id="a7d3e-128">Creare una nuova classe denominata `CalculatorWindowsService` che eredita dalla classe <xref:System.ServiceProcess.ServiceBase>.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-128">Create a new class called `CalculatorWindowsService` that inherits from the <xref:System.ServiceProcess.ServiceBase> class.</span></span> <span data-ttu-id="a7d3e-129">Aggiungere una variabile locale denominata `serviceHost` per fare riferimento all'istanza di <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-129">Add a local variable called `serviceHost` to reference the <xref:System.ServiceModel.ServiceHost> instance.</span></span> <span data-ttu-id="a7d3e-130">Definire il metodo `Main` che chiama `ServiceBase.Run(new CalculatorWindowsService)`</span><span class="sxs-lookup"><span data-stu-id="a7d3e-130">Define the `Main` method that calls `ServiceBase.Run(new CalculatorWindowsService)`</span></span>  
  
     [!code-csharp[c_HowTo_HostInNTService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#3)]
     [!code-vb[c_HowTo_HostInNTService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#3)]  
  
9. <span data-ttu-id="a7d3e-131">Eseguire l'override del metodo <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> creando e aprendo una nuova istanza di <xref:System.ServiceModel.ServiceHost> come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-131">Override the <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> method by creating and opening a new <xref:System.ServiceModel.ServiceHost> instance as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInNTService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#4)]
     [!code-vb[c_HowTo_HostInNTService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#4)]  
  
10. <span data-ttu-id="a7d3e-132">Eseguire l'override del metodo <xref:System.ServiceProcess.ServiceBase.OnStop%2A> chiudendo <xref:System.ServiceModel.ServiceHost> come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-132">Override the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method closing the <xref:System.ServiceModel.ServiceHost> as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInNTService#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#5)]
     [!code-vb[c_HowTo_HostInNTService#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#5)]  
  
11. <span data-ttu-id="a7d3e-133">Creare una nuova classe denominata `ProjectInstaller` che eredita da <xref:System.Configuration.Install.Installer> e che sia contrassegnata con <xref:System.ComponentModel.RunInstallerAttribute> impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-133">Create a new class called `ProjectInstaller` that inherits from <xref:System.Configuration.Install.Installer> and that is marked with the <xref:System.ComponentModel.RunInstallerAttribute> set to `true`.</span></span> <span data-ttu-id="a7d3e-134">Questo consente l'installazione del servizio Windows mediante lo strumento Installutil.exe.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-134">This allows the Windows service to be installed by the Installutil.exe tool.</span></span>  
  
     [!code-csharp[c_HowTo_HostInNTService#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#6)]
     [!code-vb[c_HowTo_HostInNTService#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#6)]  
  
12. <span data-ttu-id="a7d3e-135">Rimuovere la classe `Service` generata al momento della creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-135">Remove the `Service` class that was generated when you created the project.</span></span>  
  
13. <span data-ttu-id="a7d3e-136">Aggiungere un file di configurazione dell'applicazione al progetto.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-136">Add an application configuration file to the project.</span></span> <span data-ttu-id="a7d3e-137">Sostituire il contenuto del file con l'XML di configurazione riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-137">Replace the contents of the file with the following configuration XML.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>    <services>  
          <!-- This section is optional with the new configuration model  
               introduced in .NET Framework 4. -->  
          <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
                   behaviorConfiguration="CalculatorServiceBehavior">  
            <host>  
              <baseAddresses>  
                <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
              </baseAddresses>  
            </host>  
            <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service  -->  
            <endpoint address=""  
                      binding="wsHttpBinding"  
                      contract="Microsoft.ServiceModel.Samples.ICalculator" />  
            <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->  
            <endpoint address="mex"  
                      binding="mexHttpBinding"  
                      contract="IMetadataExchange" />  
          </service>  
        </services>  
        <behaviors>  
          <serviceBehaviors>  
            <behavior name="CalculatorServiceBehavior">  
              <serviceMetadata httpGetEnabled="true"/>  
              <serviceDebug includeExceptionDetailInFaults="False"/>  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="a7d3e-138">A destra fare clic sul file app. config di **Esplora** e selezionare **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-138">Right click the App.config file in the **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="a7d3e-139">In **copia nella Directory di Output di** selezionare **copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-139">Under **Copy to Output Directory** select **Copy if Newer**.</span></span>  
  
     <span data-ttu-id="a7d3e-140">In questo esempio vengono specificati in modo esplicito gli endpoint del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-140">This example explicitly specifies endpoints in the configuration file.</span></span> <span data-ttu-id="a7d3e-141">Se non vengono aggiunti endpoint al servizio, il runtime aggiunge gli endpoint predefiniti.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-141">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> <span data-ttu-id="a7d3e-142">In questo esempio, poiché il servizio ha <xref:System.ServiceModel.Description.ServiceMetadataBehavior> impostato su `true`, è anche abilitata la pubblicazione di metadati.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-142">In this example, because the service has a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> set to `true`, your service also has publishing metadata enabled.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="a7d3e-143">gli endpoint predefiniti, associazioni e comportamenti, vedere [configurazione semplificata](../../../../docs/framework/wcf/simplified-configuration.md) e [configurazione semplificata per i servizi WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="a7d3e-143"> default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
### <a name="install-and-run-the-service"></a><span data-ttu-id="a7d3e-144">Installare ed eseguire il servizio .</span><span class="sxs-lookup"><span data-stu-id="a7d3e-144">Install and run the service</span></span>  
  
1.  <span data-ttu-id="a7d3e-145">Compilare la soluzione per creare l'eseguibile `Service.exe`.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-145">Build the solution to create the `Service.exe` executable.</span></span>  
  
2.  <span data-ttu-id="a7d3e-146">Aprire il prompt dei comandi di [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], quindi passare alla directory del progetto.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-146">Open the [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] command prompt and navigate to the project directory.</span></span> <span data-ttu-id="a7d3e-147">Digitare `installutil bin\service.exe` al prompt dei comandi per installare il servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-147">Type `installutil bin\service.exe` at the command prompt to install the Windows service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a7d3e-148">Se non si utilizza il prompt dei comandi di [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], verificare che la directory `%WinDir%\Microsoft.NET\Framework\v4.0.<current version>` si trovi nel percorso di sistema.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-148">If you do not use the [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] command prompt, make sure that the `%WinDir%\Microsoft.NET\Framework\v4.0.<current version>` directory is in the system path.</span></span>  
  
     <span data-ttu-id="a7d3e-149">Digitare `services.msc` al prompt dei comandi per accedere a Gestione controllo servizi (SCM).</span><span class="sxs-lookup"><span data-stu-id="a7d3e-149">Type `services.msc` at the command prompt to access the Service Control Manager (SCM).</span></span> <span data-ttu-id="a7d3e-150">Il servizio Windows verrà visualizzato in Servizi come "WCFWindowsServiceSample".</span><span class="sxs-lookup"><span data-stu-id="a7d3e-150">The Windows service should appear in Services as "WCFWindowsServiceSample".</span></span> <span data-ttu-id="a7d3e-151">Il servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] può rispondere ai client solo se il servizio Windows è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-151">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service can only respond to clients if the Windows service is running.</span></span> <span data-ttu-id="a7d3e-152">Per avviare il servizio, pulsante destro del mouse nella Gestione controllo servizi e selezionare "Start" o tipo **net start WCFWindowsServiceSample** al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-152">To start the service, right-click it in the SCM and select "Start", or type **net start WCFWindowsServiceSample** at the command prompt.</span></span>  
  
3.  <span data-ttu-id="a7d3e-153">Se si apportano modifiche al servizio, è prima necessario arrestare il servizio e disinstallarlo.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-153">If you make changes to the service, you must first stop it and uninstall it.</span></span> <span data-ttu-id="a7d3e-154">Per arrestare il servizio, il servizio in SCM destro e selezionare "Stop", o **stop net tipo WCFWindowsServiceSample** al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-154">To stop the service, right-click the service in the SCM and select "Stop", or **type net stop WCFWindowsServiceSample** at the command prompt.</span></span> <span data-ttu-id="a7d3e-155">Si noti che se si arresta il servizio Windows e quindi si esegue un client, si verificherà un'eccezione <xref:System.ServiceModel.EndpointNotFoundException> quando un client tenta di accedere al servizio.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-155">Note that if you stop the Windows service and then run a client, an <xref:System.ServiceModel.EndpointNotFoundException> exception occurs when a client attempts to access the service.</span></span> <span data-ttu-id="a7d3e-156">Per disinstallare il tipo di servizio Windows **bin\service.exe/u installutil** al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-156">To uninstall the Windows service type **installutil /u bin\service.exe** at the command prompt.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7d3e-157">Esempio</span><span class="sxs-lookup"><span data-stu-id="a7d3e-157">Example</span></span>  
 <span data-ttu-id="a7d3e-158">Di seguito è riportato un elenco completo del codice utilizzato da questo argomento.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-158">The following is a complete listing of the code used by this topic.</span></span>  
  
 [!code-csharp[c_HowTo_HostInNTService#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#8)]
 [!code-vb[c_HowTo_HostInNTService#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#8)]  
  
 <span data-ttu-id="a7d3e-159">Analogamente all'opzione di self-hosting, l'ambiente host del servizio Windows richiede che venga scritto codice di hosting come parte dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-159">Like the "Self-Hosting" option, the Windows service hosting environment requires that some hosting code be written as part of the application.</span></span> <span data-ttu-id="a7d3e-160">Il servizio viene implementato come applicazione console e contiene il proprio codice di hosting.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-160">The service is implemented as a console application and contains its own hosting code.</span></span> <span data-ttu-id="a7d3e-161">In altri ambienti host, quali ad esempio l'host del servizio di attivazione dei processi di Windows (WAS, Windows Process Activation Service) in Internet Information Services (IIS), non è necessario che gli sviluppatori scrivano codice di hosting.</span><span class="sxs-lookup"><span data-stu-id="a7d3e-161">In other hosting environments, such as Windows Process Activation Service (WAS) hosting in Internet Information Services (IIS), it is not necessary for developers to write hosting code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7d3e-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7d3e-162">See Also</span></span>  
 [<span data-ttu-id="a7d3e-163">Configurazione semplificata</span><span class="sxs-lookup"><span data-stu-id="a7d3e-163">Simplified Configuration</span></span>](../../../../docs/framework/wcf/simplified-configuration.md)  
 [<span data-ttu-id="a7d3e-164">Hosting in un'applicazione gestita</span><span class="sxs-lookup"><span data-stu-id="a7d3e-164">Hosting in a Managed Application</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md)  
 [<span data-ttu-id="a7d3e-165">Servizi di hosting</span><span class="sxs-lookup"><span data-stu-id="a7d3e-165">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)  
 [<span data-ttu-id="a7d3e-166">Windows Server AppFabric con funzionalità di Hosting</span><span class="sxs-lookup"><span data-stu-id="a7d3e-166">Windows Server App Fabric Hosting Features</span></span>](http://go.microsoft.com/fwlink/?LinkId=201276)
