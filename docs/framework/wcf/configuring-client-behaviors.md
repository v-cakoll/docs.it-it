---
title: Configurazione dei comportamenti client
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: df5b32fa-e73b-4e8e-b66f-357c748e0173
ms.openlocfilehash: 83fdc77bd17115f9952f2ca6c494ed0eb873cd9c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59193655"
---
# <a name="configuring-client-behaviors"></a><span data-ttu-id="87607-102">Configurazione dei comportamenti client</span><span class="sxs-lookup"><span data-stu-id="87607-102">Configuring Client Behaviors</span></span>
<span data-ttu-id="87607-103">Windows Communication Foundation (WCF) consente di configurare i comportamenti in due modi: facendo riferimento alle configurazioni dei comportamenti definite nel `<behavior>` sezione di un file di configurazione dell'applicazione client, oppure a livello di codice nel chiamante applicazione.</span><span class="sxs-lookup"><span data-stu-id="87607-103">Windows Communication Foundation (WCF) configures behaviors in two ways: either by referring to behavior configurations -- which are defined in the `<behavior>` section of a client application configuration file – or programmatically in the calling application.</span></span> <span data-ttu-id="87607-104">In questo argomento vengono illustrati entrambi gli approcci.</span><span class="sxs-lookup"><span data-stu-id="87607-104">This topic describes both approaches.</span></span>  
  
 <span data-ttu-id="87607-105">Quando di usa un file di configurazione, la configurazione del comportamento è una raccolta denominata di impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="87607-105">When using a configuration file, behavior configuration is a named collection of configuration settings.</span></span> <span data-ttu-id="87607-106">Il nome di ogni configurazione di comportamento deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="87607-106">The name of each behavior configuration must be unique.</span></span> <span data-ttu-id="87607-107">Questa stringa viene usata nell'attributo `behaviorConfiguration` di una configurazione endpoint per collegare l'endpoint al comportamento.</span><span class="sxs-lookup"><span data-stu-id="87607-107">This string is used in the `behaviorConfiguration` attribute of an endpoint configuration to link the endpoint to the behavior.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87607-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="87607-108">Example</span></span>  
 <span data-ttu-id="87607-109">Nel codice di configurazione seguente viene definito un comportamento denominato `myBehavior`.</span><span class="sxs-lookup"><span data-stu-id="87607-109">The following configuration code defines a behavior called `myBehavior`.</span></span> <span data-ttu-id="87607-110">L'endpoint client fa riferimento a questo comportamento nell'attributo `behaviorConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="87607-110">The client endpoint references this behavior in the `behaviorConfiguration` attribute.</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name="myBehavior">  
                    <clientVia />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
        <bindings>  
            <basicHttpBinding>  
                <binding name="myBinding" maxReceivedMessageSize="10000" />  
            </basicHttpBinding>  
        </bindings>  
        <client>  
            <endpoint address="myAddress" binding="basicHttpBinding" bindingConfiguration="myBinding" behaviorConfiguration="myBehavior" contract="myContract" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="using-behaviors-programmatically"></a><span data-ttu-id="87607-111">Uso di comportamenti a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="87607-111">Using Behaviors Programmatically</span></span>  
 <span data-ttu-id="87607-112">È anche possibile configurare o inserire comportamenti a livello di programmazione individuando appropriato `Behaviors` proprietà sull'oggetto client Windows Communication Foundation (WCF) o l'oggetto channel factory client prima dell'apertura del client.</span><span class="sxs-lookup"><span data-stu-id="87607-112">You can also configure or insert behaviors programmatically by locating the appropriate `Behaviors` property on the Windows Communication Foundation (WCF) client object or on the client channel factory object prior to opening the client.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87607-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="87607-113">Example</span></span>  
 <span data-ttu-id="87607-114">Nell'esempio di codice seguente viene illustrato come inserire un comportamento a livello di programmazione accedendo alla proprietà <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> nell'oggetto <xref:System.ServiceModel.Description.ServiceEndpoint> restituito dalla proprietà <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> prima della creazione dell'oggetto channel.</span><span class="sxs-lookup"><span data-stu-id="87607-114">The following code example shows how to programmatically insert a behavior by accessing the <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> property on the <xref:System.ServiceModel.Description.ServiceEndpoint> returned from the <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> property prior to the creation of the channel object.</span></span>  
  
 [!code-csharp[ChannelFactoryBehaviors#10](../../../samples/snippets/csharp/VS_Snippets_CFX/channelfactorybehaviors/cs/client.cs#10)]
 [!code-vb[ChannelFactoryBehaviors#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelfactorybehaviors/vb/client.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="87607-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87607-115">See also</span></span>

- [<span data-ttu-id="87607-116">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="87607-116">\<behaviors></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)
