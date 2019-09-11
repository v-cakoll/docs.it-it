---
title: <add> di <transportConfigurationType>
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: adf4cd7f02db6535c5950443d09476a9a5ff63fb
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850315"
---
# <a name="add-of-transportconfigurationtype"></a><span data-ttu-id="afbd2-102">\<aggiungere > di \<transportConfigurationType ></span><span class="sxs-lookup"><span data-stu-id="afbd2-102">\<add> of \<transportConfigurationType></span></span>
<span data-ttu-id="afbd2-103">Questo elemento è una coppia chiave/valore che identifica il tipo di un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="afbd2-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
<span data-ttu-id="afbd2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="afbd2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="afbd2-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="afbd2-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="afbd2-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceHostingEnvironment**](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="afbd2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="afbd2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> transportConfigurationTypes**](transportconfigurationtypes.md)</span><span class="sxs-lookup"><span data-stu-id="afbd2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<transportConfigurationTypes>**](transportconfigurationtypes.md)</span></span>\
<span data-ttu-id="afbd2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Aggiungi >**</span><span class="sxs-lookup"><span data-stu-id="afbd2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afbd2-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="afbd2-109">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="afbd2-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="afbd2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="afbd2-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="afbd2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="afbd2-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="afbd2-112">Attributes</span></span>  
  
|<span data-ttu-id="afbd2-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="afbd2-113">Attribute</span></span>|<span data-ttu-id="afbd2-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="afbd2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="afbd2-115">name</span><span class="sxs-lookup"><span data-stu-id="afbd2-115">name</span></span>|<span data-ttu-id="afbd2-116">Attributo stringa obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="afbd2-116">Required String attribute.</span></span><br /><br /> <span data-ttu-id="afbd2-117">Contiene una chiave definita dall'utente che identifica in modo univoco il tipo di trasporto.</span><span class="sxs-lookup"><span data-stu-id="afbd2-117">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="afbd2-118">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="afbd2-118">transportConfigurationType</span></span>|<span data-ttu-id="afbd2-119">Stringa contenente il tipo che implementa il trasporto specifico.</span><span class="sxs-lookup"><span data-stu-id="afbd2-119">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="afbd2-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="afbd2-120">Child Elements</span></span>  
 <span data-ttu-id="afbd2-121">Nessuna</span><span class="sxs-lookup"><span data-stu-id="afbd2-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="afbd2-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="afbd2-122">Parent Elements</span></span>  
  
|<span data-ttu-id="afbd2-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="afbd2-123">Element</span></span>|<span data-ttu-id="afbd2-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="afbd2-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="afbd2-125">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="afbd2-125">\<transportConfigurationTypes></span></span>](transportconfigurationtypes.md)|<span data-ttu-id="afbd2-126">Raccolta di tipi che implementano il trasporto specifico.</span><span class="sxs-lookup"><span data-stu-id="afbd2-126">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="afbd2-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="afbd2-127">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="afbd2-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afbd2-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="afbd2-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="afbd2-129">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
