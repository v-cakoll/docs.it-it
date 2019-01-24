---
title: Elemento &lt;ImpliesType&gt; (.NET Native)
ms.date: 03/30/2017
ms.assetid: 3abd2071-0f28-40ba-b9a0-d52bd94cd2f6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe590022f1354b3a41c709e4fed30f89e865fa0c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54548050"
---
# <a name="ltimpliestypegt-element-net-native"></a><span data-ttu-id="fd21d-102">Elemento &lt;ImpliesType&gt; (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="fd21d-102">&lt;ImpliesType&gt; Element (.NET Native)</span></span>
<span data-ttu-id="fd21d-103">Applica criteri a un tipo, se tale criterio è stato applicato al metodo o al tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="fd21d-103">Applies policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd21d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fd21d-104">Syntax</span></span>  
  
```xml
<ImpliesType Name="type_name"  
             Activate="policy_type"  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd21d-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fd21d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="fd21d-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fd21d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd21d-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="fd21d-107">Attributes</span></span>  
  
|<span data-ttu-id="fd21d-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="fd21d-108">Attribute</span></span>|<span data-ttu-id="fd21d-109">Tipo di attributo</span><span class="sxs-lookup"><span data-stu-id="fd21d-109">Attribute type</span></span>|<span data-ttu-id="fd21d-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd21d-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="fd21d-111">Generale</span><span class="sxs-lookup"><span data-stu-id="fd21d-111">General</span></span>|<span data-ttu-id="fd21d-112">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fd21d-112">Required attribute.</span></span> <span data-ttu-id="fd21d-113">Specifica il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="fd21d-113">Specifies the type name.</span></span>|  
|`Activate`|<span data-ttu-id="fd21d-114">Reflection</span><span class="sxs-lookup"><span data-stu-id="fd21d-114">Reflection</span></span>|<span data-ttu-id="fd21d-115">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="fd21d-115">Optional attribute.</span></span> <span data-ttu-id="fd21d-116">Controlla l'accesso in fase di esecuzione ai costruttori per abilitare l'attivazione di istanze.</span><span class="sxs-lookup"><span data-stu-id="fd21d-116">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="fd21d-117">Reflection</span><span class="sxs-lookup"><span data-stu-id="fd21d-117">Reflection</span></span>|<span data-ttu-id="fd21d-118">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="fd21d-118">Optional attribute.</span></span> <span data-ttu-id="fd21d-119">Controlla le query per le informazioni sugli elementi di programma, ma non abilita l'accesso in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fd21d-119">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="fd21d-120">Reflection</span><span class="sxs-lookup"><span data-stu-id="fd21d-120">Reflection</span></span>|<span data-ttu-id="fd21d-121">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="fd21d-121">Optional attribute.</span></span> <span data-ttu-id="fd21d-122">Controlla l'accesso in fase di esecuzione a tutti i membri dei tipi, inclusi costruttori, metodi, campi, proprietà ed eventi, per abilitare la programmazione dinamica.</span><span class="sxs-lookup"><span data-stu-id="fd21d-122">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="fd21d-123">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="fd21d-123">Serialization</span></span>|<span data-ttu-id="fd21d-124">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="fd21d-124">Optional attribute.</span></span> <span data-ttu-id="fd21d-125">Controlla l'accesso in fase di esecuzione a costruttori, campi e proprietà per abilitare la serializzazione e la deserializzazione delle istanze del tipo da parte di librerie quali il serializzatore JSON di Newtonsoft.</span><span class="sxs-lookup"><span data-stu-id="fd21d-125">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="fd21d-126">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="fd21d-126">Serialization</span></span>|<span data-ttu-id="fd21d-127">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="fd21d-127">Optional attribute.</span></span> <span data-ttu-id="fd21d-128">Controlla i criteri per la serializzazione che usano la classe <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fd21d-128">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="fd21d-129">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="fd21d-129">Serialization</span></span>|<span data-ttu-id="fd21d-130">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="fd21d-130">Optional attribute.</span></span> <span data-ttu-id="fd21d-131">Controlla i criteri per la serializzazione JSON che usano la classe <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fd21d-131">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="fd21d-132">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="fd21d-132">Serialization</span></span>|<span data-ttu-id="fd21d-133">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="fd21d-133">Optional attribute.</span></span> <span data-ttu-id="fd21d-134">Controlla i criteri per la serializzazione XML che usano la classe <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fd21d-134">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="fd21d-135">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="fd21d-135">Interop</span></span>|<span data-ttu-id="fd21d-136">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="fd21d-136">Optional attribute.</span></span> <span data-ttu-id="fd21d-137">Controlla i criteri per effettuare il marshalling dei tipi di riferimento a Windows Runtime e COM.</span><span class="sxs-lookup"><span data-stu-id="fd21d-137">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="fd21d-138">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="fd21d-138">Interop</span></span>|<span data-ttu-id="fd21d-139">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="fd21d-139">Optional attribute.</span></span> <span data-ttu-id="fd21d-140">Controlla i criteri per effettuare il marshalling dei tipi delegati come puntatori a funzioni al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="fd21d-140">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="fd21d-141">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="fd21d-141">Interop</span></span>|<span data-ttu-id="fd21d-142">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="fd21d-142">Optional attribute.</span></span> <span data-ttu-id="fd21d-143">Controlla i criteri per il marshalling dei tipi di valore al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="fd21d-143">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="fd21d-144">Name (attributo)</span><span class="sxs-lookup"><span data-stu-id="fd21d-144">Name attribute</span></span>  
  
|<span data-ttu-id="fd21d-145">Valore</span><span class="sxs-lookup"><span data-stu-id="fd21d-145">Value</span></span>|<span data-ttu-id="fd21d-146">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd21d-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fd21d-147">*type_name*</span><span class="sxs-lookup"><span data-stu-id="fd21d-147">*type_name*</span></span>|<span data-ttu-id="fd21d-148">Nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="fd21d-148">The type name.</span></span> <span data-ttu-id="fd21d-149">Se il tipo rappresentato da questo elemento `<ImpliesType>` si trova nello stesso spazio dei nomi dell'elemento `<Type>` contenitore, *type_name* può includere il nome del tipo senza lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="fd21d-149">If the type represented by this `<ImpliesType>` element is located in the same namespace as its containing `<Type>` element, *type_name* can include the name of the type without its namespace.</span></span> <span data-ttu-id="fd21d-150">In caso contrario, *type_name* deve includere il nome completo del tipo.</span><span class="sxs-lookup"><span data-stu-id="fd21d-150">Otherwise, *type_name* must include the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="fd21d-151">Tutti gli altri attributi</span><span class="sxs-lookup"><span data-stu-id="fd21d-151">All other attributes</span></span>  
  
|<span data-ttu-id="fd21d-152">Valore</span><span class="sxs-lookup"><span data-stu-id="fd21d-152">Value</span></span>|<span data-ttu-id="fd21d-153">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd21d-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fd21d-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="fd21d-154">*policy_setting*</span></span>|<span data-ttu-id="fd21d-155">L'impostazione da applicare a questo tipo di criteri.</span><span class="sxs-lookup"><span data-stu-id="fd21d-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="fd21d-156">I valori consentiti sono `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` e `Required All`.</span><span class="sxs-lookup"><span data-stu-id="fd21d-156">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="fd21d-157">Per altre informazioni, vedere [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).</span><span class="sxs-lookup"><span data-stu-id="fd21d-157">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fd21d-158">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fd21d-158">Child Elements</span></span>  
 <span data-ttu-id="fd21d-159">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="fd21d-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fd21d-160">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fd21d-160">Parent Elements</span></span>  
  
|<span data-ttu-id="fd21d-161">Elemento</span><span class="sxs-lookup"><span data-stu-id="fd21d-161">Element</span></span>|<span data-ttu-id="fd21d-162">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd21d-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fd21d-163">\<Type></span><span class="sxs-lookup"><span data-stu-id="fd21d-163">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="fd21d-164">Applica i criteri di reflection a un tipo e a tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="fd21d-164">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="fd21d-165">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="fd21d-165">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="fd21d-166">Applica i criteri di reflection a un tipo generico costruito e a tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="fd21d-166">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
|[<span data-ttu-id="fd21d-167">\<Method></span><span class="sxs-lookup"><span data-stu-id="fd21d-167">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)|<span data-ttu-id="fd21d-168">Applica i criteri di reflection a un metodo.</span><span class="sxs-lookup"><span data-stu-id="fd21d-168">Applies reflection policy to a method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd21d-169">Note</span><span class="sxs-lookup"><span data-stu-id="fd21d-169">Remarks</span></span>  
 <span data-ttu-id="fd21d-170">L'elemento `<ImpliesType>` viene usato principalmente dalle librerie.</span><span class="sxs-lookup"><span data-stu-id="fd21d-170">The `<ImpliesType>` element is primarily intended for use by libraries.</span></span> <span data-ttu-id="fd21d-171">Consente di risolvere il seguente scenario:</span><span class="sxs-lookup"><span data-stu-id="fd21d-171">It addresses the following scenario:</span></span>  
  
-   <span data-ttu-id="fd21d-172">Se una routine deve eseguire la reflection su un tipo, deve necessariamente eseguirla anche su un secondo tipo.</span><span class="sxs-lookup"><span data-stu-id="fd21d-172">If a routine needs to reflect on one type, it necessarily needs to reflect on a second type.</span></span>  
  
-   <span data-ttu-id="fd21d-173">I metadati per la creazione di istanze implicita del secondo tipo sono altrimenti disponibili, in quanto l'analisi statica non indica che sono necessari.</span><span class="sxs-lookup"><span data-stu-id="fd21d-173">The metadata for the implied instantiation of the second type is otherwise unavailable, because static analysis doesn't indicate that it's necessary.</span></span>  
  
 <span data-ttu-id="fd21d-174">I due tipi sono, in genere, creazioni di istanze generiche con gli argomenti di tipo condiviso.</span><span class="sxs-lookup"><span data-stu-id="fd21d-174">Most commonly, the two types are generic instantiations with shared type arguments.</span></span>  
  
 <span data-ttu-id="fd21d-175">L'elemento `<ImpliesType>` è stato definito partendo dal presupposto che la necessità di reflection sul tipo specificato dal relativo elemento padre comporta la necessità della reflection sul tipo specificato dall'elemento `<ImpliesType>`.</span><span class="sxs-lookup"><span data-stu-id="fd21d-175">The `<ImpliesType>` element was defined with the assumption that a need for reflection on the type specified by its parent element implies a need for reflection on the type specified by the `<ImpliesType>` element.</span></span> <span data-ttu-id="fd21d-176">Ad esempio, le seguenti direttive di reflection si applicano a due tipi: `Explicit<T>` e `Implicit<T>`.</span><span class="sxs-lookup"><span data-stu-id="fd21d-176">For example, the following reflection directives apply to two types, `Explicit<T>` and `Implicit<T>`.</span></span>  
  
```xml  
<Type Name="Explicit{ET}">  
    <ImpliesType Name="Implicit{ET}" Dynamic="Required Public" />  
</Type>  
```  
  
 <span data-ttu-id="fd21d-177">Questa direttiva non ha alcun effetto a meno che non sia stata definita un'impostazione di criteri `Explicit` per un'istanza di `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="fd21d-177">This directive has no effect unless an instantiation of `Explicit` has a defined `Dynamic` policy setting.</span></span> <span data-ttu-id="fd21d-178">Se, ad esempio, è il caso per `Explicit<Int32>`, viene creata un'istanza di `Implicit<Int32>` con membri pubblici che contengono una radice e i relativi metadati vengono resi accessibili per la programmazione dinamica.</span><span class="sxs-lookup"><span data-stu-id="fd21d-178">For example, if that's the case for `Explicit<Int32>`, `Implicit<Int32>` is instantiated with its public members rooted, and their metadata is made accessible for dynamic programming.</span></span>  
  
 <span data-ttu-id="fd21d-179">Di seguito è riportato un esempio reale che si applica ad almeno un serializzatore.</span><span class="sxs-lookup"><span data-stu-id="fd21d-179">The following is a real-world example that applies to at least one serializer.</span></span> <span data-ttu-id="fd21d-180">Le direttive acquisiscono il requisito in base al quale la reflection su un elemento tipizzato come `IList<`*elemento*`>` comporta anche la reflection sul tipo `List<`*elemento*`>` corrispondente, senza che siano necessarie annotazioni per ogni applicazione.</span><span class="sxs-lookup"><span data-stu-id="fd21d-180">The directives capture the requirement that reflecting on something typed as `IList<`*something*`>` also involves reflecting on the corresponding `List<`*something*`>` type without requiring any per-application annotation.</span></span>  
  
```xml  
<Type Name="System.Collections.Generic.IList{T}">  
   <ImpliesType Name="System.Collections.Generic.List{T}" Serialize="Public" />  
</Type>  
```  
  
 <span data-ttu-id="fd21d-181">L'elemento `<ImpliesType>` può anche essere visualizzato all'interno di un elemento `<Method>`, perché in alcuni casi un'istanza di un metodo generico implica la reflection su un'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="fd21d-181">The `<ImpliesType>` element can also appear within a `<Method>` element, because in some cases instantiating a generic method implies reflecting on a type instantiation.</span></span> <span data-ttu-id="fd21d-182">Ad esempio, si supponga un metodo generico `IEnumerable<T> MakeEnumerable<T>(string``spelling``, T` `defaultValue``)` al quale una determinata libreria accederà in modo dinamico con i tipi <xref:System.Collections.Generic.List%601> e <xref:System.Array> associati.</span><span class="sxs-lookup"><span data-stu-id="fd21d-182">For example, imagine a generic method `IEnumerable<T> MakeEnumerable<T>(string` `spelling``, T` `defaultValue``)` that a given library will access dynamically along with the associated <xref:System.Collections.Generic.List%601> and <xref:System.Array> types.</span></span> <span data-ttu-id="fd21d-183">Questa operazione può essere espressa nel seguente modo:</span><span class="sxs-lookup"><span data-stu-id="fd21d-183">This can be expressed as:</span></span>  
  
```xml  
<Type Name="MyType">  
    <Method Name="MakeEnumerable{T}" Signature="(System.String, T)" Dynamic="Included">  
        <ImpliesType Name="T[]" Dynamic="Public" />  
        <ImpliesType Name="System.Collections.Generic.List{T}" Dynamic="Public">  
    </Method>  
</Type>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fd21d-184">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd21d-184">See also</span></span>
- [<span data-ttu-id="fd21d-185">Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="fd21d-185">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="fd21d-186">Elementi direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="fd21d-186">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
- [<span data-ttu-id="fd21d-187">Impostazioni dei criteri delle direttive di runtime</span><span class="sxs-lookup"><span data-stu-id="fd21d-187">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
