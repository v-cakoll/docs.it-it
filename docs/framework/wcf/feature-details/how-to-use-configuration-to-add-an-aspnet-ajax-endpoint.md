---
title: 'Procedura: Usare la configurazione per aggiungere un endpoint ASP.NET AJAX'
ms.date: 03/30/2017
ms.assetid: 7cd0099e-dc3a-47e4-a38c-6e10f997f6ea
ms.openlocfilehash: 26a7b0d3fef67cf9dae0913e22e3cd7ec443c111
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202976"
---
# <a name="how-to-use-configuration-to-add-an-aspnet-ajax-endpoint"></a><span data-ttu-id="b2e94-102">Procedura: Usare la configurazione per aggiungere un endpoint ASP.NET AJAX</span><span class="sxs-lookup"><span data-stu-id="b2e94-102">How to: Use Configuration to Add an ASP.NET AJAX Endpoint</span></span>
<span data-ttu-id="b2e94-103">Windows Communication Foundation (WCF) consente di creare un servizio che rende un endpoint ASP.NET compatibile con AJAX disponibile che può essere chiamato da JavaScript su un sito Web client.</span><span class="sxs-lookup"><span data-stu-id="b2e94-103">Windows Communication Foundation (WCF) allows you to create a service that makes an ASP.NET AJAX-enabled endpoint available that can be called from JavaScript on a client Web site.</span></span> <span data-ttu-id="b2e94-104">Per creare tale endpoint, è possibile usare un file di configurazione, come con tutti gli altri endpoint Windows Communication Foundation (WCF) o usare un metodo che non richiede elementi di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b2e94-104">To create such an endpoint, you can either use a configuration file, as with all other Windows Communication Foundation (WCF) endpoints, or use a method that does not require any configuration elements.</span></span> <span data-ttu-id="b2e94-105">In questo argomento viene illustrato l'approccio tramite configurazione.</span><span class="sxs-lookup"><span data-stu-id="b2e94-105">This topic demonstrates the configuration approach.</span></span>  
  
 <span data-ttu-id="b2e94-106">La parte della procedura che consente all'endpoint di servizio di diventare compatibili con AJAX ASP.NET consiste nel configurare l'endpoint da usare la <xref:System.ServiceModel.WebHttpBinding> e aggiungere i [ \<enableWebScript >](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="b2e94-106">The part of the procedure that enables the service endpoint to become ASP.NET AJAX-enabled consists of configuring the endpoint to use the <xref:System.ServiceModel.WebHttpBinding> and to add the [\<enableWebScript>](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) endpoint behavior.</span></span> <span data-ttu-id="b2e94-107">Dopo aver configurato l'endpoint, i passaggi per implementare e ospitare il servizio sono simili a quelli utilizzati da qualsiasi servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="b2e94-107">After configuring the endpoint, the steps to implement and host the service are similar to those used by any WCF service.</span></span> <span data-ttu-id="b2e94-108">Per un esempio funzionante, vedere la [servizio AJAX con HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span><span class="sxs-lookup"><span data-stu-id="b2e94-108">For a working example, see the [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span></span>  
  
 <span data-ttu-id="b2e94-109">Per altre informazioni su come configurare un endpoint ASP.NET AJAX senza usare la configurazione, vedere [come: Aggiungere un Endpoint ASP.NET AJAX senza usare la configurazione](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="b2e94-109">For more information about how to configure an ASP.NET AJAX endpoint without using configuration, see [How to: Add an ASP.NET AJAX Endpoint Without Using Configuration](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).</span></span>  
  
### <a name="to-create-a-basic-wcf-service"></a><span data-ttu-id="b2e94-110">Per creare un servizio WFC di base</span><span class="sxs-lookup"><span data-stu-id="b2e94-110">To create a basic WCF service</span></span>  
  
1.  <span data-ttu-id="b2e94-111">Definire un contratto di servizio WCF basic con un'interfaccia contrassegnata con il <xref:System.ServiceModel.ServiceContractAttribute> attributo.</span><span class="sxs-lookup"><span data-stu-id="b2e94-111">Define a basic WCF service contract with an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="b2e94-112">Contrassegnare ogni operazione con <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b2e94-112">Mark each operation with the <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="b2e94-113">Assicurarsi di impostare la proprietà <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="b2e94-113">Be sure to set the <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> property.</span></span>  
  
    ```  
    [ServiceContract(Namespace = "MyService")]  
    public interface ICalculator  
    {  
        [OperationContract]  
         // This operation returns the sum of d1 and d2.  
        double Add(double n1, double n2);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2.  <span data-ttu-id="b2e94-114">Implementare il contratto di servizio `ICalculator` con `CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="b2e94-114">Implement the `ICalculator` service contract with a `CalculatorService`.</span></span>  
  
    ```  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
  
    //Other operations omitted…  
    ```  
  
3.  <span data-ttu-id="b2e94-115">Definire uno spazio dei nomi per le implementazioni `ICalculator` e `CalculatorService` eseguendo il wrapping di queste ultime in un blocco dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b2e94-115">Define a namespace for the `ICalculator` and `CalculatorService` implementations by wrapping them in a namespace block.</span></span>  
  
    ```  
    Namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
### <a name="to-create-an-aspnet-ajax-endpoint-for-the-service"></a><span data-ttu-id="b2e94-116">Per creare endpoint ASP.NET AJAX per il servizio.</span><span class="sxs-lookup"><span data-stu-id="b2e94-116">To create an ASP.NET AJAX endpoint for the service</span></span>  
  
1.  <span data-ttu-id="b2e94-117">Creare una configurazione del comportamento e specificare il [ \<enableWebScript >](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) comportamento per gli endpoint ASP.NET compatibile con AJAX del servizio.</span><span class="sxs-lookup"><span data-stu-id="b2e94-117">Create a behavior configuration and specify the [\<enableWebScript>](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) behavior for ASP.NET AJAX-enabled endpoints of the service.</span></span>  
  
    ```xml  
    <system.serviceModel>  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name="AspNetAjaxBehavior">  
                    <enableWebScript />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
    </system.serviceModel>  
    ```  
  
2.  <span data-ttu-id="b2e94-118">Creare un endpoint per il servizio che utilizza <xref:System.ServiceModel.WebHttpBinding> e il comportamento ASP.NET AJAX definito nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="b2e94-118">Create an endpoint for the service that uses the <xref:System.ServiceModel.WebHttpBinding> and the ASP.NET AJAX behavior defined in the previous step.</span></span>  
  
    ```xml  
    <system.serviceModel>  
        <services>  
            <service name="Microsoft.Ajax.Samples.CalculatorService">  
                <endpoint address=""  
                    behaviorConfiguration="AspNetAjaxBehavior"   
                    binding="webHttpBinding"  
                    contract="Microsoft.Ajax.Samples.ICalculator" />  
            </service>  
        </services>  
    </system.serviceModel>   
    ```  
  
### <a name="to-host-the-service-in-iis"></a><span data-ttu-id="b2e94-119">Per ospitare il servizio in IIS</span><span class="sxs-lookup"><span data-stu-id="b2e94-119">To host the service in IIS</span></span>  
  
1.  <span data-ttu-id="b2e94-120">Per ospitare il servizio in IIS, creare nell'applicazione un nuovo file denominato "service" con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="b2e94-120">To host the service in IIS, create a new file named service with a .svc extension in the application.</span></span> <span data-ttu-id="b2e94-121">Modificare questo file aggiungendo le appropriate [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) informazioni della direttiva per il servizio.</span><span class="sxs-lookup"><span data-stu-id="b2e94-121">Edit this file by adding the appropriate [\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive information for the service.</span></span> <span data-ttu-id="b2e94-122">Ad esempio, il file del servizio per l'esempio `CalculatorService` contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b2e94-122">For example, the content in the service file for the `CalculatorService` sample contains the following information.</span></span>  
  
    ```  
    <%@ServiceHost   
    language=c#   
    Debug="true"   
    Service="Microsoft.Ajax.Samples.CalculatorService"  
    %>  
    ```  
  
2.  <span data-ttu-id="b2e94-123">Per altre informazioni sull'hosting in IIS, vedere [come: Ospitare un servizio WCF in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).</span><span class="sxs-lookup"><span data-stu-id="b2e94-123">For more information about hosting in IIS, see [How to: Host a WCF Service in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).</span></span>  
  
### <a name="to-call-the-service"></a><span data-ttu-id="b2e94-124">Per chiamare il servizio</span><span class="sxs-lookup"><span data-stu-id="b2e94-124">To call the service</span></span>  
  
1.  <span data-ttu-id="b2e94-125">L'endpoint viene configurato in un indirizzo vuoto relativo al file con estensione svc, in modo che il servizio è ora disponibile e può essere richiamato inviando richieste a Service. svc /\<operazione >, ad esempio service.svc/Add per il `Add` operazione.</span><span class="sxs-lookup"><span data-stu-id="b2e94-125">The endpoint is configured at an empty address relative to the .svc file, so the service is now available and can be invoked by sending requests to service.svc/\<operation> - for example, service.svc/Add for the `Add` operation.</span></span> <span data-ttu-id="b2e94-126">È possibile utilizzarlo immettendo l'URL dell'endpoint nella raccolta degli script del controllo Script Manager ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="b2e94-126">You can use it by entering the endpoint URL into the Scripts collection of the ASP.NET AJAX Script Manager control.</span></span> <span data-ttu-id="b2e94-127">Per un esempio, vedere la [servizio AJAX con HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span><span class="sxs-lookup"><span data-stu-id="b2e94-127">For an example, see the [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2e94-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2e94-128">See also</span></span>

- [<span data-ttu-id="b2e94-129">Creazione di servizi WCF per ASP.NET AJAX</span><span class="sxs-lookup"><span data-stu-id="b2e94-129">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [<span data-ttu-id="b2e94-130">Procedura: Eseguire la migrazione di servizi Web ASP.NET compatibili AJAX a WCF</span><span class="sxs-lookup"><span data-stu-id="b2e94-130">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
