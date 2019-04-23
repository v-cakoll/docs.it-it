---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 4d7fdfb1cccb14f03d11864f1939cb578c79880a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130624"
---
# <a name="defaultports"></a><span data-ttu-id="cf488-101">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="cf488-101">\<defaultPorts></span></span>
<span data-ttu-id="cf488-102">Raccolta di porte predefinite in cui sono elencati gli endpoint di comunicazione predefiniti sui quali l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="cf488-102">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="cf488-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cf488-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="cf488-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="cf488-104">\<behaviors></span></span>  
<span data-ttu-id="cf488-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="cf488-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="cf488-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="cf488-106">\<behavior></span></span>  
<span data-ttu-id="cf488-107">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="cf488-107">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="cf488-108">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="cf488-108">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf488-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cf488-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cf488-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cf488-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cf488-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cf488-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cf488-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="cf488-112">Attributes</span></span>  
 <span data-ttu-id="cf488-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="cf488-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cf488-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cf488-114">Child Elements</span></span>  
  
|<span data-ttu-id="cf488-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="cf488-115">Element</span></span>|<span data-ttu-id="cf488-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cf488-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cf488-117">\<aggiungere > di \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="cf488-117">\<add> of \<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|<span data-ttu-id="cf488-118">Endpoint di comunicazione predefinito sul quale l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="cf488-118">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cf488-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cf488-119">Parent Elements</span></span>  
  
|<span data-ttu-id="cf488-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="cf488-120">Element</span></span>|<span data-ttu-id="cf488-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cf488-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cf488-122">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="cf488-122">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="cf488-123">Elenco di porte predefinite.</span><span class="sxs-lookup"><span data-stu-id="cf488-123">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cf488-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf488-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
