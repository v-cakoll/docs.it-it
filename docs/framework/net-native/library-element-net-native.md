---
title: Elemento &lt;Library&gt; (.NET Native)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f642276b-33fb-4a81-b882-8808c31ba69e
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6b93335d0d5d1524c9a0b955d1ea279be8c0f243
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltlibrarygt-element-net-native"></a><span data-ttu-id="441a7-102">Elemento &lt;Library&gt; (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="441a7-102">&lt;Library&gt; Element (.NET Native)</span></span>
<span data-ttu-id="441a7-103">Definisce l'assembly che contiene i tipi e i membri dei tipi i cui metadati sono disponibili per la reflection al runtime.</span><span class="sxs-lookup"><span data-stu-id="441a7-103">Defines the assembly that contains types and type members whose metadata is available for reflection at run time.</span></span>  
  
 <span data-ttu-id="441a7-104">Elemento \<Directives></span><span class="sxs-lookup"><span data-stu-id="441a7-104">\<Directives> Element</span></span>  
<span data-ttu-id="441a7-105">Elemento \<Library></span><span class="sxs-lookup"><span data-stu-id="441a7-105">\<Library> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="441a7-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="441a7-106">Syntax</span></span>  
  
```xml  
<Library Name="assembly_name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="441a7-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="441a7-107">Attributes and Elements</span></span>  
 <span data-ttu-id="441a7-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="441a7-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="441a7-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="441a7-109">Attributes</span></span>  
  
|<span data-ttu-id="441a7-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="441a7-110">Attribute</span></span>|<span data-ttu-id="441a7-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="441a7-111">Description</span></span>|  
|---------------|-----------------|  
|`Name`|<span data-ttu-id="441a7-112">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="441a7-112">Required attribute.</span></span> <span data-ttu-id="441a7-113">Specifica il nome di un assembly.</span><span class="sxs-lookup"><span data-stu-id="441a7-113">Specifies the name of an assembly.</span></span> <span data-ttu-id="441a7-114">Gli elementi figlio di questo elemento `<Library>` definiscono i criteri di reflection di runtime per i tipi e i membri dei tipi rilevati nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="441a7-114">Child elements of this `<Library>` element define the runtime reflection policy for types and type members found in this assembly.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="441a7-115">Name (attributo)</span><span class="sxs-lookup"><span data-stu-id="441a7-115">Name attribute</span></span>  
  
|<span data-ttu-id="441a7-116">Valore</span><span class="sxs-lookup"><span data-stu-id="441a7-116">Value</span></span>|<span data-ttu-id="441a7-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="441a7-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="441a7-118">*assembly_name*</span><span class="sxs-lookup"><span data-stu-id="441a7-118">*assembly_name*</span></span>|<span data-ttu-id="441a7-119">Il nome semplice dell'assembly, senza estensione di file.</span><span class="sxs-lookup"><span data-stu-id="441a7-119">The simple name of the assembly, without its file extension.</span></span> <span data-ttu-id="441a7-120">Questo attributo corrisponde alla proprietà <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="441a7-120">This attribute corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="441a7-121">Ad esempio, il nome di un assembly denominato Extensions.dll è "Extensions".</span><span class="sxs-lookup"><span data-stu-id="441a7-121">For example, the name of an assembly named Extensions.dll is "Extensions".</span></span> <span data-ttu-id="441a7-122">Vedere la sezione Note per informazioni su un formato speciale di *assembly_name* che supporta l'inclusione condizionale di metadati dall'assembly.</span><span class="sxs-lookup"><span data-stu-id="441a7-122">See the Remarks section for a special form of *assembly_name* that supports conditional inclusion of metadata from the assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="441a7-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="441a7-123">Child Elements</span></span>  
  
|<span data-ttu-id="441a7-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="441a7-124">Element</span></span>|<span data-ttu-id="441a7-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="441a7-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="441a7-126">\<Assembly></span><span class="sxs-lookup"><span data-stu-id="441a7-126">\<Assembly></span></span>](../../../docs/framework/net-native/assembly-element-net-native.md)|<span data-ttu-id="441a7-127">Applica i criteri a tutti i tipi in un determinato assembly.</span><span class="sxs-lookup"><span data-stu-id="441a7-127">Applies policy to all the types in a particular assembly.</span></span>|  
|[<span data-ttu-id="441a7-128">\<Namespace></span><span class="sxs-lookup"><span data-stu-id="441a7-128">\<Namespace></span></span>](../../../docs/framework/net-native/namespace-element-net-native.md)|<span data-ttu-id="441a7-129">Applica i criteri a tutti i tipi in un determinato spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="441a7-129">Applies policy to all the types in a particular namespace.</span></span>|  
|[<span data-ttu-id="441a7-130">\<Type></span><span class="sxs-lookup"><span data-stu-id="441a7-130">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="441a7-131">Applica i criteri a un determinato tipo, ad esempio una classe o una struttura.</span><span class="sxs-lookup"><span data-stu-id="441a7-131">Applies policy to a particular type, such as a class or structure.</span></span>|  
|[<span data-ttu-id="441a7-132">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="441a7-132">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="441a7-133">Applica i criteri a un tipo generico costruito.</span><span class="sxs-lookup"><span data-stu-id="441a7-133">Applies policy to a constructed generic type.</span></span> <span data-ttu-id="441a7-134">Ad esempio, un elemento [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) può essere usato per definire i criteri per un tipo `List<String>`.</span><span class="sxs-lookup"><span data-stu-id="441a7-134">For example, a [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element could be used to define policy for a `List<String>` type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="441a7-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="441a7-135">Parent Elements</span></span>  
  
|<span data-ttu-id="441a7-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="441a7-136">Element</span></span>|<span data-ttu-id="441a7-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="441a7-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="441a7-138">\<Directives></span><span class="sxs-lookup"><span data-stu-id="441a7-138">\<Directives></span></span>](../../../docs/framework/net-native/directives-element-net-native.md)|<span data-ttu-id="441a7-139">L'elemento radice di un file di direttive di runtime.</span><span class="sxs-lookup"><span data-stu-id="441a7-139">The root element of a runtime directives file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="441a7-140">Note</span><span class="sxs-lookup"><span data-stu-id="441a7-140">Remarks</span></span>  
 <span data-ttu-id="441a7-141">L'elemento [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) può contenere nessuno, uno o più elementi `<Library>`.</span><span class="sxs-lookup"><span data-stu-id="441a7-141">The [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) element can contain zero, one, or more `<Library>` elements.</span></span>  
  
 <span data-ttu-id="441a7-142">L'elemento `<Library>` viene usato come contenitore per definire gli elementi di programma i cui metadati sono richiesti al runtime; questo elemento non esprime criteri.</span><span class="sxs-lookup"><span data-stu-id="441a7-142">The `<Library>` element serves as a container to define the program elements whose metadata is needed at run time; this element doesn't express policy.</span></span> <span data-ttu-id="441a7-143">Durante la compilazione, gli strumenti di compilazione cercano gli elementi di programma identificati dagli elementi figlio solo nella libreria designata dall'elemento `<Library>`.</span><span class="sxs-lookup"><span data-stu-id="441a7-143">At compile time, compiler tools search only the library designated by the `<Library>` element for program elements identified by its child elements.</span></span> <span data-ttu-id="441a7-144">Al contrario, gli strumenti di compilazione cercano gli elementi di programma identificati dagli elementi figlio dell'elemento [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) in tutte le librerie, incluse le librerie di base .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="441a7-144">In contrast, compiler tools search all libraries, including.NET Framework core libraries, for program elements identified by child elements of the [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) element.</span></span>  
  
 <span data-ttu-id="441a7-145">Le direttive `<Library>` possono essere usate in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="441a7-145">`<Library>` directives may be conditionally utilized.</span></span> <span data-ttu-id="441a7-146">Se il nome dell'elemento `<Library>` inizia e finisce con un asterisco (*), la direttiva `<Library>` ha effetto solo se nell'app si fa riferimento all'assembly racchiuso tra asterischi.</span><span class="sxs-lookup"><span data-stu-id="441a7-146">If the name of the `<Library>` element starts and ends with an asterisk (*), the `<Library>` directive has an effect only if the assembly specified between the asterisks is referenced by the app.</span></span> <span data-ttu-id="441a7-147">Ad esempio, la seguente direttiva di runtime si applica solo se l'assembly Utillities.dll viene indicata dall'app.</span><span class="sxs-lookup"><span data-stu-id="441a7-147">For example, the following runtime directive applies only if the Utillities.dll assembly is referenced by the app.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Library Name="*Utilities*">  
   ...  
  </Library>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="441a7-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="441a7-148">See Also</span></span>  
 [<span data-ttu-id="441a7-149">\<Applicazione > elemento</span><span class="sxs-lookup"><span data-stu-id="441a7-149">\<Application> Element</span></span>](../../../docs/framework/net-native/application-element-net-native.md)  
 [<span data-ttu-id="441a7-150">\<Direttive > elemento</span><span class="sxs-lookup"><span data-stu-id="441a7-150">\<Directives> Element</span></span>](../../../docs/framework/net-native/directives-element-net-native.md)  
 [<span data-ttu-id="441a7-151">Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="441a7-151">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="441a7-152">Elementi direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="441a7-152">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
