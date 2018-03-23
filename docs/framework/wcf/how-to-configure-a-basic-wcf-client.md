---
title: 'Procedura: configurare un client Windows Communication Foundation di base'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF clients [WCF], configuring
ms.assetid: d067b86d-afb0-47bf-94f6-45180a3d8d78
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f23918031c6cc8cd6509d7b7c079b8df050bbb08
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2018
---
# <a name="how-to-configure-a-basic-windows-communication-foundation-client"></a><span data-ttu-id="13f5f-102">Procedura: configurare un client Windows Communication Foundation di base</span><span class="sxs-lookup"><span data-stu-id="13f5f-102">How to: Configure a Basic Windows Communication Foundation Client</span></span>
<span data-ttu-id="13f5f-103">Questa è la quinta delle sei attività necessarie per creare un'applicazione [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] di base.</span><span class="sxs-lookup"><span data-stu-id="13f5f-103">This is the fifth of six tasks required to create a basic [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] application.</span></span> <span data-ttu-id="13f5f-104">Per una panoramica di tutte e sei le attività, vedere il [esercitazione introduttiva](../../../docs/framework/wcf/getting-started-tutorial.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="13f5f-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>  
  
 <span data-ttu-id="13f5f-105">Questo file di configurazione client che è stato generato utilizzando la funzionalità Aggiungi riferimento al servizio di disuccess argomento [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] o [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="13f5f-105">This topic disuccess the client configuration file that was generated using the Add Service Reference functionality of [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] or the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="13f5f-106">La configurazione del client è costituita dalla specifica dell'endpoint usato dal client per accedere al servizio.</span><span class="sxs-lookup"><span data-stu-id="13f5f-106">Configuring the client consists of specifying the endpoint that the client uses to access the service.</span></span> <span data-ttu-id="13f5f-107">Un endpoint ha un indirizzo, un'associazione e un contratto, e ognuno di questi elementi deve essere specificato nel processo di configurazione del client.</span><span class="sxs-lookup"><span data-stu-id="13f5f-107">An endpoint has an address, a binding and a contract, and each of these must be specified in the process of configuring the client.</span></span>  
  
### <a name="to-configure-a-windows-communication-foundation-client"></a><span data-ttu-id="13f5f-108">Per configurare un client Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="13f5f-108">To configure a Windows Communication Foundation client</span></span>  
  
1.  <span data-ttu-id="13f5f-109">Aprire il file di configurazione generato (App.config) dal progetto GettingStartedClient.</span><span class="sxs-lookup"><span data-stu-id="13f5f-109">Open the generated configuration file (App.config) from the GettingStartedClient project.</span></span> <span data-ttu-id="13f5f-110">L'esempio seguente è una visualizzazione del file di configurazione generato.</span><span class="sxs-lookup"><span data-stu-id="13f5f-110">The following example is a view of the generated configuration file.</span></span> <span data-ttu-id="13f5f-111">Sotto il [ \<System. ServiceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) sezione, trovare il [ \<endpoint >](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) elemento.</span><span class="sxs-lookup"><span data-stu-id="13f5f-111">Under the [\<system.serviceModel>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) section, find the [\<endpoint>](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) element.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
        <startup>   
          <!-- specifies the version of WCF to use-->  
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5,Profile=Client" />  
        </startup>  
        <system.serviceModel>  
            <bindings>  
                <!-- Uses wsHttpBinding-->  
                <wsHttpBinding>  
                    <binding name="WSHttpBinding_ICalculator" />  
                </wsHttpBinding>  
            </bindings>  
            <client>  
                <!-- specifies the endpoint to use when calling the service -->  
                <endpoint address="http://localhost:8000/ServiceModelSamples/Service/CalculatorService"  
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"  
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">  
                    <identity>  
                        <userPrincipalName value="migree@redmond.corp.microsoft.com" />  
                    </identity>  
                </endpoint>  
            </client>  
        </system.serviceModel>  
    </configuration>   
    ```  
  
     <span data-ttu-id="13f5f-112">In questo esempio viene configurato l'endpoint usato dal client per accedere al servizio disponibile all'indirizzo seguente: http://localhost:8000/ServiceModelSamples/Service/CalculatorService</span><span class="sxs-lookup"><span data-stu-id="13f5f-112">This example configures the endpoint that the client uses to access the service that is located at the following address: http://localhost:8000/ServiceModelSamples/Service/CalculatorService</span></span>  
  
     <span data-ttu-id="13f5f-113">L'elemento endpoint specifica che il contratto di servizio `ServiceReference1.ICalculator` viene usato per la comunicazione tra il client e il servizio di WCF.</span><span class="sxs-lookup"><span data-stu-id="13f5f-113">The endpoint element specifies that the `ServiceReference1.ICalculator` service contract is used for communication between the WCF client and service.</span></span> <span data-ttu-id="13f5f-114">Il canale WCF è configurato con fornito dal sistema <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>.</span><span class="sxs-lookup"><span data-stu-id="13f5f-114">The WCF channel is configured with the system-provided <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>.</span></span> <span data-ttu-id="13f5f-115">Questo contratto è stato generato usando Aggiungi riferimento al servizio in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="13f5f-115">This contract was generated by using Add Service Reference in Visual Studio.</span></span> <span data-ttu-id="13f5f-116">Si tratta essenzialmente di una copia del contratto che è stato definito nel progetto GettingStartedLib.</span><span class="sxs-lookup"><span data-stu-id="13f5f-116">It is essentially a copy of the contract that was defined in the GettingStartedLib project.</span></span> <span data-ttu-id="13f5f-117">Il <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> associazione specifica HTTP come trasporto, sicurezza interoperativa e altri dettagli di configurazione.</span><span class="sxs-lookup"><span data-stu-id="13f5f-117">The <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>  
  
2.  [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="13f5f-118"> come usare il client generato con questa configurazione, vedere [procedura: utilizzare un Client](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="13f5f-118"> how to use the generated client with this configuration, see [How to: Use a Client](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13f5f-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13f5f-119">See Also</span></span>  
 [<span data-ttu-id="13f5f-120">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="13f5f-120">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="13f5f-121">Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="13f5f-121">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [<span data-ttu-id="13f5f-122">Procedura: Creare un client</span><span class="sxs-lookup"><span data-stu-id="13f5f-122">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [<span data-ttu-id="13f5f-123">Introduzione</span><span class="sxs-lookup"><span data-stu-id="13f5f-123">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="13f5f-124">Servizio indipendente</span><span class="sxs-lookup"><span data-stu-id="13f5f-124">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
