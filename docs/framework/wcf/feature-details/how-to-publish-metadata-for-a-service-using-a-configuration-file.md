---
title: 'Procedura: pubblicare metadati per un servizio usando un file di configurazione'
description: Informazioni su come pubblicare metadati per un servizio WCF utilizzando un file di configurazione. La pubblicazione consente ai client di ottenere i metadati tramite una richiesta GET o HTTP/GET.
ms.date: 03/30/2017
ms.assetid: f061443f-92df-4824-b36a-609c4cd14a17
ms.openlocfilehash: d5d425be7f02a204476c4f6e81441aca9ea39fcc
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246818"
---
# <a name="how-to-publish-metadata-for-a-service-using-a-configuration-file"></a><span data-ttu-id="04327-104">Procedura: pubblicare metadati per un servizio usando un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="04327-104">How to: Publish Metadata for a Service Using a Configuration File</span></span>
<span data-ttu-id="04327-105">Questo è uno dei due argomenti sulle procedure che illustrano la pubblicazione di metadati per un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="04327-105">This is one of two how-to topics that demonstrate publishing metadata for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="04327-106">Esistono due modi per specificare come un servizio dovrebbe pubblicare metadati: usando un file di configurazione o il codice.</span><span class="sxs-lookup"><span data-stu-id="04327-106">There are two ways to specify how a service should publish metadata, using a configuration file and using code.</span></span> <span data-ttu-id="04327-107">In questo argomento viene illustrato come pubblicare metadati per un servizio usando un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="04327-107">This topic shows how to publish metadata for a service using a configuration file.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="04327-108">In questo argomento viene illustrato come pubblicare metadati in modo non sicuro.</span><span class="sxs-lookup"><span data-stu-id="04327-108">This topic shows how to publish metadata in an unsecure manner.</span></span> <span data-ttu-id="04327-109">Qualsiasi client può recuperare i metadati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="04327-109">Any client can retrieve the metadata from the service.</span></span> <span data-ttu-id="04327-110">Se è necessario che il servizio pubblichi metadati in modo sicuro, vedere [endpoint dei metadati protetti personalizzato](../samples/custom-secure-metadata-endpoint.md).</span><span class="sxs-lookup"><span data-stu-id="04327-110">If you require your service to publish metadata in a secure manner, see [Custom Secure Metadata Endpoint](../samples/custom-secure-metadata-endpoint.md).</span></span>  
  
 <span data-ttu-id="04327-111">Per altre informazioni sulla pubblicazione di metadati nel codice, vedere [procedura: pubblicare metadati per un servizio usando il codice](how-to-publish-metadata-for-a-service-using-code.md).</span><span class="sxs-lookup"><span data-stu-id="04327-111">For more information about publishing metadata in code, see [How to: Publish Metadata for a Service Using Code](how-to-publish-metadata-for-a-service-using-code.md).</span></span> <span data-ttu-id="04327-112">La pubblicazione di metadati consente ai client di recuperare i metadati usando una richiesta GET WS-Transfer o una richiesta HTTP/GET tramite la stringa di query `?wsdl`.</span><span class="sxs-lookup"><span data-stu-id="04327-112">Publishing metadata allows clients to retrieve the metadata using a WS-Transfer GET request or an HTTP/GET request using the `?wsdl` query string.</span></span> <span data-ttu-id="04327-113">Per assicurarsi che il codice funzioni, creare un servizio WCF di base.</span><span class="sxs-lookup"><span data-stu-id="04327-113">To be sure that the code is working, create a basic WCF service.</span></span> <span data-ttu-id="04327-114">Per motivi di semplicità, nel codice seguente viene fornito un servizio indipendente di base.</span><span class="sxs-lookup"><span data-stu-id="04327-114">For simplicity, a basic self-hosted service is provided in the following code.</span></span>  
  
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
  
 <span data-ttu-id="04327-115">Si tratta di un servizio indipendente, configurato tramite un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="04327-115">This service is a self-hosted service, which is configured using a configuration file.</span></span> <span data-ttu-id="04327-116">Il file di configurazione seguente funge da punto di partenza.</span><span class="sxs-lookup"><span data-stu-id="04327-116">The following configuration file serves as a starting point.</span></span>  
  
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
  
### <a name="to-publish-metadata-for-a-wcf-service-using-an-application-configuration-file"></a><span data-ttu-id="04327-117">Per pubblicare metadati per un servizio WCF usando un file di configurazione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="04327-117">To publish metadata for a WCF service using an application configuration file</span></span>  
  
1. <span data-ttu-id="04327-118">Nel file App.config, dopo l'elemento di chiusura `</services>`, creare un elemento `<behaviors>`.</span><span class="sxs-lookup"><span data-stu-id="04327-118">Within the App.config file, after the closing `</services>` element, create a `<behaviors>` element.</span></span>  

2. <span data-ttu-id="04327-119">All'interno dell'elemento `<behaviors>` aggiungere un elemento `<serviceBehaviors>`.</span><span class="sxs-lookup"><span data-stu-id="04327-119">Within the `<behaviors>` element, add a `<serviceBehaviors>` element.</span></span>  

3. <span data-ttu-id="04327-120">Aggiungere un elemento `<behavior>` all'elemento `<serviceBehaviors>` e specificare un valore per l'attributo `name` dell'elemento `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="04327-120">Add a `<behavior>` element to the `<serviceBehaviors>` element and specify a value for the `name` attribute of the `<behavior>` element.</span></span>  

4. <span data-ttu-id="04327-121">Aggiungere un elemento `<serviceMetadata>` all'elemento `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="04327-121">Add a `<serviceMetadata>` element to the `<behavior>` element.</span></span> <span data-ttu-id="04327-122">Impostare l'attributo `httpGetEnabled` su `true` e l'attributo `policyVersion` su Policy15.</span><span class="sxs-lookup"><span data-stu-id="04327-122">Set the `httpGetEnabled` attribute to `true` and the `policyVersion` attribute to Policy15.</span></span> <span data-ttu-id="04327-123">`httpGetEnabled` consente al servizio di rispondere a richieste di metadati eseguite da una richiesta HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="04327-123">`httpGetEnabled` allows the service to respond to metadata requests made by an HTTP GET request.</span></span> <span data-ttu-id="04327-124">`policyVersion` indica al servizio di conformarsi a WS-Policy 1.5 per la generazione di metadati.</span><span class="sxs-lookup"><span data-stu-id="04327-124">`policyVersion` tells the service to conform to WS-Policy 1.5 when generating metadata.</span></span>  

5. <span data-ttu-id="04327-125">Aggiungere un attributo `behaviorConfiguration` all'elemento `<service>` e specificare l'attributo `name` dell'elemento `<behavior>` aggiunto al passaggio 1, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="04327-125">Add a `behaviorConfiguration` attribute to the `<service>` element and specify the `name` attribute of the `<behavior>` element added in step 1, as shown in the following code example.</span></span>  
  
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
  
6. <span data-ttu-id="04327-126">Aggiungere uno o più elementi `<endpoint>` con il contratto impostato su `IMetadataExchange`, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="04327-126">Add one or more `<endpoint>` elements with the contract set to `IMetadataExchange`, as shown in the following code example.</span></span>  
  
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
  
7. <span data-ttu-id="04327-127">Per gli endpoint dei metadati aggiunti nel passaggio precedente, impostare l'attributo `binding` su uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="04327-127">For the metadata endpoints added in the previous step, set the `binding` attribute to one of the following:</span></span>  
  
    - <span data-ttu-id="04327-128">`mexHttpBinding` per la pubblicazione HTTP.</span><span class="sxs-lookup"><span data-stu-id="04327-128">`mexHttpBinding` for HTTP publication.</span></span>  
  
    - <span data-ttu-id="04327-129">`mexHttpsBinding` per la pubblicazione HTTPS.</span><span class="sxs-lookup"><span data-stu-id="04327-129">`mexHttpsBinding` for HTTPS publication.</span></span>  
  
    - <span data-ttu-id="04327-130">`mexNamedPipeBinding` per la pubblicazione named pipe.</span><span class="sxs-lookup"><span data-stu-id="04327-130">`mexNamedPipeBinding` for named pipe publication.</span></span>  
  
    - <span data-ttu-id="04327-131">`mexTcpBinding` per la pubblicazione TCP.</span><span class="sxs-lookup"><span data-stu-id="04327-131">`mexTcpBinding` for TCP publication.</span></span>  
  
8. <span data-ttu-id="04327-132">Per gli endpoint dei metadati aggiunti in un passaggio precedente, impostare l'indirizzo su:</span><span class="sxs-lookup"><span data-stu-id="04327-132">For the metadata endpoints added in a previous step, set the address equal to:</span></span>  
  
    - <span data-ttu-id="04327-133">Una stringa vuota, per usare l'indirizzo di base dell'applicazione host come punto di pubblicazione, se l'indirizzo di base corrisponde all'associazione di metadati.</span><span class="sxs-lookup"><span data-stu-id="04327-133">An empty string to use the host application's base address as the publication point if the base address is the same as the metadata binding.</span></span>  
  
    - <span data-ttu-id="04327-134">Un indirizzo relativo, se l'applicazione host ha un indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="04327-134">A relative address if the host application has a base address.</span></span>  
  
    - <span data-ttu-id="04327-135">Un indirizzo assoluto.</span><span class="sxs-lookup"><span data-stu-id="04327-135">An absolute address.</span></span>  
  
9. <span data-ttu-id="04327-136">Compilare ed eseguire l'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="04327-136">Build and run the console application.</span></span>  
  
10. <span data-ttu-id="04327-137">Utilizzare Internet Explorer per passare all'indirizzo di base del servizio ( `http://localhost:8001/MetadataSample` in questo esempio) e verificare che la pubblicazione dei metadati sia attivata.</span><span class="sxs-lookup"><span data-stu-id="04327-137">Use Internet Explorer to browse to the base address of the service (`http://localhost:8001/MetadataSample` in this sample) and verify that the metadata publishing is turned on.</span></span> <span data-ttu-id="04327-138">Se così non fosse, all'inizio della pagina risultante verrà visualizzato il messaggio: "La pubblicazione dei metadati per il servizio è attualmente disabilitata".</span><span class="sxs-lookup"><span data-stu-id="04327-138">If not, a message at the top of the resulting page displays: "Metadata publishing for this service is currently disabled."</span></span>  
  
### <a name="to-use-default-endpoints"></a><span data-ttu-id="04327-139">Per usare endpoint predefiniti</span><span class="sxs-lookup"><span data-stu-id="04327-139">To use default endpoints</span></span>  
  
1. <span data-ttu-id="04327-140">Per configurare metadati in un servizio che usa endpoint predefiniti, specificare <xref:System.ServiceModel.Description.ServiceMetadataBehavior> nel file di configurazione come nell'esempio precedente, senza però specificare alcun endpoint.</span><span class="sxs-lookup"><span data-stu-id="04327-140">To configure metadata on a service that uses default endpoints, specify the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> in the configuration file as in the previous example, but do not specify any endpoints.</span></span> <span data-ttu-id="04327-141">Il file di configurazione sarà quindi simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="04327-141">The configuration file would then look like this.</span></span>  
  
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
  
     <span data-ttu-id="04327-142">Poiché il servizio ha <xref:System.ServiceModel.Description.ServiceMetadataBehavior> con `httpGetEnabled` impostato su `true`, per il servizio è abilitata la pubblicazione di metadati. Poiché, inoltre, non è stato aggiunto in modo esplicito alcun endpoint, il runtime aggiunge gli endpoint predefiniti.</span><span class="sxs-lookup"><span data-stu-id="04327-142">Because the service has a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> with the `httpGetEnabled` set to `true`, the service has publishing metadata enabled, and because no endpoints were explicitly added, the runtime adds the default endpoints.</span></span> <span data-ttu-id="04327-143">Per altre informazioni su endpoint, associazioni e comportamenti predefiniti, vedere [Simplified Configuration](../simplified-configuration.md) (Configurazione semplificata) e [Simplified Configuration for WCF Services](../samples/simplified-configuration-for-wcf-services.md) (Configurazione semplificata per servizi WCF).</span><span class="sxs-lookup"><span data-stu-id="04327-143">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../simplified-configuration.md) and [Simplified Configuration for WCF Services](../samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="04327-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="04327-144">Example</span></span>  
 <span data-ttu-id="04327-145">Nell'esempio di codice seguente viene illustrata l'implementazione di un servizio WCF di base e il file di configurazione che pubblica i metadati per il servizio.</span><span class="sxs-lookup"><span data-stu-id="04327-145">The following code example shows the implementation of a basic WCF service and the configuration file that publishes metadata for the service.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="04327-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04327-146">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
- [<span data-ttu-id="04327-147">Procedura: ospitare un servizio WCF in un'applicazione gestita</span><span class="sxs-lookup"><span data-stu-id="04327-147">How to: Host a WCF Service in a Managed Application</span></span>](../how-to-host-a-wcf-service-in-a-managed-application.md)
- [<span data-ttu-id="04327-148">Servizio indipendente</span><span class="sxs-lookup"><span data-stu-id="04327-148">Self-Host</span></span>](../samples/self-host.md)
- [<span data-ttu-id="04327-149">Panoramica dell'architettura dei metadati</span><span class="sxs-lookup"><span data-stu-id="04327-149">Metadata Architecture Overview</span></span>](metadata-architecture-overview.md)
- [<span data-ttu-id="04327-150">Uso di metadati</span><span class="sxs-lookup"><span data-stu-id="04327-150">Using Metadata</span></span>](using-metadata.md)
- [<span data-ttu-id="04327-151">Procedura: pubblicare metadati per un servizio usando codice</span><span class="sxs-lookup"><span data-stu-id="04327-151">How to: Publish Metadata for a Service Using Code</span></span>](how-to-publish-metadata-for-a-service-using-code.md)
