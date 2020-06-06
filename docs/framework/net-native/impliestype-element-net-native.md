---
title: <ImpliesType>Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: 3abd2071-0f28-40ba-b9a0-d52bd94cd2f6
ms.openlocfilehash: 57f4208233cd5e8544b4f1c254e3b0e0eaacd508
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79181011"
---
# <a name="impliestype-element-net-native"></a><span data-ttu-id="4aa77-102">\<ImpliesType>Elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="4aa77-102">\<ImpliesType> Element (.NET Native)</span></span>
<span data-ttu-id="4aa77-103">Applica criteri a un tipo, se tale criterio è stato applicato al metodo o al tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="4aa77-103">Applies policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4aa77-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4aa77-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4aa77-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4aa77-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4aa77-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4aa77-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4aa77-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="4aa77-107">Attributes</span></span>  
  
|<span data-ttu-id="4aa77-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="4aa77-108">Attribute</span></span>|<span data-ttu-id="4aa77-109">Tipo di attributo</span><span class="sxs-lookup"><span data-stu-id="4aa77-109">Attribute type</span></span>|<span data-ttu-id="4aa77-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4aa77-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="4aa77-111">Generale</span><span class="sxs-lookup"><span data-stu-id="4aa77-111">General</span></span>|<span data-ttu-id="4aa77-112">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4aa77-112">Required attribute.</span></span> <span data-ttu-id="4aa77-113">Specifica il nome tipo.</span><span class="sxs-lookup"><span data-stu-id="4aa77-113">Specifies the type name.</span></span>|  
|`Activate`|<span data-ttu-id="4aa77-114">Reflection</span><span class="sxs-lookup"><span data-stu-id="4aa77-114">Reflection</span></span>|<span data-ttu-id="4aa77-115">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4aa77-115">Optional attribute.</span></span> <span data-ttu-id="4aa77-116">Controlla l'accesso in fase di esecuzione ai costruttori per abilitare l'attivazione di istanze.</span><span class="sxs-lookup"><span data-stu-id="4aa77-116">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="4aa77-117">Reflection</span><span class="sxs-lookup"><span data-stu-id="4aa77-117">Reflection</span></span>|<span data-ttu-id="4aa77-118">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4aa77-118">Optional attribute.</span></span> <span data-ttu-id="4aa77-119">Controlla le query per le informazioni sugli elementi di programma, ma non abilita l'accesso in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4aa77-119">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="4aa77-120">Reflection</span><span class="sxs-lookup"><span data-stu-id="4aa77-120">Reflection</span></span>|<span data-ttu-id="4aa77-121">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4aa77-121">Optional attribute.</span></span> <span data-ttu-id="4aa77-122">Controlla l'accesso in fase di esecuzione a tutti i membri dei tipi, inclusi costruttori, metodi, campi, proprietà ed eventi, per abilitare la programmazione dinamica.</span><span class="sxs-lookup"><span data-stu-id="4aa77-122">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="4aa77-123">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="4aa77-123">Serialization</span></span>|<span data-ttu-id="4aa77-124">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4aa77-124">Optional attribute.</span></span> <span data-ttu-id="4aa77-125">Controlla l'accesso in fase di esecuzione a costruttori, campi e proprietà per abilitare la serializzazione e la deserializzazione delle istanze del tipo da parte di librerie quali il serializzatore JSON di Newtonsoft.</span><span class="sxs-lookup"><span data-stu-id="4aa77-125">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="4aa77-126">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="4aa77-126">Serialization</span></span>|<span data-ttu-id="4aa77-127">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4aa77-127">Optional attribute.</span></span> <span data-ttu-id="4aa77-128">Controlla i criteri per la serializzazione che usano la classe <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4aa77-128">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="4aa77-129">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="4aa77-129">Serialization</span></span>|<span data-ttu-id="4aa77-130">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4aa77-130">Optional attribute.</span></span> <span data-ttu-id="4aa77-131">Controlla i criteri per la serializzazione JSON che usano la classe <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4aa77-131">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="4aa77-132">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="4aa77-132">Serialization</span></span>|<span data-ttu-id="4aa77-133">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4aa77-133">Optional attribute.</span></span> <span data-ttu-id="4aa77-134">Controlla i criteri per la serializzazione XML che usano la classe <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4aa77-134">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="4aa77-135">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="4aa77-135">Interop</span></span>|<span data-ttu-id="4aa77-136">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4aa77-136">Optional attribute.</span></span> <span data-ttu-id="4aa77-137">Controlla i criteri per effettuare il marshalling dei tipi di riferimento a Windows Runtime e COM.</span><span class="sxs-lookup"><span data-stu-id="4aa77-137">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="4aa77-138">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="4aa77-138">Interop</span></span>|<span data-ttu-id="4aa77-139">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4aa77-139">Optional attribute.</span></span> <span data-ttu-id="4aa77-140">Controlla i criteri per effettuare il marshalling dei tipi delegati come puntatori a funzioni al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="4aa77-140">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="4aa77-141">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="4aa77-141">Interop</span></span>|<span data-ttu-id="4aa77-142">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4aa77-142">Optional attribute.</span></span> <span data-ttu-id="4aa77-143">Controlla i criteri per il marshalling dei tipi di valore al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="4aa77-143">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="4aa77-144">Name (attributo)</span><span class="sxs-lookup"><span data-stu-id="4aa77-144">Name attribute</span></span>  
  
|<span data-ttu-id="4aa77-145">Valore</span><span class="sxs-lookup"><span data-stu-id="4aa77-145">Value</span></span>|<span data-ttu-id="4aa77-146">Description</span><span class="sxs-lookup"><span data-stu-id="4aa77-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4aa77-147">*type_name*</span><span class="sxs-lookup"><span data-stu-id="4aa77-147">*type_name*</span></span>|<span data-ttu-id="4aa77-148">Nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="4aa77-148">The type name.</span></span> <span data-ttu-id="4aa77-149">Se il tipo rappresentato da questo elemento `<ImpliesType>` si trova nello stesso spazio dei nomi dell'elemento `<Type>` contenitore, *type_name* può includere il nome del tipo senza lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="4aa77-149">If the type represented by this `<ImpliesType>` element is located in the same namespace as its containing `<Type>` element, *type_name* can include the name of the type without its namespace.</span></span> <span data-ttu-id="4aa77-150">In caso contrario, *type_name* deve includere il nome completo del tipo.</span><span class="sxs-lookup"><span data-stu-id="4aa77-150">Otherwise, *type_name* must include the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="4aa77-151">Tutti gli altri attributi</span><span class="sxs-lookup"><span data-stu-id="4aa77-151">All other attributes</span></span>  
  
|<span data-ttu-id="4aa77-152">Valore</span><span class="sxs-lookup"><span data-stu-id="4aa77-152">Value</span></span>|<span data-ttu-id="4aa77-153">Description</span><span class="sxs-lookup"><span data-stu-id="4aa77-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4aa77-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="4aa77-154">*policy_setting*</span></span>|<span data-ttu-id="4aa77-155">L'impostazione da applicare a questo tipo di criteri.</span><span class="sxs-lookup"><span data-stu-id="4aa77-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="4aa77-156">I valori consentiti sono `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` e `Required All`.</span><span class="sxs-lookup"><span data-stu-id="4aa77-156">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="4aa77-157">Per altre informazioni, vedere [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).</span><span class="sxs-lookup"><span data-stu-id="4aa77-157">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4aa77-158">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4aa77-158">Child Elements</span></span>  
 <span data-ttu-id="4aa77-159">No.</span><span class="sxs-lookup"><span data-stu-id="4aa77-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4aa77-160">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4aa77-160">Parent Elements</span></span>  
  
|<span data-ttu-id="4aa77-161">Elemento</span><span class="sxs-lookup"><span data-stu-id="4aa77-161">Element</span></span>|<span data-ttu-id="4aa77-162">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4aa77-162">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="4aa77-163">Applica i criteri di reflection a un tipo e a tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="4aa77-163">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="4aa77-164">Applica i criteri di reflection a un tipo generico costruito e a tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="4aa77-164">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
|[\<Method>](method-element-net-native.md)|<span data-ttu-id="4aa77-165">Applica i criteri di reflection a un metodo.</span><span class="sxs-lookup"><span data-stu-id="4aa77-165">Applies reflection policy to a method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4aa77-166">Commenti</span><span class="sxs-lookup"><span data-stu-id="4aa77-166">Remarks</span></span>  
 <span data-ttu-id="4aa77-167">L'elemento `<ImpliesType>` viene usato principalmente dalle librerie.</span><span class="sxs-lookup"><span data-stu-id="4aa77-167">The `<ImpliesType>` element is primarily intended for use by libraries.</span></span> <span data-ttu-id="4aa77-168">Consente di risolvere il seguente scenario:</span><span class="sxs-lookup"><span data-stu-id="4aa77-168">It addresses the following scenario:</span></span>  
  
- <span data-ttu-id="4aa77-169">Se una routine deve eseguire la reflection su un tipo, deve necessariamente eseguirla anche su un secondo tipo.</span><span class="sxs-lookup"><span data-stu-id="4aa77-169">If a routine needs to reflect on one type, it necessarily needs to reflect on a second type.</span></span>  
  
- <span data-ttu-id="4aa77-170">I metadati per la creazione di istanze implicita del secondo tipo sono altrimenti disponibili, in quanto l'analisi statica non indica che sono necessari.</span><span class="sxs-lookup"><span data-stu-id="4aa77-170">The metadata for the implied instantiation of the second type is otherwise unavailable, because static analysis doesn't indicate that it's necessary.</span></span>  
  
 <span data-ttu-id="4aa77-171">I due tipi sono, in genere, creazioni di istanze generiche con gli argomenti tipo condiviso.</span><span class="sxs-lookup"><span data-stu-id="4aa77-171">Most commonly, the two types are generic instantiations with shared type arguments.</span></span>  
  
 <span data-ttu-id="4aa77-172">L'elemento `<ImpliesType>` è stato definito partendo dal presupposto che la necessità di reflection sul tipo specificato dal relativo elemento padre comporta la necessità della reflection sul tipo specificato dall'elemento `<ImpliesType>`.</span><span class="sxs-lookup"><span data-stu-id="4aa77-172">The `<ImpliesType>` element was defined with the assumption that a need for reflection on the type specified by its parent element implies a need for reflection on the type specified by the `<ImpliesType>` element.</span></span> <span data-ttu-id="4aa77-173">Ad esempio, le seguenti direttive di reflection si applicano a due tipi: `Explicit<T>` e `Implicit<T>`.</span><span class="sxs-lookup"><span data-stu-id="4aa77-173">For example, the following reflection directives apply to two types, `Explicit<T>` and `Implicit<T>`.</span></span>  
  
```xml  
<Type Name="Explicit{ET}">  
    <ImpliesType Name="Implicit{ET}" Dynamic="Required Public" />  
</Type>  
```  
  
 <span data-ttu-id="4aa77-174">Questa direttiva non ha alcun effetto a meno che non sia stata definita un'impostazione di criteri `Explicit` per un'istanza di `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="4aa77-174">This directive has no effect unless an instantiation of `Explicit` has a defined `Dynamic` policy setting.</span></span> <span data-ttu-id="4aa77-175">Se, ad esempio, è il caso per `Explicit<Int32>`, viene creata un'istanza di `Implicit<Int32>` con membri pubblici che contengono una radice e i relativi metadati vengono resi accessibili per la programmazione dinamica.</span><span class="sxs-lookup"><span data-stu-id="4aa77-175">For example, if that's the case for `Explicit<Int32>`, `Implicit<Int32>` is instantiated with its public members rooted, and their metadata is made accessible for dynamic programming.</span></span>  
  
 <span data-ttu-id="4aa77-176">Di seguito è riportato un esempio reale che si applica ad almeno un serializzatore.</span><span class="sxs-lookup"><span data-stu-id="4aa77-176">The following is a real-world example that applies to at least one serializer.</span></span> <span data-ttu-id="4aa77-177">Le direttive acquisiscono il requisito che la reflection su un elemento tipizzato come `IList<` *elemento* `>` comporta anche la reflection sul tipo di `List<` *elemento* corrispondente `>` senza richiedere annotazioni per ogni applicazione.</span><span class="sxs-lookup"><span data-stu-id="4aa77-177">The directives capture the requirement that reflecting on something typed as `IList<`*something*`>` also involves reflecting on the corresponding `List<`*something*`>` type without requiring any per-application annotation.</span></span>  
  
```xml  
<Type Name="System.Collections.Generic.IList{T}">  
   <ImpliesType Name="System.Collections.Generic.List{T}" Serialize="Public" />  
</Type>  
```  
  
 <span data-ttu-id="4aa77-178">L'elemento `<ImpliesType>` può anche essere visualizzato all'interno di un elemento `<Method>`, perché in alcuni casi un'istanza di un metodo generico implica la reflection su un'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="4aa77-178">The `<ImpliesType>` element can also appear within a `<Method>` element, because in some cases instantiating a generic method implies reflecting on a type instantiation.</span></span> <span data-ttu-id="4aa77-179">Ad esempio, si supponga un metodo generico `IEnumerable<T> MakeEnumerable<T>(string spelling, T defaultValue)` al quale una determinata libreria accederà in modo dinamico con i tipi <xref:System.Collections.Generic.List%601> e <xref:System.Array> associati.</span><span class="sxs-lookup"><span data-stu-id="4aa77-179">For example, imagine a generic method `IEnumerable<T> MakeEnumerable<T>(string spelling, T defaultValue)` that a given library will access dynamically along with the associated <xref:System.Collections.Generic.List%601> and <xref:System.Array> types.</span></span> <span data-ttu-id="4aa77-180">Questa operazione può essere espressa nel seguente modo:</span><span class="sxs-lookup"><span data-stu-id="4aa77-180">This can be expressed as:</span></span>  
  
```xml  
<Type Name="MyType">  
    <Method Name="MakeEnumerable{T}" Signature="(System.String, T)" Dynamic="Included">  
        <ImpliesType Name="T[]" Dynamic="Public" />  
        <ImpliesType Name="System.Collections.Generic.List{T}" Dynamic="Public" />  
    </Method>  
</Type>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4aa77-181">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="4aa77-181">See also</span></span>

- [<span data-ttu-id="4aa77-182">Riferimento a file di configurazione di direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="4aa77-182">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="4aa77-183">Elementi direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="4aa77-183">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="4aa77-184">Impostazioni dei criteri della direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="4aa77-184">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
