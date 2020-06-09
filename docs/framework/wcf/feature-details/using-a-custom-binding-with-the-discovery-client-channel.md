---
title: Uso di un'associazione personalizzata con il canale client di individuazione
ms.date: 03/30/2017
ms.assetid: 36f95e75-04f7-44f3-a995-a0d623624d7f
ms.openlocfilehash: 49983c3ab303d3839350af72b1aa4821c071fe99
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595037"
---
# <a name="using-a-custom-binding-with-the-discovery-client-channel"></a><span data-ttu-id="90239-102">Uso di un'associazione personalizzata con il canale client di individuazione</span><span class="sxs-lookup"><span data-stu-id="90239-102">Using a Custom Binding with the Discovery Client Channel</span></span>
<span data-ttu-id="90239-103">In caso di utilizzo di un'associazione personalizzata con <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, è necessario definire un elemento <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> che crea istanze <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="90239-103">When using a custom binding with the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, you must define a <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> that creates <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instances.</span></span>  
  
## <a name="creating-a-discoveryendpointprovider"></a><span data-ttu-id="90239-104">Creazione di un elemento DiscoveryEndpointProvider</span><span class="sxs-lookup"><span data-stu-id="90239-104">Creating a DiscoveryEndpointProvider</span></span>  
 <span data-ttu-id="90239-105"><xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider>È responsabile della creazione <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> di istanze su richiesta.</span><span class="sxs-lookup"><span data-stu-id="90239-105">The <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> is responsible for creating <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instances on demand.</span></span> <span data-ttu-id="90239-106">Per definire un provider di endpoint di individuazione, derivare una classe da <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> ed eseguire l'override del metodo <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A>, quindi restituire un nuovo endpoint di individuazione.</span><span class="sxs-lookup"><span data-stu-id="90239-106">To define a discovery endpoint provider, derive a class from <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> and override the <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A> method and return a new discovery endpoint.</span></span> <span data-ttu-id="90239-107">Nell'esempio seguente viene mostrato come creare un provider di endpoint di individuazione.</span><span class="sxs-lookup"><span data-stu-id="90239-107">The following example shows how to create a discovery endpoint provider.</span></span>  
  
```csharp
// Extend DiscoveryEndpointProvider class to change the default DiscoveryEndpoint  
// to the DiscoveryClientBindingElement. The Discovery ClientChannel
// uses this endpoint to send Probe message.  
public class UdpDiscoveryEndpointProvider : DiscoveryEndpointProvider  
{  
   public override DiscoveryEndpoint GetDiscoveryEndpoint()  
   {  
      return new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscoveryApril2005);  
   }  
}  
```  
  
 <span data-ttu-id="90239-108">Una volta definito il provider di endpoint di individuazione, è possibile creare un'associazione personalizzata e aggiungere <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, che fa riferimento al provider di endpoint di individuazione, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="90239-108">Once you have defined the discovery endpoint provider you can create a custom binding and add the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, which references the discovery endpoint provider as shown in the following example.</span></span>  
  
```csharp
DiscoveryClientBindingElement discoveryBindingElement = new DiscoveryClientBindingElement();  
  
// Provide the search criteria and the endpoint over which the probe is sent.  
discoveryBindingElement.FindCriteria = new FindCriteria(typeof(ICalculatorService));  
discoveryBindingElement.DiscoveryEndpointProvider = new UdpDiscoveryEndpointProvider();  
  
CustomBinding customBinding = new CustomBinding(new NetTcpBinding());  
// Insert DiscoveryClientBindingElement at the top of the BindingElement stack.  
// An exception is thrown if this binding element is not at the top.  
customBinding.Elements.Insert(0, discoveryBindingElement);  
```  
  
 <span data-ttu-id="90239-109">Per ulteriori informazioni sull'utilizzo del canale del client di individuazione, vedere [utilizzo del canale del client di individuazione](using-the-discovery-client-channel.md).</span><span class="sxs-lookup"><span data-stu-id="90239-109">For more information about using the discovery client channel, see [Using the Discovery Client Channel](using-the-discovery-client-channel.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="90239-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90239-110">See also</span></span>

- [<span data-ttu-id="90239-111">Panoramica di WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="90239-111">WCF Discovery Overview</span></span>](wcf-discovery-overview.md)
- [<span data-ttu-id="90239-112">Utilizzo del canale client di individuazione</span><span class="sxs-lookup"><span data-stu-id="90239-112">Using the Discovery Client Channel</span></span>](using-the-discovery-client-channel.md)
