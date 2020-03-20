---
title: <Event>Elemento (.NET native)
ms.date: 03/30/2017
ms.assetid: e53b029c-9d6d-4c0a-9cdc-5cfca8a5ca47
ms.openlocfilehash: 60da48d5872d7ce61afcffa7977411bc6e1efc7f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181033"
---
# <a name="event-element-net-native"></a><span data-ttu-id="00d0c-102">\<Elemento> eventi (.NET Native)Event> Element (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="00d0c-102">\<Event> Element (.NET Native)</span></span>
<span data-ttu-id="00d0c-103">Applica i criteri di reflection di runtime a un evento.</span><span class="sxs-lookup"><span data-stu-id="00d0c-103">Applies runtime reflection policy to an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00d0c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="00d0c-104">Syntax</span></span>  
  
```xml  
<Event Name="event_name"
       Browse="policy_type"
       Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00d0c-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="00d0c-105">Attributes and Elements</span></span>  
 <span data-ttu-id="00d0c-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="00d0c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00d0c-107">Attributes</span><span class="sxs-lookup"><span data-stu-id="00d0c-107">Attributes</span></span>  
  
|<span data-ttu-id="00d0c-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="00d0c-108">Attribute</span></span>|<span data-ttu-id="00d0c-109">Tipo di attributo</span><span class="sxs-lookup"><span data-stu-id="00d0c-109">Attribute type</span></span>|<span data-ttu-id="00d0c-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="00d0c-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="00d0c-111">Generale</span><span class="sxs-lookup"><span data-stu-id="00d0c-111">General</span></span>|<span data-ttu-id="00d0c-112">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="00d0c-112">Required attribute.</span></span> <span data-ttu-id="00d0c-113">Specifica il nome dell'evento.</span><span class="sxs-lookup"><span data-stu-id="00d0c-113">Specifies the event name.</span></span>|  
|`Browse`|<span data-ttu-id="00d0c-114">Reflection</span><span class="sxs-lookup"><span data-stu-id="00d0c-114">Reflection</span></span>|<span data-ttu-id="00d0c-115">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="00d0c-115">Optional attribute.</span></span> <span data-ttu-id="00d0c-116">Controlla le query per le informazioni o per l'enumerazione dell'evento, ma non abilita l'accesso dinamico al runtime.</span><span class="sxs-lookup"><span data-stu-id="00d0c-116">Controls querying for information about or enumerating the event but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="00d0c-117">Reflection</span><span class="sxs-lookup"><span data-stu-id="00d0c-117">Reflection</span></span>|<span data-ttu-id="00d0c-118">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="00d0c-118">Optional attribute.</span></span> <span data-ttu-id="00d0c-119">Controlla l'accesso in fase di esecuzione all'evento per abilitare la programmazione dinamica.</span><span class="sxs-lookup"><span data-stu-id="00d0c-119">Controls runtime access to the event to enable dynamic programming.</span></span> <span data-ttu-id="00d0c-120">Questi criteri assicurano la gestione dinamica di un evento al runtime.</span><span class="sxs-lookup"><span data-stu-id="00d0c-120">This policy ensures that an event can be handled dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="00d0c-121">Name (attributo)</span><span class="sxs-lookup"><span data-stu-id="00d0c-121">Name attribute</span></span>  
  
|<span data-ttu-id="00d0c-122">valore</span><span class="sxs-lookup"><span data-stu-id="00d0c-122">Value</span></span>|<span data-ttu-id="00d0c-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="00d0c-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="00d0c-124">*method_name*</span><span class="sxs-lookup"><span data-stu-id="00d0c-124">*method_name*</span></span>|<span data-ttu-id="00d0c-125">Nome dell'evento.</span><span class="sxs-lookup"><span data-stu-id="00d0c-125">The event name.</span></span> <span data-ttu-id="00d0c-126">Il tipo dell'evento è definito dall'elemento [ \<>type](type-element-net-native.md) o [ \<TypeInstanti>ation](typeinstantiation-element-net-native.md) padre.</span><span class="sxs-lookup"><span data-stu-id="00d0c-126">The type of the event is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="00d0c-127">Tutti gli altri attributi</span><span class="sxs-lookup"><span data-stu-id="00d0c-127">All other attributes</span></span>  
  
|<span data-ttu-id="00d0c-128">valore</span><span class="sxs-lookup"><span data-stu-id="00d0c-128">Value</span></span>|<span data-ttu-id="00d0c-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="00d0c-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="00d0c-130">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="00d0c-130">*policy_setting*</span></span>|<span data-ttu-id="00d0c-131">L'impostazione da applicare a questo tipo di criteri per l'evento.</span><span class="sxs-lookup"><span data-stu-id="00d0c-131">The setting to apply to this policy type for the event.</span></span> <span data-ttu-id="00d0c-132">I valori consentiti sono `Auto`, `Excluded`, `Included` e `Required`.</span><span class="sxs-lookup"><span data-stu-id="00d0c-132">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="00d0c-133">Per altre informazioni, vedere [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).</span><span class="sxs-lookup"><span data-stu-id="00d0c-133">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="00d0c-134">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="00d0c-134">Child Elements</span></span>  
 <span data-ttu-id="00d0c-135">No.</span><span class="sxs-lookup"><span data-stu-id="00d0c-135">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="00d0c-136">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="00d0c-136">Parent Elements</span></span>  
  
|<span data-ttu-id="00d0c-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="00d0c-137">Element</span></span>|<span data-ttu-id="00d0c-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="00d0c-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00d0c-139">\<Tipo></span><span class="sxs-lookup"><span data-stu-id="00d0c-139">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="00d0c-140">Applica i criteri di reflection a un tipo e a tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="00d0c-140">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="00d0c-141">\<>TypeInstantiation</span><span class="sxs-lookup"><span data-stu-id="00d0c-141">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)|<span data-ttu-id="00d0c-142">Applica i criteri di reflection a un tipo generico costruito e a tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="00d0c-142">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00d0c-143">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="00d0c-143">Remarks</span></span>  
 <span data-ttu-id="00d0c-144">Se i criteri di un evento non sono definiti esplicitamente, l'evento eredita i criteri di runtime dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="00d0c-144">If an event's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00d0c-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00d0c-145">See also</span></span>

- [<span data-ttu-id="00d0c-146">Riferimento a file di configurazione di direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="00d0c-146">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="00d0c-147">Elementi direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="00d0c-147">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- <span data-ttu-id="00d0c-148">[Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime)</span><span class="sxs-lookup"><span data-stu-id="00d0c-148">[Runtime Directive Policy Settings](runtime-directive-policy-settings.md)</span></span>
