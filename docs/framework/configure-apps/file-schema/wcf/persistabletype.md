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
ms.openlocfilehash: 56443902885e191d93897096e55742f7665ba00a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltpersistabletypegt"></a><span data-ttu-id="eb43e-102">&lt;persistableType&gt;</span><span class="sxs-lookup"><span data-stu-id="eb43e-102">&lt;persistableType&gt;</span></span>
<span data-ttu-id="eb43e-103">Specifica tutti i tipi persistenti.</span><span class="sxs-lookup"><span data-stu-id="eb43e-103">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="eb43e-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="eb43e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="eb43e-105">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="eb43e-105">\<comContracts></span></span>  
<span data-ttu-id="eb43e-106">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="eb43e-106">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb43e-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eb43e-107">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="eb43e-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="eb43e-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb43e-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="eb43e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="eb43e-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="eb43e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb43e-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="eb43e-111">Attributes</span></span>  
  
|<span data-ttu-id="eb43e-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="eb43e-112">Attribute</span></span>|<span data-ttu-id="eb43e-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eb43e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eb43e-114">id</span><span class="sxs-lookup"><span data-stu-id="eb43e-114">id</span></span>|<span data-ttu-id="eb43e-115">Un attributo obbligatorio che contiene una stringa che specifica un identificatore univoco per un tipo persistente.</span><span class="sxs-lookup"><span data-stu-id="eb43e-115">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="eb43e-116">name</span><span class="sxs-lookup"><span data-stu-id="eb43e-116">name</span></span>|<span data-ttu-id="eb43e-117">Attributo facoltativo contenente una stringa che specifica il nome del tipo persistente.</span><span class="sxs-lookup"><span data-stu-id="eb43e-117">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eb43e-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="eb43e-118">Child Elements</span></span>  
 <span data-ttu-id="eb43e-119">None</span><span class="sxs-lookup"><span data-stu-id="eb43e-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eb43e-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="eb43e-120">Parent Elements</span></span>  
  
|<span data-ttu-id="eb43e-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="eb43e-121">Element</span></span>|<span data-ttu-id="eb43e-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eb43e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb43e-123">\<persistableTypes ></span><span class="sxs-lookup"><span data-stu-id="eb43e-123">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="eb43e-124">Raccolta di elementi `persistableType`.</span><span class="sxs-lookup"><span data-stu-id="eb43e-124">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eb43e-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb43e-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>  
 [<span data-ttu-id="eb43e-126">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="eb43e-126">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="eb43e-127">L'integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="eb43e-127">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="eb43e-128">Procedura: configurare le impostazioni di servizio COM+</span><span class="sxs-lookup"><span data-stu-id="eb43e-128">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
