---
title: 'Procedura: pubblicare metadati per un servizio usando un file di configurazione'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f061443f-92df-4824-b36a-609c4cd14a17
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d30031db590b424688cc0af6a573c1042099e64e
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-publish-metadata-for-a-service-using-a-configuration-file"></a><span data-ttu-id="f4c0f-102">Procedura: pubblicare metadati per un servizio usando un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="f4c0f-102">How to: Publish Metadata for a Service Using a Configuration File</span></span>
<span data-ttu-id="f4c0f-103">Questo è uno di due argomenti in cui viene illustrato come pubblicare metadati per un servizio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4c0f-103">This is one of two how-to topics that demonstrate publishing metadata for a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service.</span></span> <span data-ttu-id="f4c0f-104">Esistono due modi per specificare come un servizio dovrebbe pubblicare metadati: usando un file di configurazione o il codice.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-104">There are two ways to specify how a service should publish metadata, using a configuration file and using code.</span></span> <span data-ttu-id="f4c0f-105">In questo argomento viene illustrato come pubblicare metadati per un servizio usando un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-105">This topic shows how to publish metadata for a service using a configuration file.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="f4c0f-106">In questo argomento viene illustrato come pubblicare metadati in modo non sicuro.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-106">This topic shows how to publish metadata in an unsecure manner.</span></span> <span data-ttu-id="f4c0f-107">Qualsiasi client può recuperare i metadati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-107">Any client can retrieve the metadata from the service.</span></span> <span data-ttu-id="f4c0f-108">Se è necessario che il servizio per pubblicare metadati in modo sicuro, vedere [Endpoint di metadati protetto personalizzato](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).</span><span class="sxs-lookup"><span data-stu-id="f4c0f-108">If you require your service to publish metadata in a secure manner, see [Custom Secure Metadata Endpoint](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
 <span data-ttu-id="f4c0f-109">Per ulteriori informazioni sulla pubblicazione di metadati nel codice, vedere [procedura: pubblicare metadati per un servizio utilizzando codice](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md).</span><span class="sxs-lookup"><span data-stu-id="f4c0f-109">For more information about publishing metadata in code, see [How to: Publish Metadata for a Service Using Code](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md).</span></span> <span data-ttu-id="f4c0f-110">La pubblicazione di metadati consente ai client di recuperare i metadati usando una richiesta GET WS-Transfer o una richiesta HTTP/GET tramite la stringa di query `?wsdl`.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-110">Publishing metadata allows clients to retrieve the metadata using a WS-Transfer GET request or an HTTP/GET request using the `?wsdl` query string.</span></span> <span data-ttu-id="f4c0f-111">Per garantire il corretto funzionamento del codice, creare un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] di base.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-111">To be sure that the code is working, create a basic [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="f4c0f-112">Per motivi di semplicità, nel codice seguente viene fornito un servizio indipendente di base.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-112">For simplicity, a basic self-hosted service is provided in the following code.</span></span>  
  
```csharp  
using System;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
  
namespace Metadata.Samples  
{  
    [ServiceContract]  
    public interface ISimpleService  
    {  
        [OperationContract]  
        string SimpleMethod(string msg);  
    }  
  
    class SimpleService : ISimpleService  
    {  
        public string SimpleMethod(string msg)  
        {  
            Console.WriteLine("The caller passed in " + msg);  
            return "Hello " + msg;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost host = new ServiceHost(typeof(SimpleService),  
                new Uri("http://localhost:8001/MetadataSample"));   
            try  
            {  
                // Open the service host to accept incoming calls  
                host.Open();  
  
                // The service can now be accessed.  
                Console.WriteLine("The service is ready.");  
                Console.WriteLine("Press <ENTER> to terminate service.");  
                Console.WriteLine();  
                Console.ReadLine();  
  
                // Close the ServiceHostBase to shutdown the service.  
                host.Close();  
            }  
            catch (CommunicationException commProblem)  
            {  
                Console.WriteLine("There was a communication problem. " + commProblem.Message);  
                Console.Read();  
            }  
        }  
    }  
}  
```  
  
 <span data-ttu-id="f4c0f-113">Si tratta di un servizio indipendente, configurato tramite un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-113">This service is a self-hosted service, which is configured using a configuration file.</span></span> <span data-ttu-id="f4c0f-114">Il file di configurazione seguente funge da punto di partenza.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-114">The following configuration file serves as a starting point.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Metadata.Example.SimpleService">  
        <endpoint address=""  
                  binding="basicHttpBinding"  
                  contract="Metadata.Example.ISimpleService" />  
      </service>  
    </services>  
    <behaviors>  
  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="to-publish-metadata-for-a-wcf-service-using-an-application-configuration-file"></a><span data-ttu-id="f4c0f-115">Per pubblicare metadati per un servizio WCF usando un file di configurazione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="f4c0f-115">To publish metadata for a WCF service using an application configuration file</span></span>  
  
1.  <span data-ttu-id="f4c0f-116">Nel file App.config, dopo l'elemento di chiusura `</services>`, creare un elemento `<behaviors>`.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-116">Within the App.config file, after the closing `</services>` element, create a `<behaviors>` element.</span></span>  
  
  
  
2.  <span data-ttu-id="f4c0f-117">Nell'elemento `<behaviors>` aggiungere un elemento `<serviceBehaviors>`.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-117">Within the `<behaviors>` element, add a `<serviceBehaviors>` element.</span></span>  
  
  
  
3.  <span data-ttu-id="f4c0f-118">Aggiungere un elemento `<behavior>` all'elemento `<serviceBehaviors>` e specificare un valore per l'attributo `name` dell'elemento `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-118">Add a `<behavior>` element to the `<serviceBehaviors>` element and specify a value for the `name` attribute of the `<behavior>` element.</span></span>  
  
  
  
4.  <span data-ttu-id="f4c0f-119">Aggiungere un elemento `<serviceMetadata>` all'elemento `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-119">Add a `<serviceMetadata>` element to the `<behavior>` element.</span></span> <span data-ttu-id="f4c0f-120">Impostare l'attributo `httpGetEnabled` su `true` e l'attributo `policyVersion` su Policy15.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-120">Set the `httpGetEnabled` attribute to `true` and the `policyVersion` attribute to Policy15.</span></span> <span data-ttu-id="f4c0f-121">`httpGetEnabled` consente al servizio di rispondere a richieste di metadati eseguite da una richiesta HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-121">`httpGetEnabled` allows the service to respond to metadata requests made by an HTTP GET request.</span></span> <span data-ttu-id="f4c0f-122">`policyVersion` indica al servizio di conformarsi a WS-Policy 1.5 per la generazione di metadati.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-122">`policyVersion` tells the service to conform to WS-Policy 1.5 when generating metadata.</span></span>  
  
  
  
5.  <span data-ttu-id="f4c0f-123">Aggiungere un attributo `behaviorConfiguration` all'elemento `<service>` e specificare l'attributo `name` dell'elemento `<behavior>` aggiunto al passaggio 1, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-123">Add a `behaviorConfiguration` attribute to the `<service>` element and specify the `name` attribute of the `<behavior>` element added in step 1, as shown in the following code example.</span></span>  
  
    ```xml  
    <services>  
      <service  
          name="Metadata.Example.SimpleService"  
          behaviorConfiguration="SimpleServiceBehavior">  
        ...  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="SimpleServiceBehavior">  
          <serviceMetadata httpGetEnabled="True" policyVersion="Policy15" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
6.  <span data-ttu-id="f4c0f-124">Aggiungere uno o più elementi `<endpoint>` con il contratto impostato su `IMetadataExchange`, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-124">Add one or more `<endpoint>` elements with the contract set to `IMetadataExchange`, as shown in the following code example.</span></span>  
  
    ```xml  
    <services>  
      <service  
          name="Metadata.Example.SimpleService"  
          behaviorConfiguration="SimpleServiceBehavior">  
  
        <endpoint address=""  
                  binding="wsHttpBinding"  
                  contract="Metadata.Example.ISimpleService" />  
  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
    ```  
  
7.  <span data-ttu-id="f4c0f-125">Per gli endpoint dei metadati aggiunti nel passaggio precedente, impostare l'attributo `binding` su uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4c0f-125">For the metadata endpoints added in the previous step, set the `binding` attribute to one of the following:</span></span>  
  
    -   <span data-ttu-id="f4c0f-126">`mexHttpBinding` per la pubblicazione HTTP.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-126">`mexHttpBinding` for HTTP publication.</span></span>  
  
    -   <span data-ttu-id="f4c0f-127">`mexHttpsBinding` per la pubblicazione HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-127">`mexHttpsBinding` for HTTPS publication.</span></span>  
  
    -   <span data-ttu-id="f4c0f-128">`mexNamedPipeBinding` per la pubblicazione named pipe.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-128">`mexNamedPipeBinding` for named pipe publication.</span></span>  
  
    -   <span data-ttu-id="f4c0f-129">`mexTcpBinding` per la pubblicazione TCP.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-129">`mexTcpBinding` for TCP publication.</span></span>  
  
8.  <span data-ttu-id="f4c0f-130">Per gli endpoint dei metadati aggiunti in un passaggio precedente, impostare l'indirizzo su:</span><span class="sxs-lookup"><span data-stu-id="f4c0f-130">For the metadata endpoints added in a previous step, set the address equal to:</span></span>  
  
    -   <span data-ttu-id="f4c0f-131">Una stringa vuota, per usare l'indirizzo di base dell'applicazione host come punto di pubblicazione, se l'indirizzo di base corrisponde all'associazione di metadati.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-131">An empty string to use the host application's base address as the publication point if the base address is the same as the metadata binding.</span></span>  
  
    -   <span data-ttu-id="f4c0f-132">Un indirizzo relativo, se l'applicazione host ha un indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-132">A relative address if the host application has a base address.</span></span>  
  
    -   <span data-ttu-id="f4c0f-133">Un indirizzo assoluto.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-133">An absolute address.</span></span>  
  
9. <span data-ttu-id="f4c0f-134">Compilare ed eseguire l'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-134">Build and run the console application.</span></span>  
  
10. <span data-ttu-id="f4c0f-135">Usare Internet Explorer per accedere all'indirizzo di base del servizio (http://localhost:8001/MetadataSample in questo esempio) e verificare che la pubblicazione dei metadati è attivata.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-135">Use Internet Explorer to browse to the base address of the service (http://localhost:8001/MetadataSample in this sample) and verify that the metadata publishing is turned on.</span></span> <span data-ttu-id="f4c0f-136">Se così non fosse, all'inizio della pagina risultante verrà visualizzato il messaggio: "La pubblicazione dei metadati per il servizio è attualmente disabilitata".</span><span class="sxs-lookup"><span data-stu-id="f4c0f-136">If not, a message at the top of the resulting page displays: "Metadata publishing for this service is currently disabled."</span></span>  
  
### <a name="to-use-default-endpoints"></a><span data-ttu-id="f4c0f-137">Per usare endpoint predefiniti</span><span class="sxs-lookup"><span data-stu-id="f4c0f-137">To use default endpoints</span></span>  
  
1.  <span data-ttu-id="f4c0f-138">Per configurare metadati in un servizio che usa endpoint predefiniti, specificare <xref:System.ServiceModel.Description.ServiceMetadataBehavior> nel file di configurazione come nell'esempio precedente, senza però specificare alcun endpoint.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-138">To configure metadata on a service that uses default endpoints, specify the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> in the configuration file as in the previous example, but do not specify any endpoints.</span></span> <span data-ttu-id="f4c0f-139">Il file di configurazione sarà quindi simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-139">The configuration file would then look like this.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <behaviors>  
          <serviceBehaviors>  
            <behavior name="SimpleServiceBehavior">  
              <serviceMetadata httpGetEnabled="True" policyVersion="Policy12" />  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="f4c0f-140">Poiché il servizio ha <xref:System.ServiceModel.Description.ServiceMetadataBehavior> con `httpGetEnabled` impostato su `true`, per il servizio è abilitata la pubblicazione di metadati. Poiché, inoltre, non è stato aggiunto in modo esplicito alcun endpoint, il runtime aggiunge gli endpoint predefiniti.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-140">Because the service has a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> with the `httpGetEnabled` set to `true`, the service has publishing metadata enabled, and because no endpoints were explicitly added, the runtime adds the default endpoints.</span></span> <span data-ttu-id="f4c0f-141">Per ulteriori informazioni sull'endpoint predefiniti, associazioni e comportamenti, vedere [configurazione semplificata](../../../../docs/framework/wcf/simplified-configuration.md) e [configurazione semplificata per i servizi WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="f4c0f-141">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4c0f-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="f4c0f-142">Example</span></span>  
 <span data-ttu-id="f4c0f-143">Nell'esempio di codice seguente vengono illustrati l'implementazione di un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] di base e il file di configurazione che pubblica i metadati per il servizio.</span><span class="sxs-lookup"><span data-stu-id="f4c0f-143">The following code example shows the implementation of a basic [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service and the configuration file that publishes metadata for the service.</span></span>  
  
```csharp  
using System;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
  
namespace Metadata.Samples  
{  
    [ServiceContract]  
    public interface ISimpleService  
    {  
        [OperationContract]  
        string SimpleMethod(string msg);  
    }  
  
    class SimpleService : ISimpleService  
    {  
        public string SimpleMethod(string msg)  
        {  
            Console.WriteLine("The caller passed in " + msg);  
            return "Hello " + msg;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost host = new ServiceHost(typeof(SimpleService),  
                new Uri("http://localhost:8001/MetadataSample"));   
            try  
            {  
                // Open the service host to accept incoming calls  
                host.Open();  
  
                // The service can now be accessed.  
                Console.WriteLine("The service is ready.");  
                Console.WriteLine("Press <ENTER> to terminate service.");  
                Console.WriteLine();  
                Console.ReadLine();  
  
                // Close the ServiceHostBase to shutdown the service.  
                host.Close();  
            }  
            catch (CommunicationException commProblem)  
            {  
                Console.WriteLine("There was a communication problem. " + commProblem.Message);  
                Console.Read();  
            }  
        }  
    }  
}  
```  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="SimpleServiceBehavior">  
          <serviceMetadata httpGetEnabled="True" policyVersion="Policy12" />  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f4c0f-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4c0f-144">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>  
 [<span data-ttu-id="f4c0f-145">Procedura: Ospitare un servizio WCF in un'applicazione gestita</span><span class="sxs-lookup"><span data-stu-id="f4c0f-145">How to: Host a WCF Service in a Managed Application</span></span>](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)  
 [<span data-ttu-id="f4c0f-146">Servizio indipendente</span><span class="sxs-lookup"><span data-stu-id="f4c0f-146">Self-Host</span></span>](../../../../docs/framework/wcf/samples/self-host.md)  
 [<span data-ttu-id="f4c0f-147">Panoramica dell'architettura dei metadati</span><span class="sxs-lookup"><span data-stu-id="f4c0f-147">Metadata Architecture Overview</span></span>](../../../../docs/framework/wcf/feature-details/metadata-architecture-overview.md)  
 [<span data-ttu-id="f4c0f-148">Uso di metadati</span><span class="sxs-lookup"><span data-stu-id="f4c0f-148">Using Metadata</span></span>](../../../../docs/framework/wcf/feature-details/using-metadata.md)  
 [<span data-ttu-id="f4c0f-149">Procedura: Pubblicare metadati per un servizio usando il codice</span><span class="sxs-lookup"><span data-stu-id="f4c0f-149">How to: Publish Metadata for a Service Using Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)
