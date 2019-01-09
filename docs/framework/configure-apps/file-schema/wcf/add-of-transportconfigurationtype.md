---
title: '&lt;add&gt; di &lt;transportConfigurationType&gt;'
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: 1079b25ce137dc89fc31f46a11f3720486462021
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149137"
---
# <a name="ltaddgt-of-lttransportconfigurationtypegt"></a><span data-ttu-id="f23a3-102">&lt;add&gt; di &lt;transportConfigurationType&gt;</span><span class="sxs-lookup"><span data-stu-id="f23a3-102">&lt;add&gt; of &lt;transportConfigurationType&gt;</span></span>
<span data-ttu-id="f23a3-103">Questo elemento è una coppia chiave/valore che identifica il tipo di un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="f23a3-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
 <span data-ttu-id="f23a3-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f23a3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f23a3-105">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="f23a3-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="f23a3-106">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="f23a3-106">\<transportConfigurationTypes></span></span>  
<span data-ttu-id="f23a3-107">\<add></span><span class="sxs-lookup"><span data-stu-id="f23a3-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f23a3-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f23a3-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f23a3-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f23a3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f23a3-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f23a3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f23a3-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="f23a3-111">Attributes</span></span>  
  
|<span data-ttu-id="f23a3-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="f23a3-112">Attribute</span></span>|<span data-ttu-id="f23a3-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f23a3-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f23a3-114">name</span><span class="sxs-lookup"><span data-stu-id="f23a3-114">name</span></span>|<span data-ttu-id="f23a3-115">Attributo stringa obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f23a3-115">Required String attribute.</span></span><br /><br /> <span data-ttu-id="f23a3-116">Contiene una chiave definita dall'utente che identifica in modo univoco il tipo di trasporto.</span><span class="sxs-lookup"><span data-stu-id="f23a3-116">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="f23a3-117">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="f23a3-117">transportConfigurationType</span></span>|<span data-ttu-id="f23a3-118">Stringa contenente il tipo che implementa il trasporto specifico.</span><span class="sxs-lookup"><span data-stu-id="f23a3-118">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f23a3-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f23a3-119">Child Elements</span></span>  
 <span data-ttu-id="f23a3-120">nessuno</span><span class="sxs-lookup"><span data-stu-id="f23a3-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f23a3-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f23a3-121">Parent Elements</span></span>  
  
|<span data-ttu-id="f23a3-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="f23a3-122">Element</span></span>|<span data-ttu-id="f23a3-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f23a3-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f23a3-124">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="f23a3-124">\<transportConfigurationTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transportconfigurationtypes.md)|<span data-ttu-id="f23a3-125">Raccolta di tipi che implementano il trasporto specifico.</span><span class="sxs-lookup"><span data-stu-id="f23a3-125">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f23a3-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="f23a3-126">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="f23a3-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f23a3-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [<span data-ttu-id="f23a3-128">Hosting</span><span class="sxs-lookup"><span data-stu-id="f23a3-128">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
