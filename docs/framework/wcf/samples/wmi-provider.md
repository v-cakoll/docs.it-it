---
title: Provider WMI
ms.date: 03/30/2017
ms.assetid: 462f0db3-f4a4-4a4b-ac26-41fc25c670a4
ms.openlocfilehash: 04fdbb7efcae6fdbb78f467352e6106ac5218799
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183196"
---
# <a name="wmi-provider"></a><span data-ttu-id="3366c-102">Provider WMI</span><span class="sxs-lookup"><span data-stu-id="3366c-102">WMI Provider</span></span>
<span data-ttu-id="3366c-103">In questo esempio viene illustrato come raccogliere dati dai servizi Windows Communication Foundation (WCF) in fase di esecuzione utilizzando il provider di Strumentazione gestione Windows (WMI) incorporato in WCF.</span><span class="sxs-lookup"><span data-stu-id="3366c-103">This sample demonstrates how to gather data from Windows Communication Foundation (WCF) services at runtime by using the Windows Management Instrumentation (WMI) provider that is built into WCF.</span></span> <span data-ttu-id="3366c-104">Viene inoltre illustrato come aggiungere un oggetto WMI definito dall'utente a un servizio.</span><span class="sxs-lookup"><span data-stu-id="3366c-104">Also, this sample demonstrates how to add a user-defined WMI object to a service.</span></span> <span data-ttu-id="3366c-105">Nell'esempio viene attivato il provider WMI per la Guida `ICalculator` [introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md) e viene illustrato come raccogliere dati dal servizio in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3366c-105">The sample activates the WMI provider for the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and demonstrates how to gather data from the `ICalculator` service at runtime.</span></span>  
  
 <span data-ttu-id="3366c-106">WMI è l'implementazione Microsoft dello standard WBEM (Web-Based Enterprise Management).</span><span class="sxs-lookup"><span data-stu-id="3366c-106">WMI is Microsoft's implementation of the Web-Based Enterprise Management (WBEM) standard.</span></span> <span data-ttu-id="3366c-107">Per ulteriori informazioni su WMI SDK, vedere [Strumentazione gestione Windows.](/windows/desktop/WmiSdk/wmi-start-page)</span><span class="sxs-lookup"><span data-stu-id="3366c-107">For more information about the WMI SDK, see [Windows Management Instrumentation](/windows/desktop/WmiSdk/wmi-start-page).</span></span> <span data-ttu-id="3366c-108">WBEM è uno standard industriale che definisce la modalità in cui le applicazioni espongono la strumentazione della gestione a strumenti di gestione esterni.</span><span class="sxs-lookup"><span data-stu-id="3366c-108">WBEM is an industry standard for how applications expose management instrumentation to external management tools.</span></span>  
  
 <span data-ttu-id="3366c-109">WCF implementa un provider WMI, un componente che espone la strumentazione in fase di esecuzione tramite un'interfaccia compatibile con WBEM.</span><span class="sxs-lookup"><span data-stu-id="3366c-109">WCF implements a WMI provider, a component that exposes instrumentation at runtime through a WBEM-compatible interface.</span></span> <span data-ttu-id="3366c-110">Gli strumenti di gestione sono in grado di connettersi ai servizi attraverso l'interfaccia in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3366c-110">Management tools can connect to the services through the interface at runtime.</span></span> <span data-ttu-id="3366c-111">WCF espone gli attributi dei servizi, ad esempio indirizzi, associazioni, comportamenti e listener.</span><span class="sxs-lookup"><span data-stu-id="3366c-111">WCF exposes attributes of services such as addresses, bindings, behaviors, and listeners.</span></span>  
  
 <span data-ttu-id="3366c-112">Il provider WMI incorporato viene attivato nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3366c-112">The built-in WMI provider is activated in the configuration file of the application.</span></span> <span data-ttu-id="3366c-113">Questa operazione viene `wmiProviderEnabled` eseguita tramite l'attributo del>di [ \<diagnostica](../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) nella sezione [ \<>system.serviceModel,](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) come illustrato nella configurazione di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="3366c-113">This is done through the `wmiProviderEnabled` attribute of the [\<diagnostics>](../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) in the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) section, as shown in the following sample configuration:</span></span>  
  
```xml  
<system.serviceModel>  
    ...  
    <diagnostics wmiProviderEnabled="true" />  
    ...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="3366c-114">Questa voce di configurazione espone un'interfaccia WMI.</span><span class="sxs-lookup"><span data-stu-id="3366c-114">This configuration entry exposes a WMI interface.</span></span> <span data-ttu-id="3366c-115">Le applicazioni di gestione possono ora connettersi usando questa interfaccia e accedere la strumentazione di gestione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3366c-115">Management applications can now connect through this interface and access the management instrumentation of the application.</span></span>  
  
## <a name="custom-wmi-object"></a><span data-ttu-id="3366c-116">Oggetto WMI personalizzato</span><span class="sxs-lookup"><span data-stu-id="3366c-116">Custom WMI Object</span></span>  
 <span data-ttu-id="3366c-117">L'aggiunta di oggetti WMI a un servizio rende possibile la rivelazione di informazioni definite dall'utente insieme alle informazioni del provider WMI incorporato.</span><span class="sxs-lookup"><span data-stu-id="3366c-117">Adding WMI objects to a service makes it possible to reveal user-defined information along with the built-in WMI provider information.</span></span> <span data-ttu-id="3366c-118">Questa operazione viene eseguita pubblicando lo schema del servizio in WMI usando l'applicazione Installutil.exe.</span><span class="sxs-lookup"><span data-stu-id="3366c-118">This is accomplished by publishing the schema of the service to WMI by using the Installutil.exe application.</span></span> <span data-ttu-id="3366c-119">Le istruzioni per svolgere questa operazione, insieme ad altri dettagli, sono disponibili tra le istruzioni di installazione alla fine dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="3366c-119">Instructions to accomplish this, along with more details can be found in the setup instructions at the end of the topic.</span></span>  
  
## <a name="accessing-wmi-information"></a><span data-ttu-id="3366c-120">Accesso alle informazioni WMI</span><span class="sxs-lookup"><span data-stu-id="3366c-120">Accessing WMI Information</span></span>  

<span data-ttu-id="3366c-121">L'accesso ai dati WMI può essere eseguito in molti modi diversi.</span><span class="sxs-lookup"><span data-stu-id="3366c-121">WMI data can be accessed in many different ways.</span></span> <span data-ttu-id="3366c-122">Microsoft fornisce le API WMI per gli script, le applicazioni di Visual Basic, le applicazioni in C e .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3366c-122">Microsoft provides WMI APIs for scripts, Visual Basic applications, C++ applications, and the .NET Framework.</span></span> <span data-ttu-id="3366c-123">Per ulteriori informazioni, vedere [Utilizzo di WMI](/windows/desktop/wmisdk/using-wmi).</span><span class="sxs-lookup"><span data-stu-id="3366c-123">For more information, see [Using WMI](/windows/desktop/wmisdk/using-wmi).</span></span>
  
 <span data-ttu-id="3366c-124">In questo esempio vengono utilizzati due script Java: uno per enumerare i servizi in esecuzione nel computer con alcune delle relative proprietà e il secondo per visualizzare i dati WMI definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="3366c-124">This sample uses two Java scripts: one to enumerate services running on the computer along with some of their properties and the second to view user-defined WMI data.</span></span> <span data-ttu-id="3366c-125">Lo script apre una connessione al provider WMI, analizza i dati e visualizza i dati raccolti.</span><span class="sxs-lookup"><span data-stu-id="3366c-125">The script opens a connection to the WMI provider, parses data, and displays the data gathered.</span></span>  
  
 <span data-ttu-id="3366c-126">Avviare l'esempio per creare un'istanza in esecuzione di un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="3366c-126">Start the sample to create a running instance of a WCF service.</span></span> <span data-ttu-id="3366c-127">Mentre il servizio è in esecuzione, eseguire ogni script Java utilizzando il comando seguente nel prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="3366c-127">While the service is running, run each Java script by using the following command at the command prompt:</span></span>  
  
```console  
cscript EnumerateServices.js  
```  
  
 <span data-ttu-id="3366c-128">Lo script accede alla strumentazione contenuta nel servizio e produce l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="3366c-128">The script accesses the instrumentation contained in the service and produces the following output:</span></span>  
  
```console  
Microsoft (R) Windows Script Host Version 5.6  
Copyright © Microsoft Corporation 1996-2001. All rights reserved.  
  
1 service(s) found.  
|-PID:           5776  
|-DistinguishedName:  CalculatorService@http://localhost/ServiceModelSamples/service.svc  
|-Endpoints:     1 endpoints  
  |-CalculatorService.ICalculator@http://localhost/ServiceModelSamples/service.svc  
    |-Address:                        http://localhost/ServiceModelSamples/service.svc  
    |-CounterInstanceName:  
    |-AddressHeaders:                 0  
    |-ContractType:                   Contract.Name='ICalculator'  
    |-BindingElements:                4 bindings  
      |-BindingElements[0]  
        |-Type:                       TransactionFlowBindingElement  
      |-BindingElements[1]  
        |-Type:                       SymmetricSecurityBindingElement  
      |-BindingElements[2]  
        |-Type:                       TextMessageEncodingBindingElement  
        |-MaxReadPoolSize:            64  
        |-MaxWritePoolSize:           16  
      |-BindingElements[3]  
        |-Type:                       HttpTransportBindingElement  
        |-ManualAddressing:           false  
        |-MaxBufferSize:              65536  
        |-AllowCookies:               false  
        |-AuthenticationScheme:       Anonymous  
        |-BypassProxyOnLocal:         false  
        |-HostNameComparisonMode:     StrongWildcard  
        |-ProxyAddress:               null  
        |-ProxyAuthenticationScheme:  Anonymous  
        |-Realm:  
        |-TransferMode:               Buffered  
        |-UseDefaultWebProxy:         true  
|-Behaviors:     5 behaviors  
      |-Behavior[0]  
      |-Type:                       ServiceBehaviorAttribute  
        |-AddressFilterMode:               Exact  
        |-AutomaticSessionShutdown:        true  
        |-ConcurrencyMode:                 Single  
        |-IncludeExceptionDetailInFaults:  false  
        |-InstanceContextMode:             PerSession  
        |-TransactionIsolationLevel:       Unspecified  
        |-TransactionTimeout:              null  
        |-ValidateMustUnderstand:          true  
      |-Behavior[1]  
      |-Type:                       AspNetCompatibilityRequirementsAttribute  
      |-Behavior[2]  
      |-Type:                       ServiceDebugBehavior  
      |-Behavior[3]  
      |-Type:                       ServiceAuthorizationBehavior  
      |-Behavior[4]  
      |-Type:                       Behavior  
```  
  
 <span data-ttu-id="3366c-129">Eseguire quindi il secondo script Java per visualizzare i dati WMI definiti dall'utente:</span><span class="sxs-lookup"><span data-stu-id="3366c-129">Next, run the second Java Script to display the user-defined WMI data:</span></span>  
  
```console  
cscript EnumerateCustomObjects.js  
```  
  
 <span data-ttu-id="3366c-130">Lo script accede alla strumentazione definita dall'utente contenuta nei servizi e produce l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="3366c-130">The script accesses the user-defined instrumentation contained in the services and produces the following output:</span></span>  
  
```console
1 WMIObject(s) found.  
|-PID:           30285bfd-9d66-4c4e-9be2-310499c5cef5  
|-InstanceId:    3839  
|-WMIInfo:       User Defined WMI Information.  
```  
  
 <span data-ttu-id="3366c-131">L'output mostra che nel computer è in esecuzione un solo servizio.</span><span class="sxs-lookup"><span data-stu-id="3366c-131">The output shows that there is a single service running on the computer.</span></span> <span data-ttu-id="3366c-132">Il servizio espone un endpoint che implementa il contratto `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="3366c-132">The service exposes one endpoint that implements the `ICalculator` contract.</span></span> <span data-ttu-id="3366c-133">Le impostazioni del comportamento e l'associazione implementate dall'endpoint sono elencate come la somma dei singoli elementi dello stack di messaggistica.</span><span class="sxs-lookup"><span data-stu-id="3366c-133">The settings of the behavior and binding that are implemented by the endpoint are listed as the sum of individual elements of the messaging stack.</span></span>  
  
 <span data-ttu-id="3366c-134">WMI non si limita a esporre la strumentazione di gestione dell'infrastruttura WCF.</span><span class="sxs-lookup"><span data-stu-id="3366c-134">WMI is not limited to exposing the management instrumentation of the WCF infrastructure.</span></span> <span data-ttu-id="3366c-135">Mediante lo stesso meccanismo l'applicazione può esporre dati specifici del dominio.</span><span class="sxs-lookup"><span data-stu-id="3366c-135">The application can expose its own domain-specific data items through the same mechanism.</span></span> <span data-ttu-id="3366c-136">WMI è un meccanismo unificato per l'ispezione e il controllo di un servizio Web.</span><span class="sxs-lookup"><span data-stu-id="3366c-136">WMI is a unified mechanism for inspection and control of a Web service.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3366c-137">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="3366c-137">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="3366c-138">Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3366c-138">Ensure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="3366c-139">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3366c-139">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="3366c-140">Pubblicare lo schema dei servizi in WMI eseguendo InstallUtil.exe (il percorso predefinito per InstallUtil.exe è "%WINDIR%\Microsoft.NET\Framework\v4.0.303197") sul file service.dll nella directory di hosting.</span><span class="sxs-lookup"><span data-stu-id="3366c-140">Publish the services schema to WMI by running the InstallUtil.exe (the default locations for InstallUtil.exe is "%WINDIR%\Microsoft.NET\Framework\v4.0.30319") on the service.dll file in the hosting directory.</span></span> <span data-ttu-id="3366c-141">È necessario eseguire questo passaggio solo quando sono state apportate modifiche al file service.dll.</span><span class="sxs-lookup"><span data-stu-id="3366c-141">This step only needs to be executed when changes have been made to the service.dll file.</span></span>
  
4. <span data-ttu-id="3366c-142">Per eseguire l'esempio in una configurazione a singolo o tra computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3366c-142">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="3366c-143">Se è stato installato WCF dopo l'installazione di ASP.NET, potrebbe essere necessario eseguire "%WINDIR% Microsoft.Net.Framework ,v3.0 , Windows Communication Foundation , servicemodelreg.exe " -r -x per concedere all'account ASPNET l'autorizzazione a pubblicare oggetti WMI.</span><span class="sxs-lookup"><span data-stu-id="3366c-143">If you installed WCF after installing ASP.NET, you may need to run "%WINDIR%\ Microsoft.Net\Framework\v3.0\Windows Communication Foundation\servicemodelreg.exe " -r -x to give the ASPNET account permission to publish WMI objects.</span></span>  
  
5. <span data-ttu-id="3366c-144">Visualizzare i dati dall'esempio riportato tramite WMI utilizzando i comandi: `cscript EnumerateServices.js` o `cscript EnumerateCustomObjects.js`.</span><span class="sxs-lookup"><span data-stu-id="3366c-144">View data from the sample surfaced through WMI by using the commands: `cscript EnumerateServices.js` or `cscript EnumerateCustomObjects.js`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3366c-145">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="3366c-145">The samples may already be installed on your computer.</span></span> <span data-ttu-id="3366c-146">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="3366c-146">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="3366c-147">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="3366c-147">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3366c-148">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="3366c-148">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\WMIProvider`  
  
## <a name="see-also"></a><span data-ttu-id="3366c-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3366c-149">See also</span></span>

- <span data-ttu-id="3366c-150">[Monitoraggio](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="3366c-150">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
