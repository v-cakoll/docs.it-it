---
title: Elemento <ImpliesType> (.NET Native)
ms.date: 03/30/2017
ms.assetid: 3abd2071-0f28-40ba-b9a0-d52bd94cd2f6
ms.openlocfilehash: 2f0ce1a1587e190627212cba07db298c12f4b30e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128397"
---
# <a name="impliestype-element-net-native"></a><span data-ttu-id="ad4c5-102">\<elemento ImpliesType > (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="ad4c5-102">\<ImpliesType> Element (.NET Native)</span></span>
<span data-ttu-id="ad4c5-103">Applica criteri a un tipo, se tale criterio è stato applicato al metodo o al tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-103">Applies policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad4c5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ad4c5-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad4c5-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ad4c5-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ad4c5-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad4c5-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="ad4c5-107">Attributes</span></span>  
  
|<span data-ttu-id="ad4c5-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="ad4c5-108">Attribute</span></span>|<span data-ttu-id="ad4c5-109">Tipo di attributo</span><span class="sxs-lookup"><span data-stu-id="ad4c5-109">Attribute type</span></span>|<span data-ttu-id="ad4c5-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad4c5-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="ad4c5-111">Generale</span><span class="sxs-lookup"><span data-stu-id="ad4c5-111">General</span></span>|<span data-ttu-id="ad4c5-112">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-112">Required attribute.</span></span> <span data-ttu-id="ad4c5-113">Specifica il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-113">Specifies the type name.</span></span>|  
|`Activate`|<span data-ttu-id="ad4c5-114">Reflection</span><span class="sxs-lookup"><span data-stu-id="ad4c5-114">Reflection</span></span>|<span data-ttu-id="ad4c5-115">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-115">Optional attribute.</span></span> <span data-ttu-id="ad4c5-116">Controlla l'accesso in fase di esecuzione ai costruttori per abilitare l'attivazione di istanze.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-116">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="ad4c5-117">Reflection</span><span class="sxs-lookup"><span data-stu-id="ad4c5-117">Reflection</span></span>|<span data-ttu-id="ad4c5-118">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-118">Optional attribute.</span></span> <span data-ttu-id="ad4c5-119">Controlla le query per le informazioni sugli elementi di programma, ma non abilita l'accesso in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-119">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="ad4c5-120">Reflection</span><span class="sxs-lookup"><span data-stu-id="ad4c5-120">Reflection</span></span>|<span data-ttu-id="ad4c5-121">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-121">Optional attribute.</span></span> <span data-ttu-id="ad4c5-122">Controlla l'accesso in fase di esecuzione a tutti i membri dei tipi, inclusi costruttori, metodi, campi, proprietà ed eventi, per abilitare la programmazione dinamica.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-122">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="ad4c5-123">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="ad4c5-123">Serialization</span></span>|<span data-ttu-id="ad4c5-124">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-124">Optional attribute.</span></span> <span data-ttu-id="ad4c5-125">Controlla l'accesso in fase di esecuzione a costruttori, campi e proprietà per abilitare la serializzazione e la deserializzazione delle istanze del tipo da parte di librerie quali il serializzatore JSON di Newtonsoft.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-125">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="ad4c5-126">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="ad4c5-126">Serialization</span></span>|<span data-ttu-id="ad4c5-127">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-127">Optional attribute.</span></span> <span data-ttu-id="ad4c5-128">Controlla i criteri per la serializzazione che usano la classe <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-128">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="ad4c5-129">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="ad4c5-129">Serialization</span></span>|<span data-ttu-id="ad4c5-130">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-130">Optional attribute.</span></span> <span data-ttu-id="ad4c5-131">Controlla i criteri per la serializzazione JSON che usano la classe <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-131">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="ad4c5-132">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="ad4c5-132">Serialization</span></span>|<span data-ttu-id="ad4c5-133">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-133">Optional attribute.</span></span> <span data-ttu-id="ad4c5-134">Controlla i criteri per la serializzazione XML che usano la classe <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-134">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="ad4c5-135">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="ad4c5-135">Interop</span></span>|<span data-ttu-id="ad4c5-136">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-136">Optional attribute.</span></span> <span data-ttu-id="ad4c5-137">Controlla i criteri per effettuare il marshalling dei tipi di riferimento a Windows Runtime e COM.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-137">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="ad4c5-138">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="ad4c5-138">Interop</span></span>|<span data-ttu-id="ad4c5-139">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-139">Optional attribute.</span></span> <span data-ttu-id="ad4c5-140">Controlla i criteri per effettuare il marshalling dei tipi delegati come puntatori a funzioni al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-140">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="ad4c5-141">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="ad4c5-141">Interop</span></span>|<span data-ttu-id="ad4c5-142">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-142">Optional attribute.</span></span> <span data-ttu-id="ad4c5-143">Controlla i criteri per il marshalling dei tipi di valore al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-143">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="ad4c5-144">Name (attributo)</span><span class="sxs-lookup"><span data-stu-id="ad4c5-144">Name attribute</span></span>  
  
|<span data-ttu-id="ad4c5-145">Value</span><span class="sxs-lookup"><span data-stu-id="ad4c5-145">Value</span></span>|<span data-ttu-id="ad4c5-146">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad4c5-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ad4c5-147">*type_name*</span><span class="sxs-lookup"><span data-stu-id="ad4c5-147">*type_name*</span></span>|<span data-ttu-id="ad4c5-148">Nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-148">The type name.</span></span> <span data-ttu-id="ad4c5-149">Se il tipo rappresentato da questo elemento `<ImpliesType>` si trova nello stesso spazio dei nomi dell'elemento `<Type>` contenitore, *type_name* può includere il nome del tipo senza lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-149">If the type represented by this `<ImpliesType>` element is located in the same namespace as its containing `<Type>` element, *type_name* can include the name of the type without its namespace.</span></span> <span data-ttu-id="ad4c5-150">In caso contrario, *type_name* deve includere il nome completo del tipo.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-150">Otherwise, *type_name* must include the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="ad4c5-151">Tutti gli altri attributi</span><span class="sxs-lookup"><span data-stu-id="ad4c5-151">All other attributes</span></span>  
  
|<span data-ttu-id="ad4c5-152">Value</span><span class="sxs-lookup"><span data-stu-id="ad4c5-152">Value</span></span>|<span data-ttu-id="ad4c5-153">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad4c5-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ad4c5-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="ad4c5-154">*policy_setting*</span></span>|<span data-ttu-id="ad4c5-155">L'impostazione da applicare a questo tipo di criteri.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="ad4c5-156">I valori consentiti sono `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` e `Required All`.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-156">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="ad4c5-157">Per altre informazioni, vedere [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).</span><span class="sxs-lookup"><span data-stu-id="ad4c5-157">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ad4c5-158">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ad4c5-158">Child Elements</span></span>  
 <span data-ttu-id="ad4c5-159">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ad4c5-160">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ad4c5-160">Parent Elements</span></span>  
  
|<span data-ttu-id="ad4c5-161">Elemento</span><span class="sxs-lookup"><span data-stu-id="ad4c5-161">Element</span></span>|<span data-ttu-id="ad4c5-162">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad4c5-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ad4c5-163">\<Type></span><span class="sxs-lookup"><span data-stu-id="ad4c5-163">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="ad4c5-164">Applica i criteri di reflection a un tipo e a tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-164">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="ad4c5-165">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="ad4c5-165">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)|<span data-ttu-id="ad4c5-166">Applica i criteri di reflection a un tipo generico costruito e a tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-166">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
|[<span data-ttu-id="ad4c5-167">\<Method></span><span class="sxs-lookup"><span data-stu-id="ad4c5-167">\<Method></span></span>](method-element-net-native.md)|<span data-ttu-id="ad4c5-168">Applica i criteri di reflection a un metodo.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-168">Applies reflection policy to a method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad4c5-169">Note</span><span class="sxs-lookup"><span data-stu-id="ad4c5-169">Remarks</span></span>  
 <span data-ttu-id="ad4c5-170">L'elemento `<ImpliesType>` viene usato principalmente dalle librerie.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-170">The `<ImpliesType>` element is primarily intended for use by libraries.</span></span> <span data-ttu-id="ad4c5-171">Consente di risolvere il seguente scenario:</span><span class="sxs-lookup"><span data-stu-id="ad4c5-171">It addresses the following scenario:</span></span>  
  
- <span data-ttu-id="ad4c5-172">Se una routine deve eseguire la reflection su un tipo, deve necessariamente eseguirla anche su un secondo tipo.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-172">If a routine needs to reflect on one type, it necessarily needs to reflect on a second type.</span></span>  
  
- <span data-ttu-id="ad4c5-173">I metadati per la creazione di istanze implicita del secondo tipo sono altrimenti disponibili, in quanto l'analisi statica non indica che sono necessari.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-173">The metadata for the implied instantiation of the second type is otherwise unavailable, because static analysis doesn't indicate that it's necessary.</span></span>  
  
 <span data-ttu-id="ad4c5-174">I due tipi sono, in genere, creazioni di istanze generiche con gli argomenti tipo condiviso.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-174">Most commonly, the two types are generic instantiations with shared type arguments.</span></span>  
  
 <span data-ttu-id="ad4c5-175">L'elemento `<ImpliesType>` è stato definito partendo dal presupposto che la necessità di reflection sul tipo specificato dal relativo elemento padre comporta la necessità della reflection sul tipo specificato dall'elemento `<ImpliesType>`.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-175">The `<ImpliesType>` element was defined with the assumption that a need for reflection on the type specified by its parent element implies a need for reflection on the type specified by the `<ImpliesType>` element.</span></span> <span data-ttu-id="ad4c5-176">Ad esempio, le seguenti direttive di reflection si applicano a due tipi: `Explicit<T>` e `Implicit<T>`.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-176">For example, the following reflection directives apply to two types, `Explicit<T>` and `Implicit<T>`.</span></span>  
  
```xml  
<Type Name="Explicit{ET}">  
    <ImpliesType Name="Implicit{ET}" Dynamic="Required Public" />  
</Type>  
```  
  
 <span data-ttu-id="ad4c5-177">Questa direttiva non ha alcun effetto a meno che non sia stata definita un'impostazione di criteri `Explicit` per un'istanza di `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-177">This directive has no effect unless an instantiation of `Explicit` has a defined `Dynamic` policy setting.</span></span> <span data-ttu-id="ad4c5-178">Se, ad esempio, è il caso per `Explicit<Int32>`, viene creata un'istanza di `Implicit<Int32>` con membri pubblici che contengono una radice e i relativi metadati vengono resi accessibili per la programmazione dinamica.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-178">For example, if that's the case for `Explicit<Int32>`, `Implicit<Int32>` is instantiated with its public members rooted, and their metadata is made accessible for dynamic programming.</span></span>  
  
 <span data-ttu-id="ad4c5-179">Di seguito è riportato un esempio reale che si applica ad almeno un serializzatore.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-179">The following is a real-world example that applies to at least one serializer.</span></span> <span data-ttu-id="ad4c5-180">Le direttive acquisiscono il requisito in base al quale la reflection su un elemento tipizzato come `IList<`*elemento*`>` comporta anche la reflection sul tipo `List<`*elemento*`>` corrispondente, senza che siano necessarie annotazioni per ogni applicazione.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-180">The directives capture the requirement that reflecting on something typed as `IList<`*something*`>` also involves reflecting on the corresponding `List<`*something*`>` type without requiring any per-application annotation.</span></span>  
  
```xml  
<Type Name="System.Collections.Generic.IList{T}">  
   <ImpliesType Name="System.Collections.Generic.List{T}" Serialize="Public" />  
</Type>  
```  
  
 <span data-ttu-id="ad4c5-181">L'elemento `<ImpliesType>` può anche essere visualizzato all'interno di un elemento `<Method>`, perché in alcuni casi un'istanza di un metodo generico implica la reflection su un'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-181">The `<ImpliesType>` element can also appear within a `<Method>` element, because in some cases instantiating a generic method implies reflecting on a type instantiation.</span></span> <span data-ttu-id="ad4c5-182">Si supponga, ad esempio, che un metodo generico `IEnumerable<T> MakeEnumerable<T>(string spelling, T defaultValue)` che una determinata libreria possa accedere dinamicamente insieme ai tipi di <xref:System.Collections.Generic.List%601> e <xref:System.Array> associati.</span><span class="sxs-lookup"><span data-stu-id="ad4c5-182">For example, imagine a generic method `IEnumerable<T> MakeEnumerable<T>(string spelling, T defaultValue)` that a given library will access dynamically along with the associated <xref:System.Collections.Generic.List%601> and <xref:System.Array> types.</span></span> <span data-ttu-id="ad4c5-183">Questa operazione può essere espressa nel seguente modo:</span><span class="sxs-lookup"><span data-stu-id="ad4c5-183">This can be expressed as:</span></span>  
  
```xml  
<Type Name="MyType">  
    <Method Name="MakeEnumerable{T}" Signature="(System.String, T)" Dynamic="Included">  
        <ImpliesType Name="T[]" Dynamic="Public" />  
        <ImpliesType Name="System.Collections.Generic.List{T}" Dynamic="Public" />  
    </Method>  
</Type>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ad4c5-184">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad4c5-184">See also</span></span>

- [<span data-ttu-id="ad4c5-185">Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="ad4c5-185">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="ad4c5-186">Elementi direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="ad4c5-186">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="ad4c5-187">Impostazioni dei criteri delle direttive di runtime</span><span class="sxs-lookup"><span data-stu-id="ad4c5-187">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
