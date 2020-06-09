---
title: Provider WMI
ms.date: 03/30/2017
ms.assetid: 462f0db3-f4a4-4a4b-ac26-41fc25c670a4
ms.openlocfilehash: a01b4b70d4c497d1efb93bb53a7339f5f7f29ef9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84591046"
---
# <a name="wmi-provider"></a><span data-ttu-id="a3000-102">Provider WMI</span><span class="sxs-lookup"><span data-stu-id="a3000-102">WMI Provider</span></span>
<span data-ttu-id="a3000-103">In questo esempio viene illustrato come raccogliere dati dai servizi Windows Communication Foundation (WCF) in fase di esecuzione utilizzando il provider di Strumentazione gestione Windows (WMI) incorporato in WCF.</span><span class="sxs-lookup"><span data-stu-id="a3000-103">This sample demonstrates how to gather data from Windows Communication Foundation (WCF) services at runtime by using the Windows Management Instrumentation (WMI) provider that is built into WCF.</span></span> <span data-ttu-id="a3000-104">Viene inoltre illustrato come aggiungere un oggetto WMI definito dall'utente a un servizio.</span><span class="sxs-lookup"><span data-stu-id="a3000-104">Also, this sample demonstrates how to add a user-defined WMI object to a service.</span></span> <span data-ttu-id="a3000-105">L'esempio attiva il provider WMI per la [Introduzione](getting-started-sample.md) e illustra come raccogliere dati dal `ICalculator` servizio in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a3000-105">The sample activates the WMI provider for the [Getting Started](getting-started-sample.md) and demonstrates how to gather data from the `ICalculator` service at runtime.</span></span>  
  
 <span data-ttu-id="a3000-106">WMI è l'implementazione Microsoft dello standard WBEM (Web-Based Enterprise Management).</span><span class="sxs-lookup"><span data-stu-id="a3000-106">WMI is Microsoft's implementation of the Web-Based Enterprise Management (WBEM) standard.</span></span> <span data-ttu-id="a3000-107">Per ulteriori informazioni su WMI SDK, vedere [Strumentazione gestione Windows](/windows/desktop/WmiSdk/wmi-start-page).</span><span class="sxs-lookup"><span data-stu-id="a3000-107">For more information about the WMI SDK, see [Windows Management Instrumentation](/windows/desktop/WmiSdk/wmi-start-page).</span></span> <span data-ttu-id="a3000-108">WBEM è uno standard industriale che definisce la modalità in cui le applicazioni espongono la strumentazione della gestione a strumenti di gestione esterni.</span><span class="sxs-lookup"><span data-stu-id="a3000-108">WBEM is an industry standard for how applications expose management instrumentation to external management tools.</span></span>  
  
 <span data-ttu-id="a3000-109">WCF implementa un provider WMI, un componente che espone la strumentazione in fase di esecuzione tramite un'interfaccia compatibile con WBEM.</span><span class="sxs-lookup"><span data-stu-id="a3000-109">WCF implements a WMI provider, a component that exposes instrumentation at runtime through a WBEM-compatible interface.</span></span> <span data-ttu-id="a3000-110">Gli strumenti di gestione sono in grado di connettersi ai servizi attraverso l'interfaccia in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a3000-110">Management tools can connect to the services through the interface at runtime.</span></span> <span data-ttu-id="a3000-111">WCF espone attributi di servizi quali indirizzi, associazioni, comportamenti e listener.</span><span class="sxs-lookup"><span data-stu-id="a3000-111">WCF exposes attributes of services such as addresses, bindings, behaviors, and listeners.</span></span>  
  
 <span data-ttu-id="a3000-112">Il provider WMI incorporato viene attivato nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a3000-112">The built-in WMI provider is activated in the configuration file of the application.</span></span> <span data-ttu-id="a3000-113">Questa operazione viene eseguita tramite l' `wmiProviderEnabled` attributo di [\<diagnostics>](../../configure-apps/file-schema/wcf/diagnostics.md) nella [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) sezione, come illustrato nella configurazione di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="a3000-113">This is done through the `wmiProviderEnabled` attribute of the [\<diagnostics>](../../configure-apps/file-schema/wcf/diagnostics.md) in the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) section, as shown in the following sample configuration:</span></span>  
  
```xml  
<system.serviceModel>  
    ...  
    <diagnostics wmiProviderEnabled="true" />  
    ...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="a3000-114">Questa voce di configurazione espone un'interfaccia WMI.</span><span class="sxs-lookup"><span data-stu-id="a3000-114">This configuration entry exposes a WMI interface.</span></span> <span data-ttu-id="a3000-115">Le applicazioni di gestione possono ora connettersi usando questa interfaccia e accedere la strumentazione di gestione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a3000-115">Management applications can now connect through this interface and access the management instrumentation of the application.</span></span>  
  
## <a name="custom-wmi-object"></a><span data-ttu-id="a3000-116">Oggetto WMI personalizzato</span><span class="sxs-lookup"><span data-stu-id="a3000-116">Custom WMI Object</span></span>  
 <span data-ttu-id="a3000-117">L'aggiunta di oggetti WMI a un servizio rende possibile la rivelazione di informazioni definite dall'utente insieme alle informazioni del provider WMI incorporato.</span><span class="sxs-lookup"><span data-stu-id="a3000-117">Adding WMI objects to a service makes it possible to reveal user-defined information along with the built-in WMI provider information.</span></span> <span data-ttu-id="a3000-118">Questa operazione viene eseguita pubblicando lo schema del servizio in WMI usando l'applicazione Installutil.exe.</span><span class="sxs-lookup"><span data-stu-id="a3000-118">This is accomplished by publishing the schema of the service to WMI by using the Installutil.exe application.</span></span> <span data-ttu-id="a3000-119">Le istruzioni per svolgere questa operazione, insieme ad altri dettagli, sono disponibili tra le istruzioni di installazione alla fine dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="a3000-119">Instructions to accomplish this, along with more details can be found in the setup instructions at the end of the topic.</span></span>  
  
## <a name="accessing-wmi-information"></a><span data-ttu-id="a3000-120">Accesso alle informazioni WMI</span><span class="sxs-lookup"><span data-stu-id="a3000-120">Accessing WMI Information</span></span>  

<span data-ttu-id="a3000-121">L'accesso ai dati WMI può essere eseguito in molti modi diversi.</span><span class="sxs-lookup"><span data-stu-id="a3000-121">WMI data can be accessed in many different ways.</span></span> <span data-ttu-id="a3000-122">Microsoft fornisce le API WMI per gli script, Visual Basic applicazioni, le applicazioni C++ e i .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a3000-122">Microsoft provides WMI APIs for scripts, Visual Basic applications, C++ applications, and the .NET Framework.</span></span> <span data-ttu-id="a3000-123">Per ulteriori informazioni, vedere [utilizzo di WMI](/windows/desktop/wmisdk/using-wmi).</span><span class="sxs-lookup"><span data-stu-id="a3000-123">For more information, see [Using WMI](/windows/desktop/wmisdk/using-wmi).</span></span>
  
 <span data-ttu-id="a3000-124">In questo esempio vengono utilizzati due script Java: uno per enumerare i servizi in esecuzione nel computer con alcune delle relative proprietà e il secondo per visualizzare i dati WMI definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="a3000-124">This sample uses two Java scripts: one to enumerate services running on the computer along with some of their properties and the second to view user-defined WMI data.</span></span> <span data-ttu-id="a3000-125">Lo script apre una connessione al provider WMI, analizza i dati e visualizza i dati raccolti.</span><span class="sxs-lookup"><span data-stu-id="a3000-125">The script opens a connection to the WMI provider, parses data, and displays the data gathered.</span></span>  
  
 <span data-ttu-id="a3000-126">Avviare l'esempio per creare un'istanza in esecuzione di un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="a3000-126">Start the sample to create a running instance of a WCF service.</span></span> <span data-ttu-id="a3000-127">Mentre il servizio è in esecuzione, eseguire ogni script Java utilizzando il comando seguente nel prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="a3000-127">While the service is running, run each Java script by using the following command at the command prompt:</span></span>  
  
```console  
cscript EnumerateServices.js  
```  
  
 <span data-ttu-id="a3000-128">Lo script accede alla strumentazione contenuta nel servizio e produce l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="a3000-128">The script accesses the instrumentation contained in the service and produces the following output:</span></span>  
  
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
  
 <span data-ttu-id="a3000-129">Eseguire quindi il secondo script Java per visualizzare i dati WMI definiti dall'utente:</span><span class="sxs-lookup"><span data-stu-id="a3000-129">Next, run the second Java Script to display the user-defined WMI data:</span></span>  
  
```console  
cscript EnumerateCustomObjects.js  
```  
  
 <span data-ttu-id="a3000-130">Lo script accede alla strumentazione definita dall'utente contenuta nei servizi e produce l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="a3000-130">The script accesses the user-defined instrumentation contained in the services and produces the following output:</span></span>  
  
```console
1 WMIObject(s) found.  
|-PID:           30285bfd-9d66-4c4e-9be2-310499c5cef5  
|-InstanceId:    3839  
|-WMIInfo:       User Defined WMI Information.  
```  
  
 <span data-ttu-id="a3000-131">L'output mostra che nel computer è in esecuzione un solo servizio.</span><span class="sxs-lookup"><span data-stu-id="a3000-131">The output shows that there is a single service running on the computer.</span></span> <span data-ttu-id="a3000-132">Il servizio espone un endpoint che implementa il contratto `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="a3000-132">The service exposes one endpoint that implements the `ICalculator` contract.</span></span> <span data-ttu-id="a3000-133">Le impostazioni del comportamento e l'associazione implementate dall'endpoint sono elencate come la somma dei singoli elementi dello stack di messaggistica.</span><span class="sxs-lookup"><span data-stu-id="a3000-133">The settings of the behavior and binding that are implemented by the endpoint are listed as the sum of individual elements of the messaging stack.</span></span>  
  
 <span data-ttu-id="a3000-134">WMI non è limitato all'esposizione della strumentazione di gestione dell'infrastruttura WCF.</span><span class="sxs-lookup"><span data-stu-id="a3000-134">WMI is not limited to exposing the management instrumentation of the WCF infrastructure.</span></span> <span data-ttu-id="a3000-135">Mediante lo stesso meccanismo l'applicazione può esporre dati specifici del dominio.</span><span class="sxs-lookup"><span data-stu-id="a3000-135">The application can expose its own domain-specific data items through the same mechanism.</span></span> <span data-ttu-id="a3000-136">WMI è un meccanismo unificato per l'ispezione e il controllo di un servizio Web.</span><span class="sxs-lookup"><span data-stu-id="a3000-136">WMI is a unified mechanism for inspection and control of a Web service.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a3000-137">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="a3000-137">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="a3000-138">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a3000-138">Ensure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="a3000-139">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a3000-139">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="a3000-140">Pubblicare lo schema dei servizi in WMI eseguendo InstallUtil.exe (il percorso predefinito per InstallUtil.exe è "%WINDIR%\Microsoft.NET\Framework\v4.0.303197") sul file service.dll nella directory di hosting.</span><span class="sxs-lookup"><span data-stu-id="a3000-140">Publish the services schema to WMI by running the InstallUtil.exe (the default locations for InstallUtil.exe is "%WINDIR%\Microsoft.NET\Framework\v4.0.30319") on the service.dll file in the hosting directory.</span></span> <span data-ttu-id="a3000-141">È necessario eseguire questo passaggio solo quando sono state apportate modifiche al file service.dll.</span><span class="sxs-lookup"><span data-stu-id="a3000-141">This step only needs to be executed when changes have been made to the service.dll file.</span></span>
  
4. <span data-ttu-id="a3000-142">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a3000-142">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="a3000-143">Se WCF è stato installato dopo l'installazione di ASP.NET, potrebbe essere necessario eseguire "% WINDIR% \ Microsoft. Net\Framework\v3.0\Windows Communication Foundation\servicemodelreg.exe "-r-x per concedere all'account ASPNET l'autorizzazione per la pubblicazione di oggetti WMI.</span><span class="sxs-lookup"><span data-stu-id="a3000-143">If you installed WCF after installing ASP.NET, you may need to run "%WINDIR%\ Microsoft.Net\Framework\v3.0\Windows Communication Foundation\servicemodelreg.exe " -r -x to give the ASPNET account permission to publish WMI objects.</span></span>  
  
5. <span data-ttu-id="a3000-144">Visualizzare i dati dall'esempio riportato tramite WMI utilizzando i comandi: `cscript EnumerateServices.js` o `cscript EnumerateCustomObjects.js`.</span><span class="sxs-lookup"><span data-stu-id="a3000-144">View data from the sample surfaced through WMI by using the commands: `cscript EnumerateServices.js` or `cscript EnumerateCustomObjects.js`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a3000-145">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="a3000-145">The samples may already be installed on your computer.</span></span> <span data-ttu-id="a3000-146">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="a3000-146">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="a3000-147">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="a3000-147">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a3000-148">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="a3000-148">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\WMIProvider`  
  
## <a name="see-also"></a><span data-ttu-id="a3000-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3000-149">See also</span></span>

- <span data-ttu-id="a3000-150">[Monitoraggio](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="a3000-150">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
