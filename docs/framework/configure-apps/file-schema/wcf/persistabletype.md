---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 3ea99d360ceb1e3fe6e97cbf9c8827dd7c853f63
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55256524"
---
# <a name="persistabletype"></a><span data-ttu-id="3f526-101">\<persistableType></span><span class="sxs-lookup"><span data-stu-id="3f526-101">\<persistableType></span></span>
<span data-ttu-id="3f526-102">Specifica tutti i tipi persistenti.</span><span class="sxs-lookup"><span data-stu-id="3f526-102">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="3f526-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3f526-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="3f526-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="3f526-104">\<comContracts></span></span>  
<span data-ttu-id="3f526-105">\<comContract></span><span class="sxs-lookup"><span data-stu-id="3f526-105">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f526-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3f526-106">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="3f526-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="3f526-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3f526-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3f526-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3f526-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3f526-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3f526-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="3f526-110">Attributes</span></span>  
  
|<span data-ttu-id="3f526-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="3f526-111">Attribute</span></span>|<span data-ttu-id="3f526-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3f526-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3f526-113">id</span><span class="sxs-lookup"><span data-stu-id="3f526-113">id</span></span>|<span data-ttu-id="3f526-114">Un attributo obbligatorio che contiene una stringa che specifica un identificatore univoco per un tipo persistente.</span><span class="sxs-lookup"><span data-stu-id="3f526-114">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="3f526-115">name</span><span class="sxs-lookup"><span data-stu-id="3f526-115">name</span></span>|<span data-ttu-id="3f526-116">Attributo facoltativo contenente una stringa che specifica il nome del tipo persistente.</span><span class="sxs-lookup"><span data-stu-id="3f526-116">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3f526-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3f526-117">Child Elements</span></span>  
 <span data-ttu-id="3f526-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="3f526-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3f526-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3f526-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3f526-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="3f526-120">Element</span></span>|<span data-ttu-id="3f526-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3f526-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3f526-122">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="3f526-122">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="3f526-123">Raccolta di elementi `persistableType`.</span><span class="sxs-lookup"><span data-stu-id="3f526-123">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3f526-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f526-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [<span data-ttu-id="3f526-125">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="3f526-125">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="3f526-126">Integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="3f526-126">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="3f526-127">Procedura: Configurare le impostazioni di servizio COM+</span><span class="sxs-lookup"><span data-stu-id="3f526-127">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
