---
title: <Library>Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: f642276b-33fb-4a81-b882-8808c31ba69e
ms.openlocfilehash: f94bfe047fa7a95b6f24264bae0b27112c589dfd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128359"
---
# <a name="library-element-net-native"></a><span data-ttu-id="08aa9-102">\<Library>Elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="08aa9-102">\<Library> Element (.NET Native)</span></span>
<span data-ttu-id="08aa9-103">Definisce l'assembly che contiene i tipi e i membri dei tipi i cui metadati sono disponibili per la reflection al runtime.</span><span class="sxs-lookup"><span data-stu-id="08aa9-103">Defines the assembly that contains types and type members whose metadata is available for reflection at run time.</span></span>  
  
 <span data-ttu-id="08aa9-104">\<Directives> Elemento</span><span class="sxs-lookup"><span data-stu-id="08aa9-104">\<Directives> Element</span></span>  
<span data-ttu-id="08aa9-105">\<Library> Elemento</span><span class="sxs-lookup"><span data-stu-id="08aa9-105">\<Library> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08aa9-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="08aa9-106">Syntax</span></span>  
  
```xml  
<Library Name="assembly_name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08aa9-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="08aa9-107">Attributes and Elements</span></span>  
 <span data-ttu-id="08aa9-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="08aa9-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08aa9-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="08aa9-109">Attributes</span></span>  
  
|<span data-ttu-id="08aa9-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="08aa9-110">Attribute</span></span>|<span data-ttu-id="08aa9-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08aa9-111">Description</span></span>|  
|---------------|-----------------|  
|`Name`|<span data-ttu-id="08aa9-112">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="08aa9-112">Required attribute.</span></span> <span data-ttu-id="08aa9-113">Specifica il nome di un assembly.</span><span class="sxs-lookup"><span data-stu-id="08aa9-113">Specifies the name of an assembly.</span></span> <span data-ttu-id="08aa9-114">Gli elementi figlio di questo elemento `<Library>` definiscono i criteri di reflection di runtime per i tipi e i membri dei tipi rilevati nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="08aa9-114">Child elements of this `<Library>` element define the runtime reflection policy for types and type members found in this assembly.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="08aa9-115">Name (attributo)</span><span class="sxs-lookup"><span data-stu-id="08aa9-115">Name attribute</span></span>  
  
|<span data-ttu-id="08aa9-116">Valore</span><span class="sxs-lookup"><span data-stu-id="08aa9-116">Value</span></span>|<span data-ttu-id="08aa9-117">Description</span><span class="sxs-lookup"><span data-stu-id="08aa9-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="08aa9-118">*assembly_name*</span><span class="sxs-lookup"><span data-stu-id="08aa9-118">*assembly_name*</span></span>|<span data-ttu-id="08aa9-119">Il nome semplice dell'assembly, senza estensione di file.</span><span class="sxs-lookup"><span data-stu-id="08aa9-119">The simple name of the assembly, without its file extension.</span></span> <span data-ttu-id="08aa9-120">Questo attributo corrisponde alla proprietà <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="08aa9-120">This attribute corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="08aa9-121">Ad esempio, il nome di un assembly denominato Extensions.dll è "Extensions".</span><span class="sxs-lookup"><span data-stu-id="08aa9-121">For example, the name of an assembly named Extensions.dll is "Extensions".</span></span> <span data-ttu-id="08aa9-122">Vedere la sezione Note per informazioni su un formato speciale di *assembly_name* che supporta l'inclusione condizionale di metadati dall'assembly.</span><span class="sxs-lookup"><span data-stu-id="08aa9-122">See the Remarks section for a special form of *assembly_name* that supports conditional inclusion of metadata from the assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="08aa9-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="08aa9-123">Child Elements</span></span>  
  
|<span data-ttu-id="08aa9-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="08aa9-124">Element</span></span>|<span data-ttu-id="08aa9-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08aa9-125">Description</span></span>|  
|-------------|-----------------|  
|[\<Assembly>](assembly-element-net-native.md)|<span data-ttu-id="08aa9-126">Applica i criteri a tutti i tipi in un determinato assembly.</span><span class="sxs-lookup"><span data-stu-id="08aa9-126">Applies policy to all the types in a particular assembly.</span></span>|  
|[\<Namespace>](namespace-element-net-native.md)|<span data-ttu-id="08aa9-127">Applica i criteri a tutti i tipi in un determinato spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="08aa9-127">Applies policy to all the types in a particular namespace.</span></span>|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="08aa9-128">Applica i criteri a un determinato tipo, ad esempio una classe o una struttura.</span><span class="sxs-lookup"><span data-stu-id="08aa9-128">Applies policy to a particular type, such as a class or structure.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="08aa9-129">Applica i criteri a un tipo generico costruito.</span><span class="sxs-lookup"><span data-stu-id="08aa9-129">Applies policy to a constructed generic type.</span></span> <span data-ttu-id="08aa9-130">Ad esempio, [\<TypeInstantiation>](typeinstantiation-element-net-native.md) è possibile usare un elemento per definire i criteri per un `List<String>` tipo.</span><span class="sxs-lookup"><span data-stu-id="08aa9-130">For example, a [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element could be used to define policy for a `List<String>` type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="08aa9-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="08aa9-131">Parent Elements</span></span>  
  
|<span data-ttu-id="08aa9-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="08aa9-132">Element</span></span>|<span data-ttu-id="08aa9-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08aa9-133">Description</span></span>|  
|-------------|-----------------|  
|[\<Directives>](directives-element-net-native.md)|<span data-ttu-id="08aa9-134">L'elemento radice di un file di direttive di runtime.</span><span class="sxs-lookup"><span data-stu-id="08aa9-134">The root element of a runtime directives file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08aa9-135">Commenti</span><span class="sxs-lookup"><span data-stu-id="08aa9-135">Remarks</span></span>  
 <span data-ttu-id="08aa9-136">L' [\<Directives>](directives-element-net-native.md) elemento può contenere zero, uno o più `<Library>` elementi.</span><span class="sxs-lookup"><span data-stu-id="08aa9-136">The [\<Directives>](directives-element-net-native.md) element can contain zero, one, or more `<Library>` elements.</span></span>  
  
 <span data-ttu-id="08aa9-137">L'elemento `<Library>` viene usato come contenitore per definire gli elementi di programma i cui metadati sono richiesti al runtime; questo elemento non esprime criteri.</span><span class="sxs-lookup"><span data-stu-id="08aa9-137">The `<Library>` element serves as a container to define the program elements whose metadata is needed at run time; this element doesn't express policy.</span></span> <span data-ttu-id="08aa9-138">Durante la compilazione, gli strumenti di compilazione cercano gli elementi di programma identificati dagli elementi figlio solo nella libreria designata dall'elemento `<Library>`.</span><span class="sxs-lookup"><span data-stu-id="08aa9-138">At compile time, compiler tools search only the library designated by the `<Library>` element for program elements identified by its child elements.</span></span> <span data-ttu-id="08aa9-139">Al contrario, gli strumenti di compilazione cercano gli elementi di programma identificati dagli elementi figlio dell'elemento in tutte le librerie, including.NET le librerie di base del Framework [\<Application>](application-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="08aa9-139">In contrast, compiler tools search all libraries, including.NET Framework core libraries, for program elements identified by child elements of the [\<Application>](application-element-net-native.md) element.</span></span>  
  
 <span data-ttu-id="08aa9-140">Le direttive `<Library>` possono essere usate in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="08aa9-140">`<Library>` directives may be conditionally utilized.</span></span> <span data-ttu-id="08aa9-141">Se il nome dell' `<Library>` elemento inizia e termina con un asterisco ( \* ), la `<Library>` direttiva ha effetto solo se l'app fa riferimento all'assembly specificato tra gli asterischi.</span><span class="sxs-lookup"><span data-stu-id="08aa9-141">If the name of the `<Library>` element starts and ends with an asterisk (\*), the `<Library>` directive has an effect only if the assembly specified between the asterisks is referenced by the app.</span></span> <span data-ttu-id="08aa9-142">Ad esempio, la direttiva di runtime seguente si applica solo se l'app fa riferimento all'assembly Utilities. dll.</span><span class="sxs-lookup"><span data-stu-id="08aa9-142">For example, the following runtime directive applies only if the Utilities.dll assembly is referenced by the app.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Library Name="*Utilities*">  
   ...  
  </Library>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="08aa9-143">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="08aa9-143">See also</span></span>

- [<span data-ttu-id="08aa9-144">\<Application>Elemento</span><span class="sxs-lookup"><span data-stu-id="08aa9-144">\<Application> Element</span></span>](application-element-net-native.md)
- [<span data-ttu-id="08aa9-145">\<Directives>Elemento</span><span class="sxs-lookup"><span data-stu-id="08aa9-145">\<Directives> Element</span></span>](directives-element-net-native.md)
- [<span data-ttu-id="08aa9-146">Riferimento a file di configurazione di direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="08aa9-146">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="08aa9-147">Elementi direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="08aa9-147">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
