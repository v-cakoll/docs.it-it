---
title: '&lt;persistableType&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a3064727eeda30c05f38558f4f0977c71e5abb48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltpersistabletypegt"></a><span data-ttu-id="e9d52-102">&lt;persistableType&gt;</span><span class="sxs-lookup"><span data-stu-id="e9d52-102">&lt;persistableType&gt;</span></span>
<span data-ttu-id="e9d52-103">Specifica tutti i tipi persistenti.</span><span class="sxs-lookup"><span data-stu-id="e9d52-103">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="e9d52-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e9d52-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e9d52-105">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="e9d52-105">\<comContracts></span></span>  
<span data-ttu-id="e9d52-106">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="e9d52-106">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9d52-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9d52-107">Syntax</span></span>  
  
```xml  
<comContracts>  
  <comContract>  
      <persistableTypes>  
         <persistableType id="string"  
            name="string">  
         </persistableType>  
      </persistableTypes>  
  </comContract>  
</comContracts>  
```  
  
## <a name="type"></a><span data-ttu-id="e9d52-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="e9d52-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9d52-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e9d52-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e9d52-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e9d52-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9d52-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="e9d52-111">Attributes</span></span>  
  
|<span data-ttu-id="e9d52-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="e9d52-112">Attribute</span></span>|<span data-ttu-id="e9d52-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9d52-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e9d52-114">id</span><span class="sxs-lookup"><span data-stu-id="e9d52-114">id</span></span>|<span data-ttu-id="e9d52-115">Un attributo obbligatorio che contiene una stringa che specifica un identificatore univoco per un tipo persistente.</span><span class="sxs-lookup"><span data-stu-id="e9d52-115">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="e9d52-116">name</span><span class="sxs-lookup"><span data-stu-id="e9d52-116">name</span></span>|<span data-ttu-id="e9d52-117">Attributo facoltativo contenente una stringa che specifica il nome del tipo persistente.</span><span class="sxs-lookup"><span data-stu-id="e9d52-117">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9d52-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e9d52-118">Child Elements</span></span>  
 <span data-ttu-id="e9d52-119">None</span><span class="sxs-lookup"><span data-stu-id="e9d52-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9d52-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e9d52-120">Parent Elements</span></span>  
  
|<span data-ttu-id="e9d52-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="e9d52-121">Element</span></span>|<span data-ttu-id="e9d52-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9d52-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9d52-123">\<persistableTypes ></span><span class="sxs-lookup"><span data-stu-id="e9d52-123">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="e9d52-124">Raccolta di elementi `persistableType`.</span><span class="sxs-lookup"><span data-stu-id="e9d52-124">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e9d52-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9d52-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>  
 [<span data-ttu-id="e9d52-126">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="e9d52-126">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="e9d52-127">Integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="e9d52-127">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="e9d52-128">Procedura: Configurare le impostazioni del servizio COM+</span><span class="sxs-lookup"><span data-stu-id="e9d52-128">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
