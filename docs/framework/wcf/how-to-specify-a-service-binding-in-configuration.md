---
title: "Procedura: specificare un'associazione al servizio in configurazione"
description: Informazioni su come configurare un endpoint per un servizio WCF in un file di configurazione. Un contratto viene definito per un servizio e implementato in una classe.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 885037f7-1c2b-4d7a-90d9-06b89be172f2
ms.openlocfilehash: 92d0834091a1f243df6be214f606fbf0093dca54
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244556"
---
# <a name="how-to-specify-a-service-binding-in-configuration"></a><span data-ttu-id="f5638-104">Procedura: specificare un'associazione al servizio in configurazione</span><span class="sxs-lookup"><span data-stu-id="f5638-104">How to: Specify a Service Binding in Configuration</span></span>
<span data-ttu-id="f5638-105">In questo esempio viene definito un contratto `ICalculator` per un servizio calcolatrice di base, il servizio viene implementato nella classe `CalculatorService`, quindi l'endpoint relativo viene configurato nel file Web.config dove viene specificato che il servizio utilizza <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="f5638-105">In this example, an `ICalculator` contract is defined for a basic calculator service, the service is implemented in the `CalculatorService` class, and then its endpoint is configured in the Web.config file, where it is specified that the service uses the <xref:System.ServiceModel.BasicHttpBinding>.</span></span> <span data-ttu-id="f5638-106">Per una descrizione di come configurare questo servizio usando codice anziché una configurazione, vedere [procedura: specificare un'associazione al servizio nel codice](how-to-specify-a-service-binding-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="f5638-106">For a description of how to configure this service using code instead of a configuration, see [How to: Specify a Service Binding in Code](how-to-specify-a-service-binding-in-code.md).</span></span>  
  
 <span data-ttu-id="f5638-107">La procedura solitamente consigliata consiste nello specificare in modo dichiarativo l'associazione e le informazioni dell'indirizzo nella configurazione anziché in modo imperativo nel codice.</span><span class="sxs-lookup"><span data-stu-id="f5638-107">It is usually the best practice to specify the binding and address information declaratively in configuration rather than imperatively in code.</span></span> <span data-ttu-id="f5638-108">In genere definire endpoint nel codice non è pratico in quanto le associazioni e gli indirizzi di un servizio distribuito sono solitamente diversi da quelli usati durante lo sviluppo del servizio.</span><span class="sxs-lookup"><span data-stu-id="f5638-108">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="f5638-109">Più in generale, se le informazioni su associazione e indirizzo non vengono incluse nel codice, tali dati possono essere modificati senza dover compilare o distribuire nuovamente l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f5638-109">More generally, keeping the binding and addressing information out of the code allows them to change without having to recompile or redeploy the application.</span></span>  
  
 <span data-ttu-id="f5638-110">È possibile eseguire tutti i passaggi di configurazione seguenti utilizzando lo [strumento Editor di configurazione (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="f5638-110">All of the following configuration steps can be undertaken using the [Configuration Editor Tool (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
 <span data-ttu-id="f5638-111">Per la copia di origine di questo esempio, vedere l'oggetto di [base](./samples/basicbinding.md).</span><span class="sxs-lookup"><span data-stu-id="f5638-111">For the source copy of this example, see [BasicBinding](./samples/basicbinding.md).</span></span>  
  
## <a name="to-specify-the-basichttpbinding-to-use-to-configure-the-service"></a><span data-ttu-id="f5638-112">Per specificare l'elemento BasicHttpBinding necessario per la configurazione del servizio</span><span class="sxs-lookup"><span data-stu-id="f5638-112">To specify the BasicHttpBinding to use to configure the service</span></span>  
  
1. <span data-ttu-id="f5638-113">Definire un contratto di servizio per il tipo di servizio.</span><span class="sxs-lookup"><span data-stu-id="f5638-113">Define a service contract for the type of service.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureServiceBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureservicebinding/cs/source.cs#1)]
     [!code-vb[C_HowTo_ConfigureServiceBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_configureservicebinding/vb/source.vb#1)]  
  
2. <span data-ttu-id="f5638-114">Implementare il contratto di servizio in una classe del servizio.</span><span class="sxs-lookup"><span data-stu-id="f5638-114">Implement the service contract in a service class.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureServiceBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureservicebinding/cs/source.cs#2)]
     [!code-vb[C_HowTo_ConfigureServiceBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_configureservicebinding/vb/source.vb#2)]  
  
    > [!NOTE]
    > <span data-ttu-id="f5638-115">L'indirizzo o le informazioni di associazione non sono specificate nell'implementazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="f5638-115">Address or binding information is not specified inside the implementation of the service.</span></span> <span data-ttu-id="f5638-116">Non è necessario, inoltre, scrivere codice per recuperare le informazioni dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f5638-116">Also, code does not have to be written to fetch that information from the configuration file.</span></span>  
  
3. <span data-ttu-id="f5638-117">Creare un file Web.config per configurare un endpoint per l'elemento  `CalculatorService` che utilizza la classe <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="f5638-117">Create a Web.config file to configure an endpoint for the `CalculatorService` that uses the <xref:System.ServiceModel.WSHttpBinding>.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service name=" CalculatorService" >  

            <!-- Leave the address blank to be populated by default -->
            <!-- from the hosting environment,in this case IIS, so -->
            <!-- the address will just be that of the IIS Virtual -->
            <!-- Directory. -->

            <!-- Specify the binding configuration name for that -->
            <!-- binding type. This is optional but useful if you -->
            <!-- want to modify the properties of the binding. -->
            <!-- The bindingConfiguration name Binding1 is defined -->
            <!-- below in the bindings element. -->
            <endpoint
                address=""
                binding="wsHttpBinding"  
                bindingConfiguration="Binding1"  
                contract="ICalculator" />  
          </service>  
        </services>  
        <bindings>  
          <wsHttpBinding>  
            <binding name="Binding1">  
              <!-- Binding property values can be modified here. -->  
              <!-- See the next procedure. -->  
            </binding>  
          </wsHttpBinding>  
       </bindings>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
4. <span data-ttu-id="f5638-118">Creare un file Service.svc contenente la riga seguente e salvarlo nella directory virtuale di Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="f5638-118">Create a Service.svc file that contains the following line and place it in your Internet Information Services (IIS) virtual directory.</span></span>  
  
    ```  
    <%@ServiceHost language=c# Service="CalculatorService" %>
    ```  
  
## <a name="to-modify-the-default-values-of-the-binding-properties"></a><span data-ttu-id="f5638-119">Per modificare i valori predefiniti delle proprietà dell'associazione</span><span class="sxs-lookup"><span data-stu-id="f5638-119">To modify the default values of the binding properties</span></span>  
  
1. <span data-ttu-id="f5638-120">Per modificare uno dei valori di proprietà predefiniti di <xref:System.ServiceModel.WSHttpBinding> , creare un nuovo nome di configurazione dell'associazione, `<binding name="Binding1">` all'interno dell' [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) elemento e impostare i nuovi valori per gli attributi dell'associazione in questo elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="f5638-120">To modify one of the default property values of the <xref:System.ServiceModel.WSHttpBinding>, create a new binding configuration name - `<binding name="Binding1">` - within the [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) element and set the new values for the attributes of the binding in this binding element.</span></span> <span data-ttu-id="f5638-121">Per impostare, ad esempio valori di timeout di apertura e chiusura predefiniti di 1-2 minuti, aggiungere quanto segue nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f5638-121">For example, to change the default open and close timeout values of 1 minute to 2 minutes, add the following to the configuration file.</span></span>  
  
    ```xml  
    <wsHttpBinding>  
      <binding name="Binding1"  
               closeTimeout="00:02:00"  
               openTimeout="00:02:00">  
      </binding>  
    </wsHttpBinding>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f5638-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5638-122">See also</span></span>

- [<span data-ttu-id="f5638-123">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="f5638-123">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="f5638-124">Specifica di un indirizzo dell'endpoint</span><span class="sxs-lookup"><span data-stu-id="f5638-124">Specifying an Endpoint Address</span></span>](specifying-an-endpoint-address.md)
