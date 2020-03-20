---
title: <AttributeImplies>Elemento (.NET native)
ms.date: 03/30/2017
ms.assetid: 82db7193-a860-418b-84fc-fff2fdf2e025
ms.openlocfilehash: 2ab1fdc71bc43f61f69a0d9b7bea7acb35e14ea5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181069"
---
# <a name="attributeimplies-element-net-native"></a><span data-ttu-id="41469-102">\<AttribuToImplies> elemento (.NET nativo)AttributeImplies> Element (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="41469-102">\<AttributeImplies> Element (.NET Native)</span></span>
<span data-ttu-id="41469-103">Definisce i criteri per gli elementi di codice a cui viene applicato l'attributo contenitore.</span><span class="sxs-lookup"><span data-stu-id="41469-103">Defines policy for code elements the containing attribute is applied to.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41469-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="41469-104">Syntax</span></span>  
  
```xml  
<AttributeImplies Activate="policy_type"  
                  Browse="policy_type"  
                  Dynamic="policy_type"  
                  Serialize="policy_type"
                  DataContractSerializer="policy_setting"  
                  DataContractJsonSerializer="policy_setting"  
                  XmlSerializer="policy_setting"  
                  MarshalObject="policy_setting"  
                  MarshalDelegate="policy_setting"  
                  MarshalStructure="policy_setting" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="41469-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="41469-105">Attributes and Elements</span></span>  
 <span data-ttu-id="41469-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="41469-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="41469-107">Attributes</span><span class="sxs-lookup"><span data-stu-id="41469-107">Attributes</span></span>  
  
|<span data-ttu-id="41469-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="41469-108">Attribute</span></span>|<span data-ttu-id="41469-109">Tipo di attributo</span><span class="sxs-lookup"><span data-stu-id="41469-109">Attribute type</span></span>|<span data-ttu-id="41469-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41469-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Activate`|<span data-ttu-id="41469-111">Reflection</span><span class="sxs-lookup"><span data-stu-id="41469-111">Reflection</span></span>|<span data-ttu-id="41469-112">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="41469-112">Optional attribute.</span></span> <span data-ttu-id="41469-113">Controlla l'accesso in fase di esecuzione ai costruttori per abilitare l'attivazione di istanze.</span><span class="sxs-lookup"><span data-stu-id="41469-113">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="41469-114">Reflection</span><span class="sxs-lookup"><span data-stu-id="41469-114">Reflection</span></span>|<span data-ttu-id="41469-115">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="41469-115">Optional attribute.</span></span> <span data-ttu-id="41469-116">Controlla le query per le informazioni sugli elementi di programma, ma non abilita l'accesso in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="41469-116">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="41469-117">Reflection</span><span class="sxs-lookup"><span data-stu-id="41469-117">Reflection</span></span>|<span data-ttu-id="41469-118">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="41469-118">Optional attribute.</span></span> <span data-ttu-id="41469-119">Controlla l'accesso in fase di esecuzione a tutti i membri dei tipi, inclusi costruttori, metodi, campi, proprietà ed eventi, per abilitare la programmazione dinamica.</span><span class="sxs-lookup"><span data-stu-id="41469-119">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="41469-120">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="41469-120">Serialization</span></span>|<span data-ttu-id="41469-121">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="41469-121">Optional attribute.</span></span> <span data-ttu-id="41469-122">Controlla l'accesso in fase di esecuzione a costruttori, campi e proprietà per abilitare la serializzazione e la deserializzazione delle istanze del tipo da parte di librerie quali il serializzatore JSON di Newtonsoft.</span><span class="sxs-lookup"><span data-stu-id="41469-122">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="41469-123">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="41469-123">Serialization</span></span>|<span data-ttu-id="41469-124">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="41469-124">Optional attribute.</span></span> <span data-ttu-id="41469-125">Controlla i criteri per la serializzazione che usano la classe <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="41469-125">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="41469-126">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="41469-126">Serialization</span></span>|<span data-ttu-id="41469-127">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="41469-127">Optional attribute.</span></span> <span data-ttu-id="41469-128">Controlla i criteri per la serializzazione JSON che usano la classe <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="41469-128">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="41469-129">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="41469-129">Serialization</span></span>|<span data-ttu-id="41469-130">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="41469-130">Optional attribute.</span></span> <span data-ttu-id="41469-131">Controlla i criteri per la serializzazione XML che usano la classe <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="41469-131">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="41469-132">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="41469-132">Interop</span></span>|<span data-ttu-id="41469-133">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="41469-133">Optional attribute.</span></span> <span data-ttu-id="41469-134">Controlla i criteri per effettuare il marshalling dei tipi di riferimento a Windows Runtime e COM.</span><span class="sxs-lookup"><span data-stu-id="41469-134">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="41469-135">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="41469-135">Interop</span></span>|<span data-ttu-id="41469-136">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="41469-136">Optional attribute.</span></span> <span data-ttu-id="41469-137">Controlla i criteri per effettuare il marshalling dei tipi delegati come puntatori a funzioni al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="41469-137">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="41469-138">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="41469-138">Interop</span></span>|<span data-ttu-id="41469-139">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="41469-139">Optional attribute.</span></span> <span data-ttu-id="41469-140">Controlla i criteri per il marshalling dei tipi di valore al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="41469-140">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="all-attributes"></a><span data-ttu-id="41469-141">Tutti gli attributi</span><span class="sxs-lookup"><span data-stu-id="41469-141">All attributes</span></span>  
  
|<span data-ttu-id="41469-142">valore</span><span class="sxs-lookup"><span data-stu-id="41469-142">Value</span></span>|<span data-ttu-id="41469-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41469-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="41469-144">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="41469-144">*policy_setting*</span></span>|<span data-ttu-id="41469-145">L'impostazione da applicare a questo tipo di criteri.</span><span class="sxs-lookup"><span data-stu-id="41469-145">The setting to apply to this policy type.</span></span> <span data-ttu-id="41469-146">I valori consentiti sono `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` e `Required All`.</span><span class="sxs-lookup"><span data-stu-id="41469-146">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="41469-147">Per altre informazioni, vedere [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).</span><span class="sxs-lookup"><span data-stu-id="41469-147">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="41469-148">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="41469-148">Child Elements</span></span>  
 <span data-ttu-id="41469-149">No.</span><span class="sxs-lookup"><span data-stu-id="41469-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="41469-150">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="41469-150">Parent Elements</span></span>  
  
|<span data-ttu-id="41469-151">Elemento</span><span class="sxs-lookup"><span data-stu-id="41469-151">Element</span></span>|<span data-ttu-id="41469-152">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41469-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="41469-153">\<Tipo></span><span class="sxs-lookup"><span data-stu-id="41469-153">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="41469-154">Applica i criteri di reflection a un tipo e a tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="41469-154">Applies reflection policy to a type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41469-155">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="41469-155">Remarks</span></span>  
 <span data-ttu-id="41469-156">L'elemento `<AttributeImplies>` viene usato se il relativo tipo contenitore è un attributo (cioè, una classe derivata da <xref:System.Attribute?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="41469-156">The `<AttributeImplies>` element is used if its containing type is an attribute (that is, a class derived from <xref:System.Attribute?displayProperty=nameWithType>).</span></span> <span data-ttu-id="41469-157">Se l'attributo viene applicato a un particolare elemento di programma, il criterio definito dall'elemento `<AttributeImplies>` viene applicato a tale elemento di programma.</span><span class="sxs-lookup"><span data-stu-id="41469-157">If the attribute is applied to a particular program element, the policy defined by the `<AttributeImplies>` element applies to that program element.</span></span>  
  
 <span data-ttu-id="41469-158">Gli attributi di reflection, serializzazione e interoperabilità sono tutti facoltativi, ma è necessario usarne almeno uno.</span><span class="sxs-lookup"><span data-stu-id="41469-158">The reflection, serialization, and interop attributes are all optional, although at least one should be present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41469-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41469-159">See also</span></span>

- [<span data-ttu-id="41469-160">\<Tipo> elemento</span><span class="sxs-lookup"><span data-stu-id="41469-160">\<Type> Element</span></span>](type-element-net-native.md)
- [<span data-ttu-id="41469-161">Riferimento a file di configurazione di direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="41469-161">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="41469-162">Elementi direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="41469-162">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- <span data-ttu-id="41469-163">[Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime)</span><span class="sxs-lookup"><span data-stu-id="41469-163">[Runtime Directive Policy Settings](runtime-directive-policy-settings.md)</span></span>
