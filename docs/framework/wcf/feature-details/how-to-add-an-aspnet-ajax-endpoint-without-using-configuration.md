---
title: 'Procedura: aggiungere un endpoint ASP.NET AJAX senza usare la configurazione'
ms.date: 03/30/2017
ms.assetid: b05c1742-8d0a-4673-9d71-725b18a3008e
ms.openlocfilehash: 9935e2a7738796fff9a037b09237a6acbf7bf988
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185127"
---
# <a name="how-to-add-an-aspnet-ajax-endpoint-without-using-configuration"></a><span data-ttu-id="88cf4-102">Procedura: aggiungere un endpoint ASP.NET AJAX senza usare la configurazione</span><span class="sxs-lookup"><span data-stu-id="88cf4-102">How to: Add an ASP.NET AJAX Endpoint Without Using Configuration</span></span>
<span data-ttu-id="88cf4-103">Windows Communication Foundation (WCF) consente di creare un servizio che espone un ASP.NET endpoint con supporto AJAX che può essere chiamato da JavaScript in un sito Web client.</span><span class="sxs-lookup"><span data-stu-id="88cf4-103">Windows Communication Foundation (WCF) allows you to create a service that exposes an ASP.NET AJAX-enabled endpoint that can be called from JavaScript on a client Web site.</span></span> <span data-ttu-id="88cf4-104">Per creare tale endpoint è possibile utilizzare un file di configurazione, come con tutti gli altri endpoint WCF, o un metodo che non richiede elementi di configurazione.</span><span class="sxs-lookup"><span data-stu-id="88cf4-104">To create such an endpoint, you can either use a configuration file, as with all other WCF endpoints, or use a method that does not require any configuration elements.</span></span> <span data-ttu-id="88cf4-105">In questo argomento viene illustrato il secondo approccio.</span><span class="sxs-lookup"><span data-stu-id="88cf4-105">This topic demonstrates the second approach.</span></span>  
  
 <span data-ttu-id="88cf4-106">Per creare servizi con endpoint ASP.NET AJAX senza configurazione, i servizi devono essere ospitati da Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="88cf4-106">To create services with ASP.NET AJAX endpoints without configuration, the services must be hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="88cf4-107">Per attivare un endpoint AJAX ASP.NET <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> utilizzando questo approccio, specificare il parametro come Factory nella direttiva [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) nel file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="88cf4-107">To activate an ASP.NET AJAX endpoint using this approach, specify the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> as the Factory parameter in the [\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive in the .svc file.</span></span> <span data-ttu-id="88cf4-108">Questa factory personalizzata è il componente che configura automaticamente un endpoint ASP.NET AJAX, in modo che possa essere chiamato da JavaScript su un sito Web client.</span><span class="sxs-lookup"><span data-stu-id="88cf4-108">This custom factory is the component that automatically configures an ASP.NET AJAX endpoint so that it can be called from JavaScript on a client Web site.</span></span>  
  
 <span data-ttu-id="88cf4-109">Per un esempio funzionante, vedere il [servizio AJAX senza configurazione](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="88cf4-109">For a working example, see the [AJAX Service Without Configuration](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).</span></span>  
  
 <span data-ttu-id="88cf4-110">Per una descrizione su come configurare un ASP.NET endpoint AJAX utilizzando gli elementi di configurazione, vedere [Procedura: utilizzare](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)la configurazione per aggiungere un ASP.NET endpoint AJAX .</span><span class="sxs-lookup"><span data-stu-id="88cf4-110">For an outline of how to configure an ASP.NET AJAX endpoint using configuration elements, see [How to: Use Configuration to Add an ASP.NET AJAX Endpoint](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).</span></span>  
  
### <a name="to-create-a-basic-wcf-service"></a><span data-ttu-id="88cf4-111">Per creare un servizio WFC di base</span><span class="sxs-lookup"><span data-stu-id="88cf4-111">To create a basic WCF service</span></span>  
  
1. <span data-ttu-id="88cf4-112">Definire un contratto di servizio WCF <xref:System.ServiceModel.ServiceContractAttribute> di base con un'interfaccia contrassegnata con l'attributo .</span><span class="sxs-lookup"><span data-stu-id="88cf4-112">Define a basic WCF service contract with an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="88cf4-113">Contrassegnare ogni operazione con <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="88cf4-113">Mark each operation with the <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="88cf4-114">Assicurarsi di impostare la proprietà <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="88cf4-114">Be sure to set the <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> property.</span></span>  
  
    ```csharp  
    [ServiceContract(Namespace = "MyService")]]  
    public interface ICalculator  
    {  
        [OperationContract]  
        // This operation returns the sum of d1 and d2.  
        double Add(double n1, double n2);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2. <span data-ttu-id="88cf4-115">Implementare il contratto di servizio `ICalculator` con `CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="88cf4-115">Implement the `ICalculator` service contract with a `CalculatorService`.</span></span>  
  
    ```csharp  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
  
    //Other operations omitted…  
    ```  
  
3. <span data-ttu-id="88cf4-116">Definire uno spazio dei nomi per le implementazioni `ICalculator` e `CalculatorService` eseguendo il wrapping di queste ultime in un blocco dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="88cf4-116">Define a namespace for the `ICalculator` and `CalculatorService` implementations by wrapping them in a namespace block.</span></span>  
  
    ```csharp  
    Namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
### <a name="to-host-the-service-in-internet-information-services-without-configuration"></a><span data-ttu-id="88cf4-117">Per ospitare il servizio in Internet Information Services senza configurazione</span><span class="sxs-lookup"><span data-stu-id="88cf4-117">To host the service in Internet Information Services without configuration</span></span>  
  
1. <span data-ttu-id="88cf4-118">Creare un nuovo file denominato "file del servizio" con estensione svc nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="88cf4-118">Create a new file named service with a .svc extension in the application.</span></span> <span data-ttu-id="88cf4-119">Modificare questo file aggiungendo [ \@](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) le informazioni appropriate della direttiva ServiceHost per il servizio.</span><span class="sxs-lookup"><span data-stu-id="88cf4-119">Edit this file by adding the appropriate [\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive information for the service.</span></span> <span data-ttu-id="88cf4-120">Specificare <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> che l'oggetto deve essere utilizzato nella direttiva [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) per configurare automaticamente un endpoint AJAX ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="88cf4-120">Specify that the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is to be used in the [\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive to automatically configure an ASP.NET AJAX endpoint.</span></span>  
  
    ```text
    <%@ServiceHost
        language=c#
        Debug="true"
        Service="Microsoft.Ajax.Samples.CalculatorService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
2. <span data-ttu-id="88cf4-121">Generare il servizio e chiamarlo dal client.</span><span class="sxs-lookup"><span data-stu-id="88cf4-121">Build the service and call it from the client.</span></span> <span data-ttu-id="88cf4-122">Internet Information Services (IIS) attiva il servizio quando viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="88cf4-122">Internet Information Services (IIS) activates the service when called.</span></span> <span data-ttu-id="88cf4-123">Per ulteriori informazioni sull'hosting in IIS, vedere [procedura: ospitare un servizio WCF in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).</span><span class="sxs-lookup"><span data-stu-id="88cf4-123">For more information about hosting in IIS, see [How to: Host a WCF Service in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).</span></span>  
  
### <a name="to-call-the-service"></a><span data-ttu-id="88cf4-124">Per chiamare il servizio</span><span class="sxs-lookup"><span data-stu-id="88cf4-124">To call the service</span></span>  
  
1. <span data-ttu-id="88cf4-125">L'endpoint è configurato in un indirizzo vuoto relativo al file con estensione svc, pertanto il\<servizio è ora disponibile e può `Add` essere richiamato inviando richieste all'operazione service.svc/>, ad esempio service.svc/Add per l'operazione.</span><span class="sxs-lookup"><span data-stu-id="88cf4-125">The endpoint is configured at an empty address relative to the .svc file, so the service is now available and can be invoked by sending requests to service.svc/\<operation> - for example, service.svc/Add for the `Add` operation.</span></span> <span data-ttu-id="88cf4-126">È possibile utilizzarlo immettendo l'URL del servizio nella raccolta degli script del controllo Script Manager ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="88cf4-126">You can use it by entering the service URL into the Scripts collection of the ASP.NET AJAX Script Manager control.</span></span> <span data-ttu-id="88cf4-127">Per un esempio, vedere il [servizio AJAX senza configurazione](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="88cf4-127">For an example, see the [AJAX Service Without Configuration](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="88cf4-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="88cf4-128">Example</span></span>  
  
 <span data-ttu-id="88cf4-129">L'endpoint configurato automaticamente viene creato in un indirizzo vuoto relativo all'URL di base.</span><span class="sxs-lookup"><span data-stu-id="88cf4-129">The automatically-configured endpoint is created at an empty address relative to the base URL.</span></span> <span data-ttu-id="88cf4-130">Può essere aggiunto e utilizzato con questo approccio anche un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="88cf4-130">A configuration file can also be added and used with this approach.</span></span> <span data-ttu-id="88cf4-131">Se il file di configurazione contiene definizioni di endpoint, questi endpoint vengono aggiunti all'endpoint configurato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="88cf4-131">If the configuration file contains endpoint definitions, these endpoints are added to the automatically-configured endpoint.</span></span>  
  
 <span data-ttu-id="88cf4-132">Ad esempio, service.svc utilizza <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> e la directory del servizio contiene un file Web.config che definisce un endpoint per lo stesso servizio utilizzando <xref:System.ServiceModel.BasicHttpBinding> nell'indirizzo relativo "soap".</span><span class="sxs-lookup"><span data-stu-id="88cf4-132">For example, service.svc uses the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> and the service directory contains a Web.config file that defines an endpoint for the same service using the <xref:System.ServiceModel.BasicHttpBinding> at the "soap" relative address.</span></span> <span data-ttu-id="88cf4-133">In questo caso, il servizio contiene due endpoint: uno in service.svc, che risponde alle richieste ASP.NET AJAX, e un altro in service.svc/soap, che risponde alle richieste SOAP.</span><span class="sxs-lookup"><span data-stu-id="88cf4-133">In this case, the service contains two endpoints: one at service.svc (which responds to ASP.NET AJAX requests) and another at service.svc/soap (which responds to SOAP requests).</span></span>  
  
 <span data-ttu-id="88cf4-134">Se il file di configurazione definisce un endpoint in un indirizzo relativo vuoto e viene utilizzata la classe <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, viene generata un'eccezione e il servizio non viene avviato.</span><span class="sxs-lookup"><span data-stu-id="88cf4-134">If the configuration file defines an endpoint at an empty relative address and the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is used, an exception is thrown and the service fails to start.</span></span>  
  
 <span data-ttu-id="88cf4-135">Non è possibile utilizzare la configurazione per modificare impostazioni sull'endpoint configurato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="88cf4-135">You cannot use configuration to modify settings on the automatically-configured endpoint.</span></span> <span data-ttu-id="88cf4-136">Se è necessario modificare un'impostazione, quale la quota del lettore, non si deve utilizzare l'approccio senza configurazione rimuovendo <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> dal file con estensione svc e creando una voce di configurazione per l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="88cf4-136">If any setting (such as a reader quota) must be modified, you must not use the configuration-free approach by removing the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> from the .svc file and creating a configuration entry for the endpoint.</span></span>  
  
 <span data-ttu-id="88cf4-137">Se il servizio richiede la modalità di compatibilità ASP.NET, se ad esempio utilizza la classe <xref:System.Web.HttpContext> o meccanismi di autorizzazione ASP.NET, è comunque necessario un file di configurazione per attivare questa modalità.</span><span class="sxs-lookup"><span data-stu-id="88cf4-137">If your service requires ASP.NET Compatibility Mode - for example, if it uses the <xref:System.Web.HttpContext> class or ASP.NET authorization mechanisms - a configuration file is still required to turn on this mode.</span></span> <span data-ttu-id="88cf4-138">L'elemento di configurazione richiesto è l'elemento [ \<serviceHostingEnvironment>,](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) che deve essere aggiunto come segue.</span><span class="sxs-lookup"><span data-stu-id="88cf4-138">The configuration element required is the [\<serviceHostingEnvironment>](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) element, which must be added as follows.</span></span>  
  
 `<system.serviceModel>`  
  
 `<serviceHostingEnvironment aspNetCompatibilityEnabled="true" /> </system.serviceModel>`  
  
 <span data-ttu-id="88cf4-139">Per altre informazioni, vedere il [servizio WCF e ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="88cf4-139">For more information, see the [WCF Services and ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) topic.</span></span>  
  
 <span data-ttu-id="88cf4-140">La classe <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> è una classe derivata di <xref:System.ServiceModel.Activation.ServiceHostFactory>.</span><span class="sxs-lookup"><span data-stu-id="88cf4-140">The <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> class is a derived class of <xref:System.ServiceModel.Activation.ServiceHostFactory>.</span></span> <span data-ttu-id="88cf4-141">Per una spiegazione dettagliata del meccanismo di factory dell'host del servizio, vedere l'argomento Estensione dell'hosting tramite ServiceHostFactory.For a detailed explanation of the service host factory mechanism, see [the Extending Hosting Using ServiceHostFactory](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md) topic.</span><span class="sxs-lookup"><span data-stu-id="88cf4-141">For a detailed explanation of the service host factory mechanism, see the [Extending Hosting Using ServiceHostFactory](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md) topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88cf4-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88cf4-142">See also</span></span>

- [<span data-ttu-id="88cf4-143">Creazione di servizi WCF per ASP.NET AJAX</span><span class="sxs-lookup"><span data-stu-id="88cf4-143">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [<span data-ttu-id="88cf4-144">Procedura: eseguire la migrazione di servizi Web ASP.NET compatibili AJAX a WCF</span><span class="sxs-lookup"><span data-stu-id="88cf4-144">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
