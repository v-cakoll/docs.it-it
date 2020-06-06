---
title: <add> di <transportConfigurationType>
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: adf4cd7f02db6535c5950443d09476a9a5ff63fb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850315"
---
# <a name="add-of-transportconfigurationtype"></a><span data-ttu-id="cc43b-102">\<add> di \<transportConfigurationType></span><span class="sxs-lookup"><span data-stu-id="cc43b-102">\<add> of \<transportConfigurationType></span></span>
<span data-ttu-id="cc43b-103">Questo elemento è una coppia chiave/valore che identifica il tipo di un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="cc43b-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<transportConfigurationTypes>**](transportconfigurationtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="cc43b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cc43b-104">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cc43b-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cc43b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="cc43b-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cc43b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cc43b-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="cc43b-107">Attributes</span></span>  
  
|<span data-ttu-id="cc43b-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="cc43b-108">Attribute</span></span>|<span data-ttu-id="cc43b-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cc43b-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cc43b-110">name</span><span class="sxs-lookup"><span data-stu-id="cc43b-110">name</span></span>|<span data-ttu-id="cc43b-111">Attributo stringa obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="cc43b-111">Required String attribute.</span></span><br /><br /> <span data-ttu-id="cc43b-112">Contiene una chiave definita dall'utente che identifica in modo univoco il tipo di trasporto.</span><span class="sxs-lookup"><span data-stu-id="cc43b-112">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="cc43b-113">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="cc43b-113">transportConfigurationType</span></span>|<span data-ttu-id="cc43b-114">Stringa contenente il tipo che implementa il trasporto specifico.</span><span class="sxs-lookup"><span data-stu-id="cc43b-114">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cc43b-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cc43b-115">Child Elements</span></span>  
 <span data-ttu-id="cc43b-116">nessuno</span><span class="sxs-lookup"><span data-stu-id="cc43b-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cc43b-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cc43b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="cc43b-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="cc43b-118">Element</span></span>|<span data-ttu-id="cc43b-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cc43b-119">Description</span></span>|  
|-------------|-----------------|  
|[\<transportConfigurationTypes>](transportconfigurationtypes.md)|<span data-ttu-id="cc43b-120">Raccolta di tipi che implementano il trasporto specifico.</span><span class="sxs-lookup"><span data-stu-id="cc43b-120">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cc43b-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="cc43b-121">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="cc43b-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc43b-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="cc43b-123">Hosting</span><span class="sxs-lookup"><span data-stu-id="cc43b-123">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
