---
title: <Parameter>Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: 22aaa1f3-596f-4733-93db-f4bcabcb5240
ms.openlocfilehash: c6dfc347d44a794ee8496c45ca879f9daab12b22
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128191"
---
# <a name="parameter-element-net-native"></a><span data-ttu-id="7e6fc-102">\<Parameter>Elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="7e6fc-102">\<Parameter> Element (.NET Native)</span></span>
<span data-ttu-id="7e6fc-103">Applica criteri di reflection al tipo di argomento passato a un metodo.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-103">Applies reflection policy to the type of the argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e6fc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7e6fc-104">Syntax</span></span>  
  
```xml  
<Parameter Name="parameter_name"  
           Activate="policy_type"  
           Browse="policy_type"  
           Dynamic="policy_type"  
           Serialize="policy_type"  
           DataContractSerializer="policy_type"  
           DataContractJsonSerializer="policy_type"  
           XmlSerializer="policy_type"  
           MarshalObject="policy_type"  
           MarshalDelegate="policy_type"  
           MarshalStructure="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e6fc-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7e6fc-105">Attributes and Elements</span></span>  
 <span data-ttu-id="7e6fc-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e6fc-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="7e6fc-107">Attributes</span></span>  
  
|<span data-ttu-id="7e6fc-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="7e6fc-108">Attribute</span></span>|<span data-ttu-id="7e6fc-109">Tipo di attributo</span><span class="sxs-lookup"><span data-stu-id="7e6fc-109">Attribute type</span></span>|<span data-ttu-id="7e6fc-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e6fc-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="7e6fc-111">Generale</span><span class="sxs-lookup"><span data-stu-id="7e6fc-111">General</span></span>|<span data-ttu-id="7e6fc-112">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-112">Required attribute.</span></span> <span data-ttu-id="7e6fc-113">Nome del parametro.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-113">The parameter name.</span></span> <span data-ttu-id="7e6fc-114">Ad esempio, per la firma del metodo `String.CompareTo(Object value)`, il valore dell'attributo `Name` è "value".</span><span class="sxs-lookup"><span data-stu-id="7e6fc-114">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
|`Activate`|<span data-ttu-id="7e6fc-115">Reflection</span><span class="sxs-lookup"><span data-stu-id="7e6fc-115">Reflection</span></span>|<span data-ttu-id="7e6fc-116">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-116">Optional attribute.</span></span> <span data-ttu-id="7e6fc-117">Controlla l'accesso in fase di esecuzione ai costruttori per abilitare l'attivazione di istanze.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="7e6fc-118">Reflection</span><span class="sxs-lookup"><span data-stu-id="7e6fc-118">Reflection</span></span>|<span data-ttu-id="7e6fc-119">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-119">Optional attribute.</span></span> <span data-ttu-id="7e6fc-120">Controlla le query per le informazioni sugli elementi di programma, ma non abilita l'accesso in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="7e6fc-121">Reflection</span><span class="sxs-lookup"><span data-stu-id="7e6fc-121">Reflection</span></span>|<span data-ttu-id="7e6fc-122">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-122">Optional attribute.</span></span> <span data-ttu-id="7e6fc-123">Controlla l'accesso in fase di esecuzione a tutti i membri dei tipi, inclusi costruttori, metodi, campi, proprietà ed eventi, per abilitare la programmazione dinamica.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="7e6fc-124">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="7e6fc-124">Serialization</span></span>|<span data-ttu-id="7e6fc-125">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-125">Optional attribute.</span></span> <span data-ttu-id="7e6fc-126">Controlla l'accesso in fase di esecuzione a costruttori, campi e proprietà per abilitare la serializzazione e la deserializzazione delle istanze del tipo da parte di librerie quali il serializzatore JSON di Newtonsoft.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="7e6fc-127">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="7e6fc-127">Serialization</span></span>|<span data-ttu-id="7e6fc-128">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-128">Optional attribute.</span></span> <span data-ttu-id="7e6fc-129">Controlla i criteri per la serializzazione che usano la classe <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="7e6fc-130">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="7e6fc-130">Serialization</span></span>|<span data-ttu-id="7e6fc-131">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-131">Optional attribute.</span></span> <span data-ttu-id="7e6fc-132">Controlla i criteri per la serializzazione JSON che usano la classe <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="7e6fc-133">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="7e6fc-133">Serialization</span></span>|<span data-ttu-id="7e6fc-134">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-134">Optional attribute.</span></span> <span data-ttu-id="7e6fc-135">Controlla i criteri per la serializzazione XML che usano la classe <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="7e6fc-136">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="7e6fc-136">Interop</span></span>|<span data-ttu-id="7e6fc-137">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-137">Optional attribute.</span></span> <span data-ttu-id="7e6fc-138">Criteri di controlli per effettuare il marshalling dei tipi di riferimento per WinRT e COM.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-138">Controls policy for marshaling reference types to WinRT and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="7e6fc-139">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="7e6fc-139">Interop</span></span>|<span data-ttu-id="7e6fc-140">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-140">Optional attribute.</span></span> <span data-ttu-id="7e6fc-141">Controlla i criteri per effettuare il marshalling dei tipi delegati come puntatori a funzioni al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="7e6fc-142">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="7e6fc-142">Interop</span></span>|<span data-ttu-id="7e6fc-143">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-143">Optional attribute.</span></span> <span data-ttu-id="7e6fc-144">Controlla i criteri per il marshalling dei tipi di valore al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="7e6fc-145">Name (attributo)</span><span class="sxs-lookup"><span data-stu-id="7e6fc-145">Name attribute</span></span>  
  
|<span data-ttu-id="7e6fc-146">Valore</span><span class="sxs-lookup"><span data-stu-id="7e6fc-146">Value</span></span>|<span data-ttu-id="7e6fc-147">Description</span><span class="sxs-lookup"><span data-stu-id="7e6fc-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7e6fc-148">*parameter_name*</span><span class="sxs-lookup"><span data-stu-id="7e6fc-148">*parameter_name*</span></span>|<span data-ttu-id="7e6fc-149">Il nome del parametro del metodo a cui è applicato il criterio.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-149">The name of the method parameter to which policy is applied.</span></span> <span data-ttu-id="7e6fc-150">Ad esempio, per la firma del metodo `String.CompareTo(Object value)`, il valore dell'attributo `Name` è "value".</span><span class="sxs-lookup"><span data-stu-id="7e6fc-150">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="7e6fc-151">Tutti gli altri attributi</span><span class="sxs-lookup"><span data-stu-id="7e6fc-151">All other attributes</span></span>  
  
|<span data-ttu-id="7e6fc-152">Valore</span><span class="sxs-lookup"><span data-stu-id="7e6fc-152">Value</span></span>|<span data-ttu-id="7e6fc-153">Description</span><span class="sxs-lookup"><span data-stu-id="7e6fc-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7e6fc-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="7e6fc-154">*policy_setting*</span></span>|<span data-ttu-id="7e6fc-155">L'impostazione da applicare a questo tipo di criteri.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="7e6fc-156">I valori consentiti sono `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` e `Required All`.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="7e6fc-157">Per altre informazioni, vedere [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).</span><span class="sxs-lookup"><span data-stu-id="7e6fc-157">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e6fc-158">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7e6fc-158">Child Elements</span></span>  
 <span data-ttu-id="7e6fc-159">No.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7e6fc-160">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7e6fc-160">Parent Elements</span></span>  
  
|<span data-ttu-id="7e6fc-161">Elemento</span><span class="sxs-lookup"><span data-stu-id="7e6fc-161">Element</span></span>|<span data-ttu-id="7e6fc-162">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e6fc-162">Description</span></span>|  
|-------------|-----------------|  
|[\<Method>](method-element-net-native.md)|<span data-ttu-id="7e6fc-163">Applica i criteri di reflection di runtime a un costruttore o a un metodo.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-163">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e6fc-164">Commenti</span><span class="sxs-lookup"><span data-stu-id="7e6fc-164">Remarks</span></span>  
 <span data-ttu-id="7e6fc-165">L' `<Parameter>` elemento è figlio dell' [\<Method>](method-element-net-native.md) elemento e viene usato per applicare i criteri a un determinato parametro del metodo.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-165">The `<Parameter>` element is a child of the [\<Method>](method-element-net-native.md) element and is used to apply policy to a particular method parameter.</span></span> <span data-ttu-id="7e6fc-166">Il parametro del metodo specifico viene specificato per nome anziché in base al tipo.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-166">The specific method parameter is specified by name rather than by type.</span></span> <span data-ttu-id="7e6fc-167">Almeno un attributo che rappresenta un tipo di criterio, ad esempio `Activate` o `Dynamic`, deve essere presente.</span><span class="sxs-lookup"><span data-stu-id="7e6fc-167">At least one attribute that represents a policy type, such as `Activate` or `Dynamic`, must be present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e6fc-168">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="7e6fc-168">See also</span></span>

- [<span data-ttu-id="7e6fc-169">\<Method>Elemento</span><span class="sxs-lookup"><span data-stu-id="7e6fc-169">\<Method> Element</span></span>](method-element-net-native.md)
- [<span data-ttu-id="7e6fc-170">Riferimento a file di configurazione di direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="7e6fc-170">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="7e6fc-171">Impostazioni dei criteri della direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="7e6fc-171">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="7e6fc-172">Elementi direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="7e6fc-172">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
