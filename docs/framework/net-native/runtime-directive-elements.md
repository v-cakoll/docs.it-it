---
title: Elementi direttiva di runtime
ms.date: 03/30/2017
ms.assetid: 3fe5848c-ecd7-4136-970b-8e48d250bde6
ms.openlocfilehash: c900516382c8e526a6b0021bb2b681486283f3ab
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128175"
---
# <a name="runtime-directive-elements"></a><span data-ttu-id="80a9f-102">Elementi direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="80a9f-102">Runtime Directive Elements</span></span>
<span data-ttu-id="80a9f-103">Il formato del file delle direttive di runtime (rd.xml) supporta i seguenti elementi direttiva di runtime.</span><span class="sxs-lookup"><span data-stu-id="80a9f-103">The runtime directives (rd.xml) file format supports the following runtime directive elements.</span></span> <span data-ttu-id="80a9f-104">Per una rappresentazione gerarchica, vedere [Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md).</span><span class="sxs-lookup"><span data-stu-id="80a9f-104">See [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md) for a hierarchical representation.</span></span>  
  
 [\<Application>](application-element-net-native.md)  
 <span data-ttu-id="80a9f-105">Applica criteri di reflection di runtime a tutti i tipi usati dall'app e funge da contenitore per i tipi a livello di applicazione e i membri del tipo i cui metadati sono disponibili per la reflection in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="80a9f-105">Applies runtime reflection policy to all types used by the app, and serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="80a9f-106">Si tratta di un elemento figlio dell' [\<Directives>](directives-element-net-native.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="80a9f-106">This is a child of the [\<Directives>](directives-element-net-native.md) element.</span></span>  
  
 [\<Assembly>](assembly-element-net-native.md)  
 <span data-ttu-id="80a9f-107">Applica criteri di runtime a tutti i tipi in un assembly.</span><span class="sxs-lookup"><span data-stu-id="80a9f-107">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="80a9f-108">Si tratta di un elemento figlio [\<Application>](application-element-net-native.md) degli [\<Library>](library-element-net-native.md) elementi e.</span><span class="sxs-lookup"><span data-stu-id="80a9f-108">This is a child of the [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md) elements.</span></span>  
  
 [\<AttributeImplies>](attributeimplies-element-net-native.md)  
 <span data-ttu-id="80a9f-109">Se la [\<Type>](type-element-net-native.md) direttiva contenitore è un attributo, applica i criteri di runtime agli elementi di codice a cui è applicato l'attributo.</span><span class="sxs-lookup"><span data-stu-id="80a9f-109">If its containing [\<Type>](type-element-net-native.md) directive is an attribute, applies runtime policy to code elements to which that attribute is applied.</span></span>  
  
 [\<Directives>](directives-element-net-native.md)  
 <span data-ttu-id="80a9f-110">Elemento radice in ogni file di direttive di runtime per .NET Native.</span><span class="sxs-lookup"><span data-stu-id="80a9f-110">The root element in every runtime directives file for .NET Native.</span></span> <span data-ttu-id="80a9f-111">I relativi elementi figlio sono [\<Application>](application-element-net-native.md) e [\<Library>](library-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="80a9f-111">Its child elements are [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md).</span></span>  
  
 [\<Event>](event-element-net-native.md)  
 <span data-ttu-id="80a9f-112">Applica criteri di runtime a un evento.</span><span class="sxs-lookup"><span data-stu-id="80a9f-112">Applies runtime policy to an event.</span></span> <span data-ttu-id="80a9f-113">Si tratta di un elemento figlio [\<Type>](type-element-net-native.md) degli [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elementi e.</span><span class="sxs-lookup"><span data-stu-id="80a9f-113">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<Field>](field-element-net-native.md)  
 <span data-ttu-id="80a9f-114">Applica criteri di runtime a un campo.</span><span class="sxs-lookup"><span data-stu-id="80a9f-114">Applies runtime policy to a field.</span></span> <span data-ttu-id="80a9f-115">Si tratta di un elemento figlio [\<Type>](type-element-net-native.md) degli [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elementi e.</span><span class="sxs-lookup"><span data-stu-id="80a9f-115">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<GenericParameter>](genericparameter-element-net-native.md)  
 <span data-ttu-id="80a9f-116">Applica i criteri di runtime al tipo di parametro di un tipo o di un metodo generico.</span><span class="sxs-lookup"><span data-stu-id="80a9f-116">Applies runtime policy to the parameter type of a generic type or method.</span></span>  
  
 [\<ImpliesType>](impliestype-element-net-native.md)  
 <span data-ttu-id="80a9f-117">Applica criteri di runtime a un tipo, se tale criterio è stato applicato al metodo o al tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="80a9f-117">Applies runtime policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
 [\<Library>](library-element-net-native.md)  
 <span data-ttu-id="80a9f-118">Applica criteri di runtime a tutti i tipi in un assembly.</span><span class="sxs-lookup"><span data-stu-id="80a9f-118">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="80a9f-119">Si tratta di un elemento figlio [\<Application>](application-element-net-native.md) degli [\<Library>](library-element-net-native.md) elementi e.</span><span class="sxs-lookup"><span data-stu-id="80a9f-119">This is a child of the [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md) elements.</span></span>  
  
 [\<Method>](method-element-net-native.md)  
 <span data-ttu-id="80a9f-120">Applica criteri di runtime a un metodo.</span><span class="sxs-lookup"><span data-stu-id="80a9f-120">Applies runtime policy to a method.</span></span> <span data-ttu-id="80a9f-121">Si tratta di un elemento figlio [\<Type>](type-element-net-native.md) degli [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elementi e.</span><span class="sxs-lookup"><span data-stu-id="80a9f-121">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<MethodInstantiation>](methodinstantiation-element-net-native.md)  
 <span data-ttu-id="80a9f-122">Applica criteri di runtime a un metodo generico costruito.</span><span class="sxs-lookup"><span data-stu-id="80a9f-122">Applies runtime policy to a constructed generic method.</span></span> <span data-ttu-id="80a9f-123">Si tratta di un elemento figlio [\<Type>](type-element-net-native.md) degli [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elementi e.</span><span class="sxs-lookup"><span data-stu-id="80a9f-123">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<Namespace>](namespace-element-net-native.md)  
 <span data-ttu-id="80a9f-124">Applica criteri di runtime a tutti i tipi in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="80a9f-124">Applies runtime policy to all the types in a namespace.</span></span>  
  
 [\<Parameter>](parameter-element-net-native.md)  
 <span data-ttu-id="80a9f-125">Applica criteri di runtime al tipo di argomento passato a un metodo.</span><span class="sxs-lookup"><span data-stu-id="80a9f-125">Applies runtime policy to the type of the argument passed to a method.</span></span>  
  
 [\<Property>](property-element-net-native.md)  
 <span data-ttu-id="80a9f-126">Applica criteri di runtime a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="80a9f-126">Applies runtime policy to a property.</span></span> <span data-ttu-id="80a9f-127">Si tratta di un elemento figlio [\<Type>](type-element-net-native.md) degli [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elementi e.</span><span class="sxs-lookup"><span data-stu-id="80a9f-127">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<Subtypes>](subtypes-element-net-native.md)  
 <span data-ttu-id="80a9f-128">Applica i criteri di runtime a tutte le classi ereditate per il tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="80a9f-128">Applies runtime policy to all classes inherited from the containing type.</span></span>  
  
 [\<Type>](type-element-net-native.md)  
 <span data-ttu-id="80a9f-129">Applica criteri di runtime a un tipo.</span><span class="sxs-lookup"><span data-stu-id="80a9f-129">Applies runtime policy to a type.</span></span>  
  
 [\<TypeInstantiation>](typeinstantiation-element-net-native.md)  
 <span data-ttu-id="80a9f-130">Applica criteri di runtime a un tipo generico costruito.</span><span class="sxs-lookup"><span data-stu-id="80a9f-130">Applies runtime policy to a constructed generic type.</span></span>  
  
 [\<TypeParameter>](typeparameter-element-net-native.md)  
 <span data-ttu-id="80a9f-131">Applica criteri di runtime al tipo rappresentato da un argomento <xref:System.Type> passato a un metodo.</span><span class="sxs-lookup"><span data-stu-id="80a9f-131">Applies runtime policy to the type represented by a <xref:System.Type> argument passed to a method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80a9f-132">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="80a9f-132">See also</span></span>

- [<span data-ttu-id="80a9f-133">Informazioni di riferimento sul file di configurazione rd.xml</span><span class="sxs-lookup"><span data-stu-id="80a9f-133">rd.xml Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
