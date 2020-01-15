---
title: 'Procedura: ospitare un servizio WCF in un servizio Windows gestito'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8e37363b-4dad-4fb6-907f-73c30fac1d9a
ms.openlocfilehash: 698a5134683341fedf2a37f7d6383770e14c232c
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964795"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-windows-service"></a><span data-ttu-id="f38e3-102">Procedura: ospitare un servizio WCF in un servizio Windows gestito</span><span class="sxs-lookup"><span data-stu-id="f38e3-102">How to: Host a WCF Service in a Managed Windows Service</span></span>

<span data-ttu-id="f38e3-103">In questo argomento vengono illustrati i passaggi di base necessari per creare un servizio Windows Communication Foundation (WCF) ospitato da un servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="f38e3-103">This topic outlines the basic steps required to create a Windows Communication Foundation (WCF) service that is hosted by a Windows Service.</span></span> <span data-ttu-id="f38e3-104">Lo scenario è abilitato dall'opzione di hosting del servizio Windows gestito che è un servizio WCF con esecuzione prolungata ospitato all'esterno di Internet Information Services (IIS) in un ambiente protetto che non viene attivato tramite messaggio.</span><span class="sxs-lookup"><span data-stu-id="f38e3-104">The scenario is enabled by the managed Windows service hosting option that is a long-running WCF service hosted outside of Internet Information Services (IIS) in a secure environment that is not message activated.</span></span> <span data-ttu-id="f38e3-105">La durata del servizio è controllata invece dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="f38e3-105">The lifetime of the service is controlled instead by the operating system.</span></span> <span data-ttu-id="f38e3-106">Questa opzione di hosting è disponibile in tutte le versioni di Windows.</span><span class="sxs-lookup"><span data-stu-id="f38e3-106">This hosting option is available in all versions of Windows.</span></span>

<span data-ttu-id="f38e3-107">I servizi Windows possono essere gestiti con Microsoft.ManagementConsole.SnapIn in Microsoft Management Console (MMC) e possono essere configurati per essere avviati automaticamente all'avvio del sistema.</span><span class="sxs-lookup"><span data-stu-id="f38e3-107">Windows services can be managed with the Microsoft.ManagementConsole.SnapIn in Microsoft Management Console (MMC) and can be configured to start up automatically when the system boots up.</span></span> <span data-ttu-id="f38e3-108">Questa opzione di hosting consiste nella registrazione del dominio applicazione (AppDomain) che ospita un servizio WCF come servizio Windows gestito, in modo che la durata del processo del servizio sia controllata da Gestione controllo servizi (SCM) per i servizi Windows.</span><span class="sxs-lookup"><span data-stu-id="f38e3-108">This hosting option consists of registering the application domain (AppDomain) that hosts a WCF service as a managed Windows service so that the process lifetime of the service is controlled by the Service Control Manager (SCM) for Windows services.</span></span>

<span data-ttu-id="f38e3-109">Il codice del servizio include un'implementazione del contratto di servizio, una classe di servizio Windows e una classe del programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="f38e3-109">The service code includes a service implementation of the service contract, a Windows Service class, and an installer class.</span></span> <span data-ttu-id="f38e3-110">La classe di implementazione del servizio, `CalculatorService`, è un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="f38e3-110">The service implementation class, `CalculatorService`, is a WCF service.</span></span> <span data-ttu-id="f38e3-111">`CalculatorWindowsService` è un servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="f38e3-111">The `CalculatorWindowsService` is a Windows service.</span></span> <span data-ttu-id="f38e3-112">Per essere qualificata come servizio Windows, la classe eredita da `ServiceBase` e implementa i metodi `OnStart` e `OnStop`.</span><span class="sxs-lookup"><span data-stu-id="f38e3-112">To qualify as a Windows service, the class inherits from `ServiceBase` and implements the `OnStart` and `OnStop` methods.</span></span> <span data-ttu-id="f38e3-113">In `OnStart`, viene creata e aperta una classe <xref:System.ServiceModel.ServiceHost> per il tipo `CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="f38e3-113">In `OnStart`, a <xref:System.ServiceModel.ServiceHost> is created for the `CalculatorService` type and opened.</span></span> <span data-ttu-id="f38e3-114">In `OnStop`, il servizio viene interrotto ed eliminato.</span><span class="sxs-lookup"><span data-stu-id="f38e3-114">In `OnStop`, the service is stopped and disposed.</span></span> <span data-ttu-id="f38e3-115">L'host è inoltre responsabile di fornire un indirizzo di base all'host del servizio, che è stato configurato nelle impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f38e3-115">The host is also responsible for providing a base address to the service host, which has been configured in application settings.</span></span> <span data-ttu-id="f38e3-116">La classe del programma di installazione, che eredita da <xref:System.Configuration.Install.Installer>, consente al programma di essere installato come servizio Windows dallo strumento Installutil.exe.</span><span class="sxs-lookup"><span data-stu-id="f38e3-116">The installer class, which inherits from <xref:System.Configuration.Install.Installer>, allows the program to be installed as a Windows service by the Installutil.exe tool.</span></span>

## <a name="construct-the-service-and-provide-the-hosting-code"></a><span data-ttu-id="f38e3-117">Costruire il servizio e fornire il codice host</span><span class="sxs-lookup"><span data-stu-id="f38e3-117">Construct the service and provide the hosting code</span></span>

1. <span data-ttu-id="f38e3-118">Creare un nuovo progetto di **app console** di Visual Studio denominato **servizio**.</span><span class="sxs-lookup"><span data-stu-id="f38e3-118">Create a new Visual Studio **Console app** project called **Service**.</span></span>

2. <span data-ttu-id="f38e3-119">Rinominare Program.cs come Service.cs.</span><span class="sxs-lookup"><span data-stu-id="f38e3-119">Rename Program.cs to Service.cs.</span></span>

3. <span data-ttu-id="f38e3-120">Modificare lo spazio dei nomi in `Microsoft.ServiceModel.Samples`.</span><span class="sxs-lookup"><span data-stu-id="f38e3-120">Change the namespace to `Microsoft.ServiceModel.Samples`.</span></span>

4. <span data-ttu-id="f38e3-121">Aggiungere riferimenti agli assembly riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="f38e3-121">Add references to the following assemblies:</span></span>

    - <span data-ttu-id="f38e3-122">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="f38e3-122">System.ServiceModel.dll</span></span>

    - <span data-ttu-id="f38e3-123">System.ServiceProcess.dll</span><span class="sxs-lookup"><span data-stu-id="f38e3-123">System.ServiceProcess.dll</span></span>

    - <span data-ttu-id="f38e3-124">System.Configuration.Install.dll</span><span class="sxs-lookup"><span data-stu-id="f38e3-124">System.Configuration.Install.dll</span></span>

5. <span data-ttu-id="f38e3-125">Aggiungere le istruzioni using seguenti a Service.cs.</span><span class="sxs-lookup"><span data-stu-id="f38e3-125">Add the following using statements to Service.cs.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#0)]
     [!code-vb[c_HowTo_HostInNTService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#0)]

6. <span data-ttu-id="f38e3-126">Definire il contratto di servizio `ICalculator` come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f38e3-126">Define the `ICalculator` service contract as shown in the following code.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#1)]
     [!code-vb[c_HowTo_HostInNTService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#1)]

7. <span data-ttu-id="f38e3-127">Implementare il contratto di servizio in una classe denominata `CalculatorService` come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f38e3-127">Implement the service contract in a class called `CalculatorService` as shown in the following code.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#2)]
     [!code-vb[c_HowTo_HostInNTService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#2)]

8. <span data-ttu-id="f38e3-128">Creare una nuova classe denominata `CalculatorWindowsService` che eredita dalla classe <xref:System.ServiceProcess.ServiceBase>.</span><span class="sxs-lookup"><span data-stu-id="f38e3-128">Create a new class called `CalculatorWindowsService` that inherits from the <xref:System.ServiceProcess.ServiceBase> class.</span></span> <span data-ttu-id="f38e3-129">Aggiungere una variabile locale denominata `serviceHost` per fare riferimento all'istanza di <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="f38e3-129">Add a local variable called `serviceHost` to reference the <xref:System.ServiceModel.ServiceHost> instance.</span></span> <span data-ttu-id="f38e3-130">Definire il metodo `Main` che chiama `ServiceBase.Run(new CalculatorWindowsService)`</span><span class="sxs-lookup"><span data-stu-id="f38e3-130">Define the `Main` method that calls `ServiceBase.Run(new CalculatorWindowsService)`</span></span>

     [!code-csharp[c_HowTo_HostInNTService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#3)]
     [!code-vb[c_HowTo_HostInNTService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#3)]

9. <span data-ttu-id="f38e3-131">Eseguire l'override del metodo <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> creando e aprendo una nuova istanza di <xref:System.ServiceModel.ServiceHost> come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f38e3-131">Override the <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> method by creating and opening a new <xref:System.ServiceModel.ServiceHost> instance as shown in the following code.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#4)]
     [!code-vb[c_HowTo_HostInNTService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#4)]

10. <span data-ttu-id="f38e3-132">Eseguire l'override del metodo <xref:System.ServiceProcess.ServiceBase.OnStop%2A> chiudendo <xref:System.ServiceModel.ServiceHost> come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f38e3-132">Override the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method closing the <xref:System.ServiceModel.ServiceHost> as shown in the following code.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#5)]
     [!code-vb[c_HowTo_HostInNTService#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#5)]

11. <span data-ttu-id="f38e3-133">Creare una nuova classe denominata `ProjectInstaller` che eredita da <xref:System.Configuration.Install.Installer> e che sia contrassegnata con <xref:System.ComponentModel.RunInstallerAttribute> impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="f38e3-133">Create a new class called `ProjectInstaller` that inherits from <xref:System.Configuration.Install.Installer> and that is marked with the <xref:System.ComponentModel.RunInstallerAttribute> set to `true`.</span></span> <span data-ttu-id="f38e3-134">Questo consente l'installazione del servizio Windows mediante lo strumento Installutil.exe.</span><span class="sxs-lookup"><span data-stu-id="f38e3-134">This allows the Windows service to be installed by the Installutil.exe tool.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#6)]
     [!code-vb[c_HowTo_HostInNTService#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#6)]

12. <span data-ttu-id="f38e3-135">Rimuovere la classe `Service` generata al momento della creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="f38e3-135">Remove the `Service` class that was generated when you created the project.</span></span>

13. <span data-ttu-id="f38e3-136">Aggiungere un file di configurazione dell'applicazione al progetto.</span><span class="sxs-lookup"><span data-stu-id="f38e3-136">Add an application configuration file to the project.</span></span> <span data-ttu-id="f38e3-137">Sostituire il contenuto del file con l'XML di configurazione riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="f38e3-137">Replace the contents of the file with the following configuration XML.</span></span>

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

     <span data-ttu-id="f38e3-138">Fare clic con il pulsante destro del mouse sul file app. config nel **Esplora soluzioni** e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="f38e3-138">Right click the App.config file in the **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="f38e3-139">In **copia nella directory di output** selezionare **copia se più recente**.</span><span class="sxs-lookup"><span data-stu-id="f38e3-139">Under **Copy to Output Directory** select **Copy if Newer**.</span></span>

     <span data-ttu-id="f38e3-140">In questo esempio vengono specificati in modo esplicito gli endpoint del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f38e3-140">This example explicitly specifies endpoints in the configuration file.</span></span> <span data-ttu-id="f38e3-141">Se non vengono aggiunti endpoint al servizio, il runtime aggiunge gli endpoint predefiniti.</span><span class="sxs-lookup"><span data-stu-id="f38e3-141">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> <span data-ttu-id="f38e3-142">In questo esempio, poiché il servizio ha <xref:System.ServiceModel.Description.ServiceMetadataBehavior> impostato su `true`, è anche abilitata la pubblicazione di metadati.</span><span class="sxs-lookup"><span data-stu-id="f38e3-142">In this example, because the service has a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> set to `true`, your service also has publishing metadata enabled.</span></span> <span data-ttu-id="f38e3-143">Per altre informazioni su endpoint, associazioni e comportamenti predefiniti, vedere [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) (Configurazione semplificata) e [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md) (Configurazione semplificata per servizi WCF).</span><span class="sxs-lookup"><span data-stu-id="f38e3-143">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>

## <a name="install-and-run-the-service"></a><span data-ttu-id="f38e3-144">Installare ed eseguire il servizio .</span><span class="sxs-lookup"><span data-stu-id="f38e3-144">Install and run the service</span></span>

1. <span data-ttu-id="f38e3-145">Compilare la soluzione per creare l'eseguibile `Service.exe`.</span><span class="sxs-lookup"><span data-stu-id="f38e3-145">Build the solution to create the `Service.exe` executable.</span></span>

2. <span data-ttu-id="f38e3-146">Aprire Prompt dei comandi per gli sviluppatori per Visual Studio e passare alla directory del progetto.</span><span class="sxs-lookup"><span data-stu-id="f38e3-146">Open Developer Command Prompt for Visual Studio and navigate to the project directory.</span></span> <span data-ttu-id="f38e3-147">Digitare `installutil bin\service.exe` al prompt dei comandi per installare il servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="f38e3-147">Type `installutil bin\service.exe` at the command prompt to install the Windows service.</span></span>

     <span data-ttu-id="f38e3-148">Digitare `services.msc` al prompt dei comandi per accedere a Gestione controllo servizi (SCM).</span><span class="sxs-lookup"><span data-stu-id="f38e3-148">Type `services.msc` at the command prompt to access the Service Control Manager (SCM).</span></span> <span data-ttu-id="f38e3-149">Il servizio Windows verrà visualizzato in Servizi come "WCFWindowsServiceSample".</span><span class="sxs-lookup"><span data-stu-id="f38e3-149">The Windows service should appear in Services as "WCFWindowsServiceSample".</span></span> <span data-ttu-id="f38e3-150">Il servizio WCF può rispondere ai client solo se il servizio Windows è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f38e3-150">The WCF service can only respond to clients if the Windows service is running.</span></span> <span data-ttu-id="f38e3-151">Per avviare il servizio, fare clic con il pulsante destro del mouse su di esso in Gestione controllo servizi e scegliere "Avvia" oppure digitare **net start WCFWindowsServiceSample** al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="f38e3-151">To start the service, right-click it in the SCM and select "Start", or type **net start WCFWindowsServiceSample** at the command prompt.</span></span>

3. <span data-ttu-id="f38e3-152">Se si apportano modifiche al servizio, è prima necessario arrestare il servizio e disinstallarlo.</span><span class="sxs-lookup"><span data-stu-id="f38e3-152">If you make changes to the service, you must first stop it and uninstall it.</span></span> <span data-ttu-id="f38e3-153">Per arrestare il servizio, fare clic con il pulsante destro del mouse sul servizio in SCM e selezionare "arresta" oppure **digitare net stop WCFWindowsServiceSample** al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="f38e3-153">To stop the service, right-click the service in the SCM and select "Stop", or **type net stop WCFWindowsServiceSample** at the command prompt.</span></span> <span data-ttu-id="f38e3-154">Si noti che se si arresta il servizio Windows e quindi si esegue un client, si verificherà un'eccezione <xref:System.ServiceModel.EndpointNotFoundException> quando un client tenta di accedere al servizio.</span><span class="sxs-lookup"><span data-stu-id="f38e3-154">Note that if you stop the Windows service and then run a client, an <xref:System.ServiceModel.EndpointNotFoundException> exception occurs when a client attempts to access the service.</span></span> <span data-ttu-id="f38e3-155">Per disinstallare il servizio Windows digitare **installutil/u bin\service.exe** al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="f38e3-155">To uninstall the Windows service type **installutil /u bin\service.exe** at the command prompt.</span></span>

## <a name="example"></a><span data-ttu-id="f38e3-156">Esempio</span><span class="sxs-lookup"><span data-stu-id="f38e3-156">Example</span></span>

<span data-ttu-id="f38e3-157">Di seguito è riportato un elenco completo del codice utilizzato in questo argomento:</span><span class="sxs-lookup"><span data-stu-id="f38e3-157">The following is a complete listing of the code used by this topic:</span></span>

[!code-csharp[c_HowTo_HostInNTService#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#8)]
[!code-vb[c_HowTo_HostInNTService#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#8)]

<span data-ttu-id="f38e3-158">Analogamente all'opzione di self-hosting, l'ambiente host del servizio Windows richiede che venga scritto codice di hosting come parte dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f38e3-158">Like the "Self-Hosting" option, the Windows service hosting environment requires that some hosting code be written as part of the application.</span></span> <span data-ttu-id="f38e3-159">Il servizio viene implementato come applicazione console e contiene il proprio codice di hosting.</span><span class="sxs-lookup"><span data-stu-id="f38e3-159">The service is implemented as a console application and contains its own hosting code.</span></span> <span data-ttu-id="f38e3-160">In altri ambienti host, quali ad esempio l'host del servizio di attivazione dei processi di Windows (WAS, Windows Process Activation Service) in Internet Information Services (IIS), non è necessario che gli sviluppatori scrivano codice di hosting.</span><span class="sxs-lookup"><span data-stu-id="f38e3-160">In other hosting environments, such as Windows Process Activation Service (WAS) hosting in Internet Information Services (IIS), it is not necessary for developers to write hosting code.</span></span>

## <a name="see-also"></a><span data-ttu-id="f38e3-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f38e3-161">See also</span></span>

- [<span data-ttu-id="f38e3-162">Configurazione semplificata</span><span class="sxs-lookup"><span data-stu-id="f38e3-162">Simplified Configuration</span></span>](../../../../docs/framework/wcf/simplified-configuration.md)
- [<span data-ttu-id="f38e3-163">Hosting in un'applicazione gestita</span><span class="sxs-lookup"><span data-stu-id="f38e3-163">Hosting in a Managed Application</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md)
- [<span data-ttu-id="f38e3-164">Servizi di hosting</span><span class="sxs-lookup"><span data-stu-id="f38e3-164">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
- <span data-ttu-id="f38e3-165">[Funzionalità di hosting di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="f38e3-165">[Windows Server App Fabric Hosting Features](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span></span>
