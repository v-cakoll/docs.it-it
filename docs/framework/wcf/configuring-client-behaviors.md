---
title: Configurazione dei comportamenti client
description: "Informazioni sui due modi in cui WCF configura i comportamenti: nel file di configurazione dell'applicazione o a livello di codice dall'applicazione chiamante."
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: df5b32fa-e73b-4e8e-b66f-357c748e0173
ms.openlocfilehash: 4b83862221cf249455478c3ade159a3101062f3e
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245440"
---
# <a name="configuring-client-behaviors"></a><span data-ttu-id="7f7a0-103">Configurazione dei comportamenti client</span><span class="sxs-lookup"><span data-stu-id="7f7a0-103">Configuring Client Behaviors</span></span>
<span data-ttu-id="7f7a0-104">Windows Communication Foundation (WCF) configura i comportamenti in due modi: facendo riferimento alle configurazioni del comportamento, definite nella `<behavior>` sezione di un file di configurazione dell'applicazione client, o a livello di codice nell'applicazione chiamante.</span><span class="sxs-lookup"><span data-stu-id="7f7a0-104">Windows Communication Foundation (WCF) configures behaviors in two ways: either by referring to behavior configurations -- which are defined in the `<behavior>` section of a client application configuration file – or programmatically in the calling application.</span></span> <span data-ttu-id="7f7a0-105">In questo argomento vengono illustrati entrambi gli approcci.</span><span class="sxs-lookup"><span data-stu-id="7f7a0-105">This topic describes both approaches.</span></span>  
  
 <span data-ttu-id="7f7a0-106">Quando di usa un file di configurazione, la configurazione del comportamento è una raccolta denominata di impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7f7a0-106">When using a configuration file, behavior configuration is a named collection of configuration settings.</span></span> <span data-ttu-id="7f7a0-107">Il nome di ogni configurazione di comportamento deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="7f7a0-107">The name of each behavior configuration must be unique.</span></span> <span data-ttu-id="7f7a0-108">Questa stringa viene usata nell'attributo `behaviorConfiguration` di una configurazione endpoint per collegare l'endpoint al comportamento.</span><span class="sxs-lookup"><span data-stu-id="7f7a0-108">This string is used in the `behaviorConfiguration` attribute of an endpoint configuration to link the endpoint to the behavior.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f7a0-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="7f7a0-109">Example</span></span>  
 <span data-ttu-id="7f7a0-110">Nel codice di configurazione seguente viene definito un comportamento denominato `myBehavior`.</span><span class="sxs-lookup"><span data-stu-id="7f7a0-110">The following configuration code defines a behavior called `myBehavior`.</span></span> <span data-ttu-id="7f7a0-111">L'endpoint client fa riferimento a questo comportamento nell'attributo `behaviorConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="7f7a0-111">The client endpoint references this behavior in the `behaviorConfiguration` attribute.</span></span>  
  
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
  
## <a name="using-behaviors-programmatically"></a><span data-ttu-id="7f7a0-112">Uso di comportamenti a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="7f7a0-112">Using Behaviors Programmatically</span></span>  
 <span data-ttu-id="7f7a0-113">È inoltre possibile configurare o inserire comportamenti a livello di codice individuando la `Behaviors` proprietà appropriata nell'oggetto client Windows Communication Foundation (WCF) o nell'oggetto channel factory client prima di aprire il client.</span><span class="sxs-lookup"><span data-stu-id="7f7a0-113">You can also configure or insert behaviors programmatically by locating the appropriate `Behaviors` property on the Windows Communication Foundation (WCF) client object or on the client channel factory object prior to opening the client.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f7a0-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="7f7a0-114">Example</span></span>  
 <span data-ttu-id="7f7a0-115">Nell'esempio di codice seguente viene illustrato come inserire un comportamento a livello di programmazione accedendo alla proprietà <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> nell'oggetto <xref:System.ServiceModel.Description.ServiceEndpoint> restituito dalla proprietà <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> prima della creazione dell'oggetto channel.</span><span class="sxs-lookup"><span data-stu-id="7f7a0-115">The following code example shows how to programmatically insert a behavior by accessing the <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> property on the <xref:System.ServiceModel.Description.ServiceEndpoint> returned from the <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> property prior to the creation of the channel object.</span></span>  
  
 [!code-csharp[ChannelFactoryBehaviors#10](../../../samples/snippets/csharp/VS_Snippets_CFX/channelfactorybehaviors/cs/client.cs#10)]
 [!code-vb[ChannelFactoryBehaviors#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelfactorybehaviors/vb/client.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="7f7a0-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f7a0-116">See also</span></span>

- [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md)
