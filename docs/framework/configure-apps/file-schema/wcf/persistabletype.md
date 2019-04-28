---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 939a29e90ee21e94ccb78842d6f7224e9a6288d0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783318"
---
# <a name="persistabletype"></a><span data-ttu-id="5a242-101">\<persistableType></span><span class="sxs-lookup"><span data-stu-id="5a242-101">\<persistableType></span></span>
<span data-ttu-id="5a242-102">Specifica tutti i tipi persistenti.</span><span class="sxs-lookup"><span data-stu-id="5a242-102">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="5a242-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5a242-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="5a242-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="5a242-104">\<comContracts></span></span>  
<span data-ttu-id="5a242-105">\<comContract></span><span class="sxs-lookup"><span data-stu-id="5a242-105">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a242-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5a242-106">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="5a242-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="5a242-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a242-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5a242-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5a242-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5a242-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a242-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="5a242-110">Attributes</span></span>  
  
|<span data-ttu-id="5a242-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="5a242-111">Attribute</span></span>|<span data-ttu-id="5a242-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5a242-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5a242-113">ID</span><span class="sxs-lookup"><span data-stu-id="5a242-113">id</span></span>|<span data-ttu-id="5a242-114">Un attributo obbligatorio che contiene una stringa che specifica un identificatore univoco per un tipo persistente.</span><span class="sxs-lookup"><span data-stu-id="5a242-114">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="5a242-115">name</span><span class="sxs-lookup"><span data-stu-id="5a242-115">name</span></span>|<span data-ttu-id="5a242-116">Attributo facoltativo contenente una stringa che specifica il nome del tipo persistente.</span><span class="sxs-lookup"><span data-stu-id="5a242-116">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5a242-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5a242-117">Child Elements</span></span>  
 <span data-ttu-id="5a242-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="5a242-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5a242-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5a242-119">Parent Elements</span></span>  
  
|<span data-ttu-id="5a242-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="5a242-120">Element</span></span>|<span data-ttu-id="5a242-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5a242-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5a242-122">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="5a242-122">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="5a242-123">Raccolta di elementi `persistableType`.</span><span class="sxs-lookup"><span data-stu-id="5a242-123">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5a242-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a242-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [<span data-ttu-id="5a242-125">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="5a242-125">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="5a242-126">Integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="5a242-126">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="5a242-127">Procedura: Configurare le impostazioni di servizio COM+</span><span class="sxs-lookup"><span data-stu-id="5a242-127">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
