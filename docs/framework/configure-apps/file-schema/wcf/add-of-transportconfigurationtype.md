---
title: '&lt;add&gt; di &lt;transportConfigurationType&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cb00a5d5a2b4f64cdce6832faef4822b63f426d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-of-lttransportconfigurationtypegt"></a><span data-ttu-id="09e16-102">&lt;add&gt; di &lt;transportConfigurationType&gt;</span><span class="sxs-lookup"><span data-stu-id="09e16-102">&lt;add&gt; of &lt;transportConfigurationType&gt;</span></span>
<span data-ttu-id="09e16-103">Questo elemento è una coppia chiave/valore che identifica il tipo di un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="09e16-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
 <span data-ttu-id="09e16-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="09e16-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="09e16-105">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="09e16-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="09e16-106">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="09e16-106">\<transportConfigurationTypes></span></span>  
<span data-ttu-id="09e16-107">\<add></span><span class="sxs-lookup"><span data-stu-id="09e16-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09e16-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="09e16-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="String"  
               transportConfigurationType="String"/>   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="09e16-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="09e16-109">Attributes and Elements</span></span>  
 <span data-ttu-id="09e16-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="09e16-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="09e16-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="09e16-111">Attributes</span></span>  
  
|<span data-ttu-id="09e16-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="09e16-112">Attribute</span></span>|<span data-ttu-id="09e16-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="09e16-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="09e16-114">name</span><span class="sxs-lookup"><span data-stu-id="09e16-114">name</span></span>|<span data-ttu-id="09e16-115">Attributo stringa obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="09e16-115">Required String attribute.</span></span><br /><br /> <span data-ttu-id="09e16-116">Contiene una chiave definita dall'utente che identifica in modo univoco il tipo di trasporto.</span><span class="sxs-lookup"><span data-stu-id="09e16-116">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="09e16-117">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="09e16-117">transportConfigurationType</span></span>|<span data-ttu-id="09e16-118">Stringa contenente il tipo che implementa il trasporto specifico.</span><span class="sxs-lookup"><span data-stu-id="09e16-118">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="09e16-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="09e16-119">Child Elements</span></span>  
 <span data-ttu-id="09e16-120">None</span><span class="sxs-lookup"><span data-stu-id="09e16-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="09e16-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="09e16-121">Parent Elements</span></span>  
  
|<span data-ttu-id="09e16-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="09e16-122">Element</span></span>|<span data-ttu-id="09e16-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="09e16-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="09e16-124">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="09e16-124">\<transportConfigurationTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transportconfigurationtypes.md)|<span data-ttu-id="09e16-125">Raccolta di tipi che implementano il trasporto specifico.</span><span class="sxs-lookup"><span data-stu-id="09e16-125">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="09e16-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="09e16-126">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="net.udp"  
      transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## <a name="see-also"></a><span data-ttu-id="09e16-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09e16-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [<span data-ttu-id="09e16-128">Hosting</span><span class="sxs-lookup"><span data-stu-id="09e16-128">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
