---
title: '&lt;persistableType&gt;'
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: b9d61a736a2f8650c543433931d57e156d115018
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706852"
---
# <a name="ltpersistabletypegt"></a><span data-ttu-id="61d1d-102">&lt;persistableType&gt;</span><span class="sxs-lookup"><span data-stu-id="61d1d-102">&lt;persistableType&gt;</span></span>
<span data-ttu-id="61d1d-103">Specifica tutti i tipi persistenti.</span><span class="sxs-lookup"><span data-stu-id="61d1d-103">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="61d1d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="61d1d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="61d1d-105">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="61d1d-105">\<comContracts></span></span>  
<span data-ttu-id="61d1d-106">\<comContract></span><span class="sxs-lookup"><span data-stu-id="61d1d-106">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61d1d-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="61d1d-107">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <persistableTypes>
      <persistableType id="String"
                       name="String">
      </persistableType>
    </persistableTypes>
  </comContract>
</comContracts>
```  
  
## <a name="type"></a><span data-ttu-id="61d1d-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="61d1d-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61d1d-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="61d1d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="61d1d-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="61d1d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61d1d-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="61d1d-111">Attributes</span></span>  
  
|<span data-ttu-id="61d1d-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="61d1d-112">Attribute</span></span>|<span data-ttu-id="61d1d-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61d1d-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="61d1d-114">id</span><span class="sxs-lookup"><span data-stu-id="61d1d-114">id</span></span>|<span data-ttu-id="61d1d-115">Un attributo obbligatorio che contiene una stringa che specifica un identificatore univoco per un tipo persistente.</span><span class="sxs-lookup"><span data-stu-id="61d1d-115">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="61d1d-116">name</span><span class="sxs-lookup"><span data-stu-id="61d1d-116">name</span></span>|<span data-ttu-id="61d1d-117">Attributo facoltativo contenente una stringa che specifica il nome del tipo persistente.</span><span class="sxs-lookup"><span data-stu-id="61d1d-117">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="61d1d-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="61d1d-118">Child Elements</span></span>  
 <span data-ttu-id="61d1d-119">nessuno</span><span class="sxs-lookup"><span data-stu-id="61d1d-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="61d1d-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="61d1d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="61d1d-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="61d1d-121">Element</span></span>|<span data-ttu-id="61d1d-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61d1d-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="61d1d-123">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="61d1d-123">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="61d1d-124">Raccolta di elementi `persistableType`.</span><span class="sxs-lookup"><span data-stu-id="61d1d-124">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="61d1d-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61d1d-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [<span data-ttu-id="61d1d-126">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="61d1d-126">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="61d1d-127">Integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="61d1d-127">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="61d1d-128">Procedura: Configurare le impostazioni di servizio COM+</span><span class="sxs-lookup"><span data-stu-id="61d1d-128">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
