---
title: <add> di <transportConfigurationType>
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: c71a58b13e89bedb5eed24d784c82fb1525f7625
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701437"
---
# <a name="add-of-transportconfigurationtype"></a><span data-ttu-id="8e724-102">\<aggiungere > di \<transportConfigurationType ></span><span class="sxs-lookup"><span data-stu-id="8e724-102">\<add> of \<transportConfigurationType></span></span>
<span data-ttu-id="8e724-103">Questo elemento è una coppia chiave/valore che identifica il tipo di un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="8e724-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
 <span data-ttu-id="8e724-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8e724-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8e724-105">\<ServiceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="8e724-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="8e724-106">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="8e724-106">\<transportConfigurationTypes></span></span>  
<span data-ttu-id="8e724-107">\<add></span><span class="sxs-lookup"><span data-stu-id="8e724-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e724-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8e724-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e724-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8e724-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8e724-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8e724-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e724-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="8e724-111">Attributes</span></span>  
  
|<span data-ttu-id="8e724-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="8e724-112">Attribute</span></span>|<span data-ttu-id="8e724-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8e724-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8e724-114">name</span><span class="sxs-lookup"><span data-stu-id="8e724-114">name</span></span>|<span data-ttu-id="8e724-115">Attributo stringa obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8e724-115">Required String attribute.</span></span><br /><br /> <span data-ttu-id="8e724-116">Contiene una chiave definita dall'utente che identifica in modo univoco il tipo di trasporto.</span><span class="sxs-lookup"><span data-stu-id="8e724-116">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="8e724-117">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="8e724-117">transportConfigurationType</span></span>|<span data-ttu-id="8e724-118">Stringa contenente il tipo che implementa il trasporto specifico.</span><span class="sxs-lookup"><span data-stu-id="8e724-118">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e724-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8e724-119">Child Elements</span></span>  
 <span data-ttu-id="8e724-120">nessuno</span><span class="sxs-lookup"><span data-stu-id="8e724-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8e724-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8e724-121">Parent Elements</span></span>  
  
|<span data-ttu-id="8e724-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="8e724-122">Element</span></span>|<span data-ttu-id="8e724-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8e724-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e724-124">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="8e724-124">\<transportConfigurationTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transportconfigurationtypes.md)|<span data-ttu-id="8e724-125">Raccolta di tipi che implementano il trasporto specifico.</span><span class="sxs-lookup"><span data-stu-id="8e724-125">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8e724-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="8e724-126">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="8e724-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e724-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="8e724-128">Hosting</span><span class="sxs-lookup"><span data-stu-id="8e724-128">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
