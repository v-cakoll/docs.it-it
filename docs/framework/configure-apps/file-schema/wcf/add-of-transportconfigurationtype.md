---
title: <add> di <transportConfigurationType>
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: 483ede53df13c896b88171910031dbe9793d66dc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920040"
---
# <a name="add-of-transportconfigurationtype"></a><span data-ttu-id="37737-102">\<aggiungere > di \<transportConfigurationType ></span><span class="sxs-lookup"><span data-stu-id="37737-102">\<add> of \<transportConfigurationType></span></span>
<span data-ttu-id="37737-103">Questo elemento è una coppia chiave/valore che identifica il tipo di un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="37737-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
 <span data-ttu-id="37737-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="37737-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="37737-105">\<ServiceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="37737-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="37737-106">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="37737-106">\<transportConfigurationTypes></span></span>  
<span data-ttu-id="37737-107">\<add></span><span class="sxs-lookup"><span data-stu-id="37737-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37737-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="37737-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="37737-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="37737-109">Attributes and Elements</span></span>  
 <span data-ttu-id="37737-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="37737-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="37737-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="37737-111">Attributes</span></span>  
  
|<span data-ttu-id="37737-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="37737-112">Attribute</span></span>|<span data-ttu-id="37737-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37737-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="37737-114">name</span><span class="sxs-lookup"><span data-stu-id="37737-114">name</span></span>|<span data-ttu-id="37737-115">Attributo stringa obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="37737-115">Required String attribute.</span></span><br /><br /> <span data-ttu-id="37737-116">Contiene una chiave definita dall'utente che identifica in modo univoco il tipo di trasporto.</span><span class="sxs-lookup"><span data-stu-id="37737-116">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="37737-117">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="37737-117">transportConfigurationType</span></span>|<span data-ttu-id="37737-118">Stringa contenente il tipo che implementa il trasporto specifico.</span><span class="sxs-lookup"><span data-stu-id="37737-118">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="37737-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="37737-119">Child Elements</span></span>  
 <span data-ttu-id="37737-120">Nessuna</span><span class="sxs-lookup"><span data-stu-id="37737-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="37737-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="37737-121">Parent Elements</span></span>  
  
|<span data-ttu-id="37737-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="37737-122">Element</span></span>|<span data-ttu-id="37737-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37737-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="37737-124">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="37737-124">\<transportConfigurationTypes></span></span>](transportconfigurationtypes.md)|<span data-ttu-id="37737-125">Raccolta di tipi che implementano il trasporto specifico.</span><span class="sxs-lookup"><span data-stu-id="37737-125">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="37737-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="37737-126">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="37737-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37737-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="37737-128">Hosting</span><span class="sxs-lookup"><span data-stu-id="37737-128">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
