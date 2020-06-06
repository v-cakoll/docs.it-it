---
title: <Event>Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: e53b029c-9d6d-4c0a-9cdc-5cfca8a5ca47
ms.openlocfilehash: 60da48d5872d7ce61afcffa7977411bc6e1efc7f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79181033"
---
# <a name="event-element-net-native"></a><span data-ttu-id="14e87-102">\<Event>Elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="14e87-102">\<Event> Element (.NET Native)</span></span>
<span data-ttu-id="14e87-103">Applica i criteri di reflection di runtime a un evento.</span><span class="sxs-lookup"><span data-stu-id="14e87-103">Applies runtime reflection policy to an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14e87-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="14e87-104">Syntax</span></span>  
  
```xml  
<Event Name="event_name"
       Browse="policy_type"
       Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14e87-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="14e87-105">Attributes and Elements</span></span>  
 <span data-ttu-id="14e87-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="14e87-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14e87-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="14e87-107">Attributes</span></span>  
  
|<span data-ttu-id="14e87-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="14e87-108">Attribute</span></span>|<span data-ttu-id="14e87-109">Tipo di attributo</span><span class="sxs-lookup"><span data-stu-id="14e87-109">Attribute type</span></span>|<span data-ttu-id="14e87-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="14e87-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="14e87-111">Generale</span><span class="sxs-lookup"><span data-stu-id="14e87-111">General</span></span>|<span data-ttu-id="14e87-112">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="14e87-112">Required attribute.</span></span> <span data-ttu-id="14e87-113">Specifica il nome dell'evento.</span><span class="sxs-lookup"><span data-stu-id="14e87-113">Specifies the event name.</span></span>|  
|`Browse`|<span data-ttu-id="14e87-114">Reflection</span><span class="sxs-lookup"><span data-stu-id="14e87-114">Reflection</span></span>|<span data-ttu-id="14e87-115">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="14e87-115">Optional attribute.</span></span> <span data-ttu-id="14e87-116">Controlla le query per le informazioni o per l'enumerazione dell'evento, ma non abilita l'accesso dinamico al runtime.</span><span class="sxs-lookup"><span data-stu-id="14e87-116">Controls querying for information about or enumerating the event but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="14e87-117">Reflection</span><span class="sxs-lookup"><span data-stu-id="14e87-117">Reflection</span></span>|<span data-ttu-id="14e87-118">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="14e87-118">Optional attribute.</span></span> <span data-ttu-id="14e87-119">Controlla l'accesso in fase di esecuzione all'evento per abilitare la programmazione dinamica.</span><span class="sxs-lookup"><span data-stu-id="14e87-119">Controls runtime access to the event to enable dynamic programming.</span></span> <span data-ttu-id="14e87-120">Questi criteri assicurano la gestione dinamica di un evento al runtime.</span><span class="sxs-lookup"><span data-stu-id="14e87-120">This policy ensures that an event can be handled dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="14e87-121">Name (attributo)</span><span class="sxs-lookup"><span data-stu-id="14e87-121">Name attribute</span></span>  
  
|<span data-ttu-id="14e87-122">Valore</span><span class="sxs-lookup"><span data-stu-id="14e87-122">Value</span></span>|<span data-ttu-id="14e87-123">Description</span><span class="sxs-lookup"><span data-stu-id="14e87-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="14e87-124">*method_name*</span><span class="sxs-lookup"><span data-stu-id="14e87-124">*method_name*</span></span>|<span data-ttu-id="14e87-125">Nome dell'evento.</span><span class="sxs-lookup"><span data-stu-id="14e87-125">The event name.</span></span> <span data-ttu-id="14e87-126">Il tipo dell'evento viene definito dall' [\<Type>](type-element-net-native.md) elemento padre o [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="14e87-126">The type of the event is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="14e87-127">Tutti gli altri attributi</span><span class="sxs-lookup"><span data-stu-id="14e87-127">All other attributes</span></span>  
  
|<span data-ttu-id="14e87-128">Valore</span><span class="sxs-lookup"><span data-stu-id="14e87-128">Value</span></span>|<span data-ttu-id="14e87-129">Description</span><span class="sxs-lookup"><span data-stu-id="14e87-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="14e87-130">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="14e87-130">*policy_setting*</span></span>|<span data-ttu-id="14e87-131">L'impostazione da applicare a questo tipo di criteri per l'evento.</span><span class="sxs-lookup"><span data-stu-id="14e87-131">The setting to apply to this policy type for the event.</span></span> <span data-ttu-id="14e87-132">I valori consentiti sono `Auto`, `Excluded`, `Included` e `Required`.</span><span class="sxs-lookup"><span data-stu-id="14e87-132">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="14e87-133">Per altre informazioni, vedere [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).</span><span class="sxs-lookup"><span data-stu-id="14e87-133">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14e87-134">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="14e87-134">Child Elements</span></span>  
 <span data-ttu-id="14e87-135">No.</span><span class="sxs-lookup"><span data-stu-id="14e87-135">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="14e87-136">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="14e87-136">Parent Elements</span></span>  
  
|<span data-ttu-id="14e87-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="14e87-137">Element</span></span>|<span data-ttu-id="14e87-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="14e87-138">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="14e87-139">Applica i criteri di reflection a un tipo e a tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="14e87-139">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="14e87-140">Applica i criteri di reflection a un tipo generico costruito e a tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="14e87-140">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14e87-141">Commenti</span><span class="sxs-lookup"><span data-stu-id="14e87-141">Remarks</span></span>  
 <span data-ttu-id="14e87-142">Se i criteri di un evento non sono definiti esplicitamente, l'evento eredita i criteri di runtime dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="14e87-142">If an event's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14e87-143">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="14e87-143">See also</span></span>

- [<span data-ttu-id="14e87-144">Riferimento a file di configurazione di direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="14e87-144">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="14e87-145">Elementi direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="14e87-145">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="14e87-146">Impostazioni dei criteri della direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="14e87-146">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
