---
title: '&lt;add&gt; di &lt;transportConfigurationType&gt;'
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: 5d13ef51444e1600b0cea5d55a1b5e332e440bc6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32749634"
---
# <a name="ltaddgt-of-lttransportconfigurationtypegt"></a><span data-ttu-id="02ad4-102">&lt;add&gt; di &lt;transportConfigurationType&gt;</span><span class="sxs-lookup"><span data-stu-id="02ad4-102">&lt;add&gt; of &lt;transportConfigurationType&gt;</span></span>
<span data-ttu-id="02ad4-103">Questo elemento è una coppia chiave/valore che identifica il tipo di un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="02ad4-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
 <span data-ttu-id="02ad4-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="02ad4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="02ad4-105">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="02ad4-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="02ad4-106">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="02ad4-106">\<transportConfigurationTypes></span></span>  
<span data-ttu-id="02ad4-107">\<add></span><span class="sxs-lookup"><span data-stu-id="02ad4-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02ad4-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="02ad4-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="String"  
               transportConfigurationType="String"/>   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02ad4-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="02ad4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="02ad4-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="02ad4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02ad4-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="02ad4-111">Attributes</span></span>  
  
|<span data-ttu-id="02ad4-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="02ad4-112">Attribute</span></span>|<span data-ttu-id="02ad4-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02ad4-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="02ad4-114">name</span><span class="sxs-lookup"><span data-stu-id="02ad4-114">name</span></span>|<span data-ttu-id="02ad4-115">Attributo stringa obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="02ad4-115">Required String attribute.</span></span><br /><br /> <span data-ttu-id="02ad4-116">Contiene una chiave definita dall'utente che identifica in modo univoco il tipo di trasporto.</span><span class="sxs-lookup"><span data-stu-id="02ad4-116">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="02ad4-117">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="02ad4-117">transportConfigurationType</span></span>|<span data-ttu-id="02ad4-118">Stringa contenente il tipo che implementa il trasporto specifico.</span><span class="sxs-lookup"><span data-stu-id="02ad4-118">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02ad4-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="02ad4-119">Child Elements</span></span>  
 <span data-ttu-id="02ad4-120">Nessuno</span><span class="sxs-lookup"><span data-stu-id="02ad4-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="02ad4-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="02ad4-121">Parent Elements</span></span>  
  
|<span data-ttu-id="02ad4-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="02ad4-122">Element</span></span>|<span data-ttu-id="02ad4-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02ad4-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02ad4-124">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="02ad4-124">\<transportConfigurationTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transportconfigurationtypes.md)|<span data-ttu-id="02ad4-125">Raccolta di tipi che implementano il trasporto specifico.</span><span class="sxs-lookup"><span data-stu-id="02ad4-125">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="02ad4-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="02ad4-126">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="net.udp"  
      transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## <a name="see-also"></a><span data-ttu-id="02ad4-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02ad4-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [<span data-ttu-id="02ad4-128">Hosting</span><span class="sxs-lookup"><span data-stu-id="02ad4-128">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
