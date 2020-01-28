---
title: Riferimento a file di configurazione di direttive di runtime (rd.xml)
ms.date: 03/30/2017
ms.assetid: 8241523f-d8e1-4fb6-bf6a-b29bfe07b38a
ms.openlocfilehash: e74d34693446cca645003a9f93bc1777849e3182
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738413"
---
# <a name="runtime-directives-rdxml-configuration-file-reference"></a><span data-ttu-id="f06a2-102">Riferimento a file di configurazione di direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="f06a2-102">Runtime Directives (rd.xml) Configuration File Reference</span></span>

<span data-ttu-id="f06a2-103">Un file di direttive di runtime (rd.xml) è un file di configurazione XML che specifica se gli elementi del programma designato sono disponibili per la reflection.</span><span class="sxs-lookup"><span data-stu-id="f06a2-103">A runtime directives (.rd.xml) file is an XML configuration file that specifies whether designated program elements are available for reflection.</span></span> <span data-ttu-id="f06a2-104">Ecco un esempio di un file di direttive di runtime:</span><span class="sxs-lookup"><span data-stu-id="f06a2-104">Here’s an example of a runtime directives file:</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
    <Namespace Name="Contoso.Cloud.AppServices" Serialize="Required Public" />
    <Namespace Name="ContosoClient.ViewModels" Serialize="Required Public" />
    <Namespace Name="ContosoClient.DataModel" Serialize="Required Public" />
    <Namespace Name="Contoso.Reader.UtilityLib" Serialize="Required Public" />

    <Namespace Name="System.Collections.ObjectModel" >
      <TypeInstantiation Name="ObservableCollection"
            Arguments="ContosoClient.DataModel.ProductItem" Serialize="Public" />
      <TypeInstantiation Name="ReadOnlyObservableCollection"
            Arguments="ContosoClient.DataModel.ProductGroup" Serialize="Public" />
    </Namespace>
  </Application>
</Directives>
```

## <a name="the-structure-of-a-runtime-directives-file"></a><span data-ttu-id="f06a2-105">La struttura di un file di direttive di runtime</span><span class="sxs-lookup"><span data-stu-id="f06a2-105">The structure of a runtime directives file</span></span>

<span data-ttu-id="f06a2-106">Il file di direttive di runtime usa lo spazio dei nomi `http://schemas.microsoft.com/netfx/2013/01/metadata`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-106">The runtime directives file uses the `http://schemas.microsoft.com/netfx/2013/01/metadata` namespace.</span></span>

<span data-ttu-id="f06a2-107">L'elemento radice è l'elemento [Directives](directives-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="f06a2-107">The root element is the [Directives](directives-element-net-native.md) element.</span></span> <span data-ttu-id="f06a2-108">Può contenere zero o più elementi [Library](library-element-net-native.md) e zero o un elemento [Application](application-element-net-native.md), come illustrato nella struttura seguente.</span><span class="sxs-lookup"><span data-stu-id="f06a2-108">It can contain zero or more [Library](library-element-net-native.md) elements, and zero or one [Application](application-element-net-native.md) element, as shown in the following structure.</span></span> <span data-ttu-id="f06a2-109">Gli attributi dell'elemento [Application](application-element-net-native.md) possono definire criteri di reflection di runtime a livello di applicazione oppure possono fungere da contenitore per gli elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="f06a2-109">The attributes of the [Application](application-element-net-native.md) element can define application-wide runtime reflection policy, or it can serve as a container for child elements.</span></span> <span data-ttu-id="f06a2-110">L'elemento [Library](library-element-net-native.md), invece, è semplicemente un contenitore.</span><span class="sxs-lookup"><span data-stu-id="f06a2-110">The [Library](library-element-net-native.md) element, on the other hand, is simply a container.</span></span> <span data-ttu-id="f06a2-111">Gli elementi figlio degli elementi [Application](application-element-net-native.md) e [Library](library-element-net-native.md) definiscono i tipi, i metodi, i campi, le proprietà e gli eventi disponibili per la reflection.</span><span class="sxs-lookup"><span data-stu-id="f06a2-111">The children of the [Application](application-element-net-native.md) and [Library](library-element-net-native.md) elements define the types, methods, fields, properties, and events that are available for reflection.</span></span>

<span data-ttu-id="f06a2-112">Per le informazioni di riferimento, scegliere gli elementi dalla struttura seguente o vedere [Elementi direttiva di runtime](runtime-directive-elements.md).</span><span class="sxs-lookup"><span data-stu-id="f06a2-112">For reference information, choose elements from the following structure or see [Runtime Directive Elements](runtime-directive-elements.md).</span></span> <span data-ttu-id="f06a2-113">Nella seguente gerarchia, i puntini di sospensione contrassegnano una struttura ricorsiva.</span><span class="sxs-lookup"><span data-stu-id="f06a2-113">In the following hierarchy, the ellipsis marks a recursive structure.</span></span> <span data-ttu-id="f06a2-114">Le informazioni tra parentesi quadre indicano se tale elemento è facoltativo oppure obbligatorio e, se viene usato, il numero di istanze consentito (una o molte).</span><span class="sxs-lookup"><span data-stu-id="f06a2-114">The information in brackets indicates whether that element is optional or required, and if it is used, how many instances (one or many) are allowed.</span></span>

- <span data-ttu-id="f06a2-115">[Directives](directives-element-net-native.md) [1:1]</span><span class="sxs-lookup"><span data-stu-id="f06a2-115">[Directives](directives-element-net-native.md) [1:1]</span></span>
  - <span data-ttu-id="f06a2-116">[Application](application-element-net-native.md) [0:1]</span><span class="sxs-lookup"><span data-stu-id="f06a2-116">[Application](application-element-net-native.md) [0:1]</span></span>
    - <span data-ttu-id="f06a2-117">[Assembly](assembly-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-117">[Assembly](assembly-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="f06a2-118">[Spazio dei nomi](namespace-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="f06a2-118">[Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="f06a2-119">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-119">.</span></span> <span data-ttu-id="f06a2-120">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-120">.</span></span>
      - <span data-ttu-id="f06a2-121">[Digitare](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="f06a2-121">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="f06a2-122">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-122">.</span></span> <span data-ttu-id="f06a2-123">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-123">.</span></span>
      - <span data-ttu-id="f06a2-124">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo generico costruito) [0: M].</span><span class="sxs-lookup"><span data-stu-id="f06a2-124">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="f06a2-125">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-125">.</span></span> <span data-ttu-id="f06a2-126">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-126">.</span></span>
    - <span data-ttu-id="f06a2-127">[Namespace](namespace-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-127">[Namespace](namespace-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="f06a2-128">[Spazio dei nomi](namespace-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="f06a2-128">[Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="f06a2-129">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-129">.</span></span> <span data-ttu-id="f06a2-130">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-130">.</span></span>
      - <span data-ttu-id="f06a2-131">[Digitare](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="f06a2-131">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="f06a2-132">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-132">.</span></span> <span data-ttu-id="f06a2-133">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-133">.</span></span>
      - <span data-ttu-id="f06a2-134">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo generico costruito) [0: M].</span><span class="sxs-lookup"><span data-stu-id="f06a2-134">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="f06a2-135">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-135">.</span></span> <span data-ttu-id="f06a2-136">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-136">.</span></span>
    - <span data-ttu-id="f06a2-137">[Type](type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-137">[Type](type-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="f06a2-138">[Subtypes](subtypes-element-net-native.md) (sottoclassi del tipo contenitore) [O:1]</span><span class="sxs-lookup"><span data-stu-id="f06a2-138">[Subtypes](subtypes-element-net-native.md) (subclasses of the containing type) [O:1]</span></span>
      - <span data-ttu-id="f06a2-139">[Digitare](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="f06a2-139">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="f06a2-140">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-140">.</span></span> <span data-ttu-id="f06a2-141">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-141">.</span></span>
      - <span data-ttu-id="f06a2-142">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo generico costruito) [0: M].</span><span class="sxs-lookup"><span data-stu-id="f06a2-142">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="f06a2-143">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-143">.</span></span> <span data-ttu-id="f06a2-144">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-144">.</span></span>
      - <span data-ttu-id="f06a2-145">[AttributeImplies](attributeimplies-element-net-native.md) (il tipo contenitore è un attributo) [O:1]</span><span class="sxs-lookup"><span data-stu-id="f06a2-145">[AttributeImplies](attributeimplies-element-net-native.md) (containing type is an attribute) [O:1]</span></span>
      - <span data-ttu-id="f06a2-146">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-146">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="f06a2-147">[Method](method-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-147">[Method](method-element-net-native.md) [0:M]</span></span>
        - <span data-ttu-id="f06a2-148">[Parameter](parameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-148">[Parameter](parameter-element-net-native.md) [0:M]</span></span>
        - <span data-ttu-id="f06a2-149">[TypeParameter](typeparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-149">[TypeParameter](typeparameter-element-net-native.md) [0:M]</span></span>
        - <span data-ttu-id="f06a2-150">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-150">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="f06a2-151">[MethodInstantiation](methodinstantiation-element-net-native.md) (metodo generico costruito) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-151">[MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M]</span></span>
      - <span data-ttu-id="f06a2-152">[Property](property-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-152">[Property](property-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="f06a2-153">[Field](field-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-153">[Field](field-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="f06a2-154">[Event](event-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-154">[Event](event-element-net-native.md) [0:M]</span></span>
    - <span data-ttu-id="f06a2-155">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo generico costruito) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-155">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>
      - <span data-ttu-id="f06a2-156">[Digitare](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="f06a2-156">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="f06a2-157">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-157">.</span></span> <span data-ttu-id="f06a2-158">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-158">.</span></span>
      - <span data-ttu-id="f06a2-159">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo generico costruito) [0: M].</span><span class="sxs-lookup"><span data-stu-id="f06a2-159">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="f06a2-160">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-160">.</span></span> <span data-ttu-id="f06a2-161">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-161">.</span></span>
      - <span data-ttu-id="f06a2-162">[Method](method-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-162">[Method](method-element-net-native.md) [0:M]</span></span>
        - <span data-ttu-id="f06a2-163">[Parameter](parameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-163">[Parameter](parameter-element-net-native.md) [0:M]</span></span>
        - <span data-ttu-id="f06a2-164">[TypeParameter](typeparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-164">[TypeParameter](typeparameter-element-net-native.md) [0:M]</span></span>
        - <span data-ttu-id="f06a2-165">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-165">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="f06a2-166">[MethodInstantiation](methodinstantiation-element-net-native.md) (metodo generico costruito) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-166">[MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M]</span></span>
      - <span data-ttu-id="f06a2-167">[Property](property-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-167">[Property](property-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="f06a2-168">[Field](field-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-168">[Field](field-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="f06a2-169">[Event](event-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-169">[Event](event-element-net-native.md) [0:M]</span></span>
  - <span data-ttu-id="f06a2-170">[Library](library-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-170">[Library](library-element-net-native.md) [0:M]</span></span>
    - <span data-ttu-id="f06a2-171">[Assembly](assembly-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-171">[Assembly](assembly-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="f06a2-172">[Spazio dei nomi](namespace-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="f06a2-172">[Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="f06a2-173">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-173">.</span></span> <span data-ttu-id="f06a2-174">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-174">.</span></span>
      - <span data-ttu-id="f06a2-175">[Digitare](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="f06a2-175">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="f06a2-176">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-176">.</span></span> <span data-ttu-id="f06a2-177">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-177">.</span></span>
      - <span data-ttu-id="f06a2-178">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo generico costruito) [0: M].</span><span class="sxs-lookup"><span data-stu-id="f06a2-178">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="f06a2-179">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-179">.</span></span> <span data-ttu-id="f06a2-180">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-180">.</span></span>
    - <span data-ttu-id="f06a2-181">[Namespace](namespace-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-181">[Namespace](namespace-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="f06a2-182">[Spazio dei nomi](namespace-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="f06a2-182">[Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="f06a2-183">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-183">.</span></span> <span data-ttu-id="f06a2-184">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-184">.</span></span>
      - <span data-ttu-id="f06a2-185">[Digitare](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="f06a2-185">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="f06a2-186">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-186">.</span></span> <span data-ttu-id="f06a2-187">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-187">.</span></span>
      - <span data-ttu-id="f06a2-188">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo generico costruito) [0: M].</span><span class="sxs-lookup"><span data-stu-id="f06a2-188">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="f06a2-189">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-189">.</span></span> <span data-ttu-id="f06a2-190">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-190">.</span></span>
    - <span data-ttu-id="f06a2-191">[Type](type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-191">[Type](type-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="f06a2-192">[Subtypes](subtypes-element-net-native.md) (sottoclassi del tipo contenitore) [O:1]</span><span class="sxs-lookup"><span data-stu-id="f06a2-192">[Subtypes](subtypes-element-net-native.md) (subclasses of the containing type) [O:1]</span></span>
      - <span data-ttu-id="f06a2-193">[Digitare](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="f06a2-193">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="f06a2-194">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-194">.</span></span> <span data-ttu-id="f06a2-195">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-195">.</span></span>
      - <span data-ttu-id="f06a2-196">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo generico costruito) [0: M].</span><span class="sxs-lookup"><span data-stu-id="f06a2-196">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="f06a2-197">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-197">.</span></span> <span data-ttu-id="f06a2-198">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-198">.</span></span>
      - <span data-ttu-id="f06a2-199">[AttributeImplies](attributeimplies-element-net-native.md) (il tipo contenitore è un attributo) [O:1]</span><span class="sxs-lookup"><span data-stu-id="f06a2-199">[AttributeImplies](attributeimplies-element-net-native.md) (containing type is an attribute) [O:1]</span></span>
      - <span data-ttu-id="f06a2-200">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-200">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="f06a2-201">[Method](method-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-201">[Method](method-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="f06a2-202">[MethodInstantiation](methodinstantiation-element-net-native.md) (metodo generico costruito) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-202">[MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M]</span></span>
      - <span data-ttu-id="f06a2-203">[Property](property-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-203">[Property](property-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="f06a2-204">[Field](field-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-204">[Field](field-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="f06a2-205">[Event](event-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-205">[Event](event-element-net-native.md) [0:M]</span></span>
    - <span data-ttu-id="f06a2-206">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo generico costruito) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-206">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>
      - <span data-ttu-id="f06a2-207">[Digitare](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="f06a2-207">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="f06a2-208">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-208">.</span></span> <span data-ttu-id="f06a2-209">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-209">.</span></span>
      - <span data-ttu-id="f06a2-210">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo generico costruito) [0: M].</span><span class="sxs-lookup"><span data-stu-id="f06a2-210">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="f06a2-211">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-211">.</span></span> <span data-ttu-id="f06a2-212">.</span><span class="sxs-lookup"><span data-stu-id="f06a2-212">.</span></span>
      - <span data-ttu-id="f06a2-213">[Method](method-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-213">[Method](method-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="f06a2-214">[MethodInstantiation](methodinstantiation-element-net-native.md) (metodo generico costruito) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-214">[MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M]</span></span>
      - <span data-ttu-id="f06a2-215">[Property](property-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-215">[Property](property-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="f06a2-216">[Field](field-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-216">[Field](field-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="f06a2-217">[Event](event-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="f06a2-217">[Event](event-element-net-native.md) [0:M]</span></span>

<span data-ttu-id="f06a2-218">L'elemento [Application](application-element-net-native.md) può non avere attributi oppure può avere gli attributi dei criteri descritti nella sezione [Direttive e criteri di runtime](#Directives).</span><span class="sxs-lookup"><span data-stu-id="f06a2-218">The [Application](application-element-net-native.md) element can have no attributes, or it can have the policy attributes discussed in the [Runtime directive and policy section](#Directives).</span></span>

<span data-ttu-id="f06a2-219">Un elemento [Library](library-element-net-native.md) ha un solo attributo, `Name`, che specifica il nome di una libreria o di un assembly, senza l'estensione del file.</span><span class="sxs-lookup"><span data-stu-id="f06a2-219">A [Library](library-element-net-native.md) element has a single attribute, `Name`, that specifies the name of a library or assembly, without its file extension.</span></span> <span data-ttu-id="f06a2-220">Ad esempio, l'elemento [Library](library-element-net-native.md) seguente si applica a un assembly denominato Extensions.dll.</span><span class="sxs-lookup"><span data-stu-id="f06a2-220">For example, the following [Library](library-element-net-native.md) element applies to an assembly named Extensions.dll.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
     <!-- Child elements go here -->
  </Application>
  <Library Name="Extensions">
     <!-- Child elements go here -->
  </Library>
</Directives>
```

<a name="Directives"></a>

## <a name="runtime-directives-and-policy"></a><span data-ttu-id="f06a2-221">Direttive e criteri di runtime</span><span class="sxs-lookup"><span data-stu-id="f06a2-221">Runtime directives and policy</span></span>

<span data-ttu-id="f06a2-222">L'elemento [Application](application-element-net-native.md) stesso e gli elementi figlio degli elementi [Library](library-element-net-native.md) e [Application](application-element-net-native.md) esprimono criteri, ovvero definiscono il modo in cui un'app può applicare la reflection a un elemento del programma.</span><span class="sxs-lookup"><span data-stu-id="f06a2-222">The [Application](application-element-net-native.md) element itself and the child elements of the [Library](library-element-net-native.md) and [Application](application-element-net-native.md) elements express policy; that is, they define the way in which an app can apply reflection to a program element.</span></span> <span data-ttu-id="f06a2-223">Il tipo di criterio è definito da un attributo dell'elemento (ad esempio, `Serialize`).</span><span class="sxs-lookup"><span data-stu-id="f06a2-223">The policy type is defined by an attribute of the element (for example, `Serialize`).</span></span> <span data-ttu-id="f06a2-224">Il valore di criterio è definito dal valore dell'attributo (ad esempio, `Serialize="Required"`).</span><span class="sxs-lookup"><span data-stu-id="f06a2-224">The policy value is defined by the attribute’s value (for example, `Serialize="Required"`).</span></span>

<span data-ttu-id="f06a2-225">Qualsiasi criterio specificato da un attributo di un elemento si applica a tutti gli elementi figlio che non specificano un valore per tale criterio.</span><span class="sxs-lookup"><span data-stu-id="f06a2-225">Any policy specified by an attribute of an element applies to all child elements that don’t specify a value for that policy.</span></span> <span data-ttu-id="f06a2-226">Ad esempio, se vengono specificati criteri da un elemento [Type](type-element-net-native.md), tali criteri si applicano a tutti i tipi e membri contenuti per i quali non sono stati esplicitamente specificati i criteri.</span><span class="sxs-lookup"><span data-stu-id="f06a2-226">For example, if a policy is specified by a [Type](type-element-net-native.md) element, that policy applies to all contained types and members for which a policy is not explicitly specified.</span></span>

<span data-ttu-id="f06a2-227">I criteri che possono essere espressi dagli elementi [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md) e [Type](type-element-net-native.md) differiscono da quelli che possono essere espressi per i singoli membri (dagli elementi [Method](method-element-net-native.md), [Property](property-element-net-native.md), [Field](field-element-net-native.md) ed [Event](event-element-net-native.md)).</span><span class="sxs-lookup"><span data-stu-id="f06a2-227">The policy that can be expressed by the [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md), and [Type](type-element-net-native.md) elements differs from the policy that can be expressed for individual members (by the [Method](method-element-net-native.md), [Property](property-element-net-native.md), [Field](field-element-net-native.md), and [Event](event-element-net-native.md) elements).</span></span>

### <a name="specifying-policy-for-assemblies-namespaces-and-types"></a><span data-ttu-id="f06a2-228">Specifica di criteri per assembly, spazi dei nomi e tipi</span><span class="sxs-lookup"><span data-stu-id="f06a2-228">Specifying policy for assemblies, namespaces, and types</span></span>

<span data-ttu-id="f06a2-229">Gli elementi [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md) e [Type](type-element-net-native.md) supportano i tipi di criteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="f06a2-229">The [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md), and [Type](type-element-net-native.md) elements support the following policy types:</span></span>

- <span data-ttu-id="f06a2-230">`Activate`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-230">`Activate`.</span></span> <span data-ttu-id="f06a2-231">Controlla l'accesso in fase di esecuzione ai costruttori per abilitare l'attivazione di istanze.</span><span class="sxs-lookup"><span data-stu-id="f06a2-231">Controls runtime access to constructors, to enable activation of instances.</span></span>

- <span data-ttu-id="f06a2-232">`Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-232">`Browse`.</span></span> <span data-ttu-id="f06a2-233">Controlla le query per le informazioni sugli elementi di programma, ma non abilita l'accesso in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f06a2-233">Controls querying for information about program elements but does not enable any runtime access.</span></span>

- <span data-ttu-id="f06a2-234">`Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-234">`Dynamic`.</span></span> <span data-ttu-id="f06a2-235">Controlla l'accesso in fase di esecuzione a tutti i membri dei tipi, inclusi costruttori, metodi, campi, proprietà ed eventi, per abilitare la programmazione dinamica.</span><span class="sxs-lookup"><span data-stu-id="f06a2-235">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>

- <span data-ttu-id="f06a2-236">`Serialize`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-236">`Serialize`.</span></span> <span data-ttu-id="f06a2-237">Controlla l'accesso in fase di esecuzione ai costruttori, ai campi e alle proprietà per abilitare la serializzazione e la deserializzazione delle istanze del tipo da parte di librerie di terze parti, ad esempio il serializzatore JSON di Newtonsoft.</span><span class="sxs-lookup"><span data-stu-id="f06a2-237">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and serialized by third-party libraries such as the Newtonsoft JSON serializer.</span></span>

- <span data-ttu-id="f06a2-238">`DataContractSerializer`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-238">`DataContractSerializer`.</span></span> <span data-ttu-id="f06a2-239">Controlla i criteri per la serializzazione che usano la classe <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f06a2-239">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>

- <span data-ttu-id="f06a2-240">`DataContractJsonSerializer`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-240">`DataContractJsonSerializer`.</span></span> <span data-ttu-id="f06a2-241">Controlla i criteri per la serializzazione JSON che usano la classe <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f06a2-241">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>

- <span data-ttu-id="f06a2-242">`XmlSerializer`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-242">`XmlSerializer`.</span></span> <span data-ttu-id="f06a2-243">Controlla i criteri per la serializzazione XML che usano la classe <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f06a2-243">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>

- <span data-ttu-id="f06a2-244">`MarshalObject`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-244">`MarshalObject`.</span></span> <span data-ttu-id="f06a2-245">Criteri di controlli per effettuare il marshalling dei tipi di riferimento per WinRT e COM.</span><span class="sxs-lookup"><span data-stu-id="f06a2-245">Controls policy for marshaling reference types to WinRT and COM.</span></span>

- <span data-ttu-id="f06a2-246">`MarshalDelegate`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-246">`MarshalDelegate`.</span></span> <span data-ttu-id="f06a2-247">Controlla i criteri per effettuare il marshalling dei tipi delegati come puntatori a funzioni al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="f06a2-247">Controls policy for marshaling delegate types as function pointers to native code.</span></span>

- <span data-ttu-id="f06a2-248">`MarshalStructure` .</span><span class="sxs-lookup"><span data-stu-id="f06a2-248">`MarshalStructure` .</span></span> <span data-ttu-id="f06a2-249">Controlla i criteri per effettuare il marshalling delle strutture al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="f06a2-249">Controls policy for marshaling structures to native code.</span></span>

<span data-ttu-id="f06a2-250">Le impostazioni associate a questi tipi di criteri sono:</span><span class="sxs-lookup"><span data-stu-id="f06a2-250">The settings associated with these policy types are:</span></span>

- <span data-ttu-id="f06a2-251">`All`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-251">`All`.</span></span> <span data-ttu-id="f06a2-252">Attivare il criterio per tutti i tipi e membri che la catena di strumenti non riesce a rimuovere.</span><span class="sxs-lookup"><span data-stu-id="f06a2-252">Enable the policy for all types and members that the tool chain does not remove.</span></span>

- <span data-ttu-id="f06a2-253">`Auto`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-253">`Auto`.</span></span> <span data-ttu-id="f06a2-254">Usare il comportamento predefinito</span><span class="sxs-lookup"><span data-stu-id="f06a2-254">Use the default behavior.</span></span> <span data-ttu-id="f06a2-255">(non specificare un criterio è equivalente a impostare tale criterio su `Auto` a meno che tale criterio sia sottoposto a override, ad esempio da un elemento padre).</span><span class="sxs-lookup"><span data-stu-id="f06a2-255">(Not specifying a policy is equivalent to setting that policy to `Auto` unless that policy is overridden, for example by a parent element.)</span></span>

- <span data-ttu-id="f06a2-256">`Excluded`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-256">`Excluded`.</span></span> <span data-ttu-id="f06a2-257">Disattivare il criterio per l'elemento di programma.</span><span class="sxs-lookup"><span data-stu-id="f06a2-257">Disable the policy for the program element.</span></span>

- <span data-ttu-id="f06a2-258">`Public`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-258">`Public`.</span></span> <span data-ttu-id="f06a2-259">Attivare i criteri per i tipi o i membri pubblici, a meno che la catena di strumenti non determini che il tipo o il membro non è necessario e lo rimuova</span><span class="sxs-lookup"><span data-stu-id="f06a2-259">Enable the policy for public types or members unless the tool chain determines that the member is unnecessary and therefore removes it.</span></span> <span data-ttu-id="f06a2-260">(in quest'ultimo caso, è necessario usare `Required Public` per garantire che il membro venga mantenuto e abbia funzionalità di reflection.)</span><span class="sxs-lookup"><span data-stu-id="f06a2-260">(In the latter case, you must use `Required Public` to ensure that the member is kept and has reflection capabilities.)</span></span>

- <span data-ttu-id="f06a2-261">`PublicAndInternal`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-261">`PublicAndInternal`.</span></span> <span data-ttu-id="f06a2-262">Attivare il criterio per i tipi o membri pubblici e interni se la catena di strumenti non li rimuove.</span><span class="sxs-lookup"><span data-stu-id="f06a2-262">Enable the policy for public and internal types or members if the tool chain doesn't remove them.</span></span>

- <span data-ttu-id="f06a2-263">`Required Public`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-263">`Required Public`.</span></span> <span data-ttu-id="f06a2-264">Richiedere che la catena di strumenti mantenga i tipi e i membri pubblici, indipendentemente dal fatto che vengano usati o no, e attivare i relativi criteri.</span><span class="sxs-lookup"><span data-stu-id="f06a2-264">Require the tool chain to keep public types and members whether or not they are used, and enable the policy for them.</span></span>

- <span data-ttu-id="f06a2-265">`Required PublicAndInternal`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-265">`Required PublicAndInternal`.</span></span> <span data-ttu-id="f06a2-266">Richiedere che la catena di strumenti mantenga i tipi e i membri pubblici e interni, indipendentemente dal fatto che vengano usati o no, e attivare i relativi criteri.</span><span class="sxs-lookup"><span data-stu-id="f06a2-266">Require the tool chain to keep both public and internal types and members whether or not they are used, and enable the policy for them.</span></span>

- <span data-ttu-id="f06a2-267">`Required All`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-267">`Required All`.</span></span> <span data-ttu-id="f06a2-268">Richiedere che la catena di strumenti mantenga tutti i tipi e i membri, indipendentemente dal fatto che vengano usati o no, e attivare i relativi criteri.</span><span class="sxs-lookup"><span data-stu-id="f06a2-268">Require the tool chain to keep all types and members whether or not they are used, and enable the policy for them.</span></span>

<span data-ttu-id="f06a2-269">Il seguente file di direttive di runtime, ad esempio, definisce i criteri per tutti i tipi e membri nell'assembly DataClasses.dll.</span><span class="sxs-lookup"><span data-stu-id="f06a2-269">For example, the following runtime directives file defines policy for all types and members in the assembly DataClasses.dll.</span></span> <span data-ttu-id="f06a2-270">Consente la reflection per la serializzazione di tutte le proprietà pubbliche, consente di cercare tutti i tipi e membri del tipo, consente l'attivazione per tutti i tipi (a causa dell'attributo `Dynamic`) e abilita la reflection per tutti i tipi e membri pubblici.</span><span class="sxs-lookup"><span data-stu-id="f06a2-270">It enables reflection for serialization of all public properties, enables browsing for all types and type members, enables activation for all types (because of the `Dynamic` attribute), and enables reflection for all public types and members.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public"
                Browse="All" Activate="PublicAndInternal"
                Dynamic="Public"  />
   </Application>
   <Library Name="UtilityLibrary">
     <!-- Child elements go here -->
   </Library>
</Directives>
```

### <a name="specifying-policy-for-members"></a><span data-ttu-id="f06a2-271">Specifica di criteri per i membri</span><span class="sxs-lookup"><span data-stu-id="f06a2-271">Specifying policy for members</span></span>

<span data-ttu-id="f06a2-272">Gli elementi [Property](property-element-net-native.md) e [Field](field-element-net-native.md) supportano i tipi di criteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="f06a2-272">The [Property](property-element-net-native.md) and [Field](field-element-net-native.md) elements support the following policy types:</span></span>

- <span data-ttu-id="f06a2-273">`Browse`: controlla le query per le informazioni su questo membro, ma non abilita l'accesso in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f06a2-273">`Browse` - Controls querying for information about this member but does not enable any runtime access.</span></span>

- <span data-ttu-id="f06a2-274">`Dynamic`: controlla l'accesso in fase di esecuzione a tutti i membri dei tipi, inclusi costruttori, metodi, campi, proprietà ed eventi, per abilitare la programmazione dinamica.</span><span class="sxs-lookup"><span data-stu-id="f06a2-274">`Dynamic` - Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span> <span data-ttu-id="f06a2-275">Controlla anche la ricerca di informazioni sul tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="f06a2-275">Also controls querying for information about the containing type.</span></span>

- <span data-ttu-id="f06a2-276">`Serialize`: controlla l'accesso in fase di esecuzione al membro per abilitare istanze di tipi da serializzare e deserializzare da parte di librerie quali il serializzatore JSON di Newtonsoft.</span><span class="sxs-lookup"><span data-stu-id="f06a2-276">`Serialize` - Controls runtime access to the member to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span> <span data-ttu-id="f06a2-277">Questi criteri possono essere applicati a costruttori, campi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="f06a2-277">This policy can be applied to constructors, fields, and properties.</span></span>

<span data-ttu-id="f06a2-278">Gli elementi [Method](method-element-net-native.md) ed [Event](event-element-net-native.md) supportano i tipi di criteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="f06a2-278">The [Method](method-element-net-native.md) and [Event](event-element-net-native.md) elements support the following policy types:</span></span>

- <span data-ttu-id="f06a2-279">`Browse`: controlla le query per le informazioni su questo membro, ma non abilita l'accesso in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f06a2-279">`Browse` - Controls querying for information about this member but doesn’t enable any runtime access.</span></span>

- <span data-ttu-id="f06a2-280">`Dynamic`: controlla l'accesso in fase di esecuzione a tutti i membri dei tipi, inclusi costruttori, metodi, campi, proprietà ed eventi, per abilitare la programmazione dinamica.</span><span class="sxs-lookup"><span data-stu-id="f06a2-280">`Dynamic` - Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span> <span data-ttu-id="f06a2-281">Controlla anche la ricerca di informazioni sul tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="f06a2-281">Also controls querying for information about the containing type.</span></span>

 <span data-ttu-id="f06a2-282">Le impostazioni associate a questi tipi di criteri sono:</span><span class="sxs-lookup"><span data-stu-id="f06a2-282">The settings associated with these policy types are:</span></span>

- <span data-ttu-id="f06a2-283">`Auto`: usare il comportamento predefinito</span><span class="sxs-lookup"><span data-stu-id="f06a2-283">`Auto` - Use the default behavior.</span></span> <span data-ttu-id="f06a2-284">(non specificare un criterio equivale a impostare tale criterio su `Auto` a meno che un elemento esegua l'override).</span><span class="sxs-lookup"><span data-stu-id="f06a2-284">(Not specifying a policy is equivalent to setting that policy to `Auto` unless something overrides it.)</span></span>

- <span data-ttu-id="f06a2-285">`Excluded`: non includere mai i metadati per il membro.</span><span class="sxs-lookup"><span data-stu-id="f06a2-285">`Excluded` - Never include metadata for the member.</span></span>

- <span data-ttu-id="f06a2-286">`Included`: abilitare il criterio se il tipo padre è presente nell'output.</span><span class="sxs-lookup"><span data-stu-id="f06a2-286">`Included` - Enable the policy if the parent type is present in the output.</span></span>

- <span data-ttu-id="f06a2-287">`Required`: richiedere che la catena di strumenti conservi questo membro anche se sembra non essere in uso e abilitare i relativi criteri.</span><span class="sxs-lookup"><span data-stu-id="f06a2-287">`Required` - Require the tool chain to keep this member even if appears to be unused, and enable policy for it.</span></span>

## <a name="runtime-directives-file-semantics"></a><span data-ttu-id="f06a2-288">Semantica dei file di runtime direttive</span><span class="sxs-lookup"><span data-stu-id="f06a2-288">Runtime directives file semantics</span></span>

<span data-ttu-id="f06a2-289">È possibile definire criteri contemporaneamente per gli elementi di livello più alto e più basso.</span><span class="sxs-lookup"><span data-stu-id="f06a2-289">Policy can be defined simultaneously for both higher-level and lower-level elements.</span></span> <span data-ttu-id="f06a2-290">Ad esempio, è possibile definire dei criteri per un assembly e per alcuni dei tipi di contenuti in tale assembly.</span><span class="sxs-lookup"><span data-stu-id="f06a2-290">For example, policy can be defined for an assembly, and for some of the types contained in that assembly.</span></span> <span data-ttu-id="f06a2-291">Se non è rappresentato un particolare elemento di livello inferiore, esso eredita i criteri del padre.</span><span class="sxs-lookup"><span data-stu-id="f06a2-291">If a particular lower-level element is not represented, it inherits the policy of its parent.</span></span> <span data-ttu-id="f06a2-292">Ad esempio, se è presente un elemento `Assembly`, ma gli elementi `Type` sono assenti, il criterio specificato nell'elemento `Assembly` viene applicato a ciascun tipo nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="f06a2-292">For example, if an `Assembly` element is present but `Type` elements are not, the policy specified in the `Assembly` element applies to each type in the assembly.</span></span> <span data-ttu-id="f06a2-293">Più elementi possono anche applicare criteri allo stesso elemento di programma.</span><span class="sxs-lookup"><span data-stu-id="f06a2-293">Multiple elements can also apply policy to the same program element.</span></span> <span data-ttu-id="f06a2-294">Ad esempio, elementi [Assembly](assembly-element-net-native.md) separati potrebbero definire lo stesso elemento di criteri per lo stesso assembly in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="f06a2-294">For example, separate [Assembly](assembly-element-net-native.md) elements might define the same policy element for the same assembly differently.</span></span> <span data-ttu-id="f06a2-295">Le sezioni seguenti spiegano come risolvere il criterio per un determinato tipo in questi casi.</span><span class="sxs-lookup"><span data-stu-id="f06a2-295">The following sections explain how the policy for a particular type is resolved in those cases.</span></span>

<span data-ttu-id="f06a2-296">Un elemento [Type](type-element-net-native.md) o [Method](method-element-net-native.md) di un tipo o un metodo generico applica i relativi criteri a tutte le istanze che non hanno criteri propri.</span><span class="sxs-lookup"><span data-stu-id="f06a2-296">A [Type](type-element-net-native.md) or [Method](method-element-net-native.md) element of a generic type or method applies its policy to all instantiations that do not have their own policy.</span></span> <span data-ttu-id="f06a2-297">Ad esempio, un elemento `Type` che specifica i criteri per <xref:System.Collections.Generic.List%601> si applica a tutte le istanze costruite di tale tipo generico, a meno che non venga eseguito l'override per un particolare tipo generico costruito (come `List<Int32>`) da un elemento `TypeInstantiation`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-297">For example, a `Type` element that specifies policy for <xref:System.Collections.Generic.List%601> applies to all constructed instances of that generic type, unless it's overridden for a particular constructed generic type (such as a `List<Int32>`) by a `TypeInstantiation` element.</span></span> <span data-ttu-id="f06a2-298">In caso contrario, gli elementi definiscono i criteri per l'elemento di programma denominato.</span><span class="sxs-lookup"><span data-stu-id="f06a2-298">Otherwise, elements define policy for the program element named.</span></span>

<span data-ttu-id="f06a2-299">Quando un elemento è ambiguo, il motore ricerca corrispondenze e, se ne trova di esatte, le usa.</span><span class="sxs-lookup"><span data-stu-id="f06a2-299">When an element is ambiguous, the engine looks for matches, and if it finds an exact match, it will use it.</span></span> <span data-ttu-id="f06a2-300">Se trova più corrispondenze, si riceverà un avviso o un errore.</span><span class="sxs-lookup"><span data-stu-id="f06a2-300">If it finds multiple matches, there will be a warning or error.</span></span>

### <a name="if-two-directives-apply-policy-to-the-same-program-element"></a><span data-ttu-id="f06a2-301">Se due direttive applicano criteri allo stesso elemento di programma</span><span class="sxs-lookup"><span data-stu-id="f06a2-301">If two directives apply policy to the same program element</span></span>

<span data-ttu-id="f06a2-302">Se due elementi in diversi file di direttive di runtime provano a impostare lo stesso tipo di criteri per lo stesso elemento di programma (ad esempio un tipo o assembly) su valori diversi, il conflitto viene risolto come segue:</span><span class="sxs-lookup"><span data-stu-id="f06a2-302">If two elements in different runtime directives files try to set the same policy type for the same program element (such as an assembly or type) to different values, the conflict is resolved as follows:</span></span>

1. <span data-ttu-id="f06a2-303">Se l'elemento `Excluded` è presente, ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="f06a2-303">If the `Excluded` element is present, it has precedence.</span></span>

2. <span data-ttu-id="f06a2-304">`Required` ha la precedenza su non `Required`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-304">`Required` has precedence over not `Required`.</span></span>

3. <span data-ttu-id="f06a2-305">`All` ha la precedenza su `PublicAndInternal`, che a sua volta ha la precedenza su `Public`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-305">`All` has precedence over `PublicAndInternal`, which has precedence over `Public`.</span></span>

4. <span data-ttu-id="f06a2-306">Qualsiasi impostazione esplicita ha la precedenza su `Auto`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-306">Any explicit setting has precedence over `Auto`.</span></span>

<span data-ttu-id="f06a2-307">Ad esempio, se un singolo progetto include i due file di direttive di runtime seguenti, i criteri di serializzazione per DataClasses.dll vengono impostati su `Required Public` e `All`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-307">For example, if a single project includes the following two runtime directives files, the serialization policy for DataClasses.dll is set to both `Required Public` and `All`.</span></span> <span data-ttu-id="f06a2-308">In questo caso, il criterio di serializzazione sarebbe risolto come `Required All`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-308">In this case, the serialization policy would be resolved as `Required All`.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public"/>
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="All" />
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

<span data-ttu-id="f06a2-309">Tuttavia, se due direttive in un unico file di direttive di runtime prova a impostare lo stesso tipo di criteri per l'elemento del programma stesso, lo strumento di definizione di schema XML visualizza un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="f06a2-309">However, if two directives in a single runtime directives file try to set the same policy type for the same program element, the XML Scheme Definition tool displays an error message.</span></span>

### <a name="if-child-and-parent-elements-apply-the-same-policy-type"></a><span data-ttu-id="f06a2-310">Se gli elementi figlio e padre applicano lo stesso tipo di criteri</span><span class="sxs-lookup"><span data-stu-id="f06a2-310">If child and parent elements apply the same policy type</span></span>

<span data-ttu-id="f06a2-311">Gli elementi figlio eseguono l'override dei relativi elementi padre, inclusa l'impostazione `Excluded`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-311">Child elements override their parent elements, including the `Excluded` setting.</span></span> <span data-ttu-id="f06a2-312">L'override è il motivo principale per cui è preferibile specificare `Auto`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-312">Overriding is the main reason you would want to specify `Auto`.</span></span>

<span data-ttu-id="f06a2-313">Nell'esempio seguente, l'impostazione dei criteri di serializzazione per tutto quanto presente in `DataClasses` ma assente in `DataClasses.ViewModels` corrisponderebbe a `Required Public`, e tutto quanto presente sia in `DataClasses` sia in `DataClasses.ViewModels` corrisponderebbe a `All`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-313">In the following example, the serialization policy setting for everything in `DataClasses` that’s not in `DataClasses.ViewModels` would be `Required Public`, and everything that's in both `DataClasses` and `DataClasses.ViewModels` would be `All`.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public" >
         <Namespace Name="DataClasses.ViewModels" Serialize="All" />
      </Assembly>
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

### <a name="if-open-generics-and-instantiated-elements-apply-the-same-policy-type"></a><span data-ttu-id="f06a2-314">Se i generics aperti e gli elementi di un'istanza applicano lo stesso tipo di criteri</span><span class="sxs-lookup"><span data-stu-id="f06a2-314">If open generics and instantiated elements apply the same policy type</span></span>

<span data-ttu-id="f06a2-315">Nell'esempio seguente, a `Dictionary<int,int>` viene assegnato il criterio `Browse` solo se il motore ha un motivo differente per assegnare il criterio `Browse` (che altrimenti sarebbe il comportamento predefinito). Per qualsiasi altra istanza di <xref:System.Collections.Generic.Dictionary%602> sarà possibile esplorare tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="f06a2-315">In the following example, `Dictionary<int,int>` is assigned the `Browse` policy only if the engine has another reason to give it the `Browse` policy (which would otherwise be the default behavior); every other instantiation of <xref:System.Collections.Generic.Dictionary%602> will have all of its members browsable.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public" >
         <Namespace Name="DataClasses.ViewModels" Serialize="All" />
      </Assembly>
      <Namespace Name="DataClasses.Generics" />
      <Type Name="Dictionary" Browse="All" />
      <TypeInstantiation Name="Dictionary"
                         Arguments="System.Int32,System.Int32" Browse="Auto" />
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

### <a name="how-policy-is-inferred"></a><span data-ttu-id="f06a2-316">Come vengono dedotti i criteri</span><span class="sxs-lookup"><span data-stu-id="f06a2-316">How policy is inferred</span></span>

<span data-ttu-id="f06a2-317">Ogni tipo di criteri ha un diverso insieme di regole che determinano in che modo la presenza di tale tipo di criterio ha effetto su altri costrutti.</span><span class="sxs-lookup"><span data-stu-id="f06a2-317">Each policy type has a different set of rules that determine how the presence of that policy type affects other constructs.</span></span>

#### <a name="the-effect-of-browse-policy"></a><span data-ttu-id="f06a2-318">Effetto del criterio Browse</span><span class="sxs-lookup"><span data-stu-id="f06a2-318">The effect of Browse policy</span></span>

<span data-ttu-id="f06a2-319">L'applicazione del criterio `Browse` a un tipo implica le seguenti modifiche:</span><span class="sxs-lookup"><span data-stu-id="f06a2-319">Applying the `Browse` policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="f06a2-320">Il tipo di base del tipo viene contrassegnato con il criterio `Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-320">The base type of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="f06a2-321">Se il tipo è un generico istanziato, la versione priva di istanze del tipo è contrassegnata con il criterio `Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-321">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="f06a2-322">Se il tipo è un delegato, il metodo `Invoke` del tipo è contrassegnato con il criterio `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-322">If the type is a delegate, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="f06a2-323">Ciascuna interfaccia del tipo viene contrassegnata con il criterio `Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-323">Each interface of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="f06a2-324">Il tipo di ciascun attributo applicato al tipo è contrassegnato con il criterio `Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-324">The type of each attribute applied to the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="f06a2-325">Se il tipo è generico, ogni tipo di vincolo è contrassegnato con il criterio `Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-325">If the type is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="f06a2-326">Se il tipo è generico, i tipi su cui viene creata un'istanza del tipo sono contrassegnati con il criterio `Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-326">If the type is generic, the types over which the type is instantiated are marked with the `Browse` policy.</span></span>

<span data-ttu-id="f06a2-327">L'applicazione del criterio `Browse` a un metodo implica le seguenti modifiche:</span><span class="sxs-lookup"><span data-stu-id="f06a2-327">Applying the `Browse` policy to a method involves the following policy changes:</span></span>

- <span data-ttu-id="f06a2-328">Ogni tipo di parametro del metodo è contrassegnato con il criterio `Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-328">Each parameter type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="f06a2-329">Il tipo restituito del metodo è contrassegnato con il criterio `Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-329">The return type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="f06a2-330">Il tipo contenitore del metodo è contrassegnato con il criterio `Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-330">The containing type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="f06a2-331">Se il metodo è un metodo generico istanziato, il metodo generico privo di istanze è contrassegnato con il criterio `Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-331">If the method is an instantiated generic method, the uninstantiated generic method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="f06a2-332">Il tipo di ciascun attributo applicato al metodo è contrassegnato con il criterio `Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-332">The type of each attribute applied to the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="f06a2-333">Se il metodo è generico, ogni tipo di vincolo è contrassegnato con il criterio `Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-333">If the method is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="f06a2-334">Se il metodo è generico, i tipi su cui viene creata un'istanza del metodo sono contrassegnati con il criterio `Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-334">If the method is generic, the types over which the method is instantiated are marked with the `Browse` policy.</span></span>

<span data-ttu-id="f06a2-335">L'applicazione del criterio `Browse` a un campo implica le seguenti modifiche:</span><span class="sxs-lookup"><span data-stu-id="f06a2-335">Applying the `Browse` policy to a field involves the following policy changes:</span></span>

- <span data-ttu-id="f06a2-336">Il tipo di ciascun attributo applicato al campo è contrassegnato con il criterio `Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-336">The type of each attribute applied to the field is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="f06a2-337">Il tipo del campo viene contrassegnato con il criterio `Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-337">The type of the field is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="f06a2-338">Il tipo al quale appartiene il campo viene contrassegnato con il criterio `Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-338">The type to which the field belongs is marked with the `Browse` policy.</span></span>

#### <a name="the-effect-of-dynamic-policy"></a><span data-ttu-id="f06a2-339">Effetto dei criteri Dynamic</span><span class="sxs-lookup"><span data-stu-id="f06a2-339">The effect of Dynamic policy</span></span>

<span data-ttu-id="f06a2-340">L'applicazione del criterio `Dynamic` a un tipo implica le seguenti modifiche:</span><span class="sxs-lookup"><span data-stu-id="f06a2-340">Applying the `Dynamic` policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="f06a2-341">Il tipo di base del tipo viene contrassegnato con il criterio `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-341">The base type of the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="f06a2-342">Se il tipo è un generico istanziato, la versione priva di istanze del tipo è contrassegnata con il criterio `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-342">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="f06a2-343">Se il tipo è un delegato, il metodo `Invoke` del tipo è contrassegnato con il criterio `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-343">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="f06a2-344">Ciascuna interfaccia del tipo viene contrassegnata con il criterio `Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-344">Each interface of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="f06a2-345">Il tipo di ciascun attributo applicato al tipo è contrassegnato con il criterio `Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-345">The type of each attribute applied to the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="f06a2-346">Se il tipo è generico, ogni tipo di vincolo è contrassegnato con il criterio `Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-346">If the type is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="f06a2-347">Se il tipo è generico, i tipi su cui viene creata un'istanza del tipo sono contrassegnati con il criterio `Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-347">If the type is generic, the types over which the type is instantiated are marked with the `Browse` policy.</span></span>

<span data-ttu-id="f06a2-348">L'applicazione del criterio `Dynamic` a un metodo implica le seguenti modifiche:</span><span class="sxs-lookup"><span data-stu-id="f06a2-348">Applying the `Dynamic` policy to a method involves the following policy changes:</span></span>

- <span data-ttu-id="f06a2-349">Ogni tipo di parametro del metodo è contrassegnato con il criterio `Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-349">Each parameter type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="f06a2-350">Il tipo restituito del metodo è contrassegnato con il criterio `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-350">The return type of the method is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="f06a2-351">Il tipo contenitore del metodo è contrassegnato con il criterio `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-351">The containing type of the method is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="f06a2-352">Se il metodo è un metodo generico istanziato, il metodo generico privo di istanze è contrassegnato con il criterio `Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-352">If the method is an instantiated generic method, the uninstantiated generic method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="f06a2-353">Il tipo di ciascun attributo applicato al metodo è contrassegnato con il criterio `Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-353">The type of each attribute applied to the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="f06a2-354">Se il metodo è generico, ogni tipo di vincolo è contrassegnato con il criterio `Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-354">If the method is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="f06a2-355">Se il metodo è generico, i tipi su cui viene creata un'istanza del metodo sono contrassegnati con il criterio `Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-355">If the method is generic, the types over which the method is instantiated are marked with the `Browse` policy.</span></span>

- <span data-ttu-id="f06a2-356">Il metodo può essere richiamato da `MethodInfo.Invoke` e la creazione del delegato è resa possibile da <xref:System.Reflection.MethodInfo.CreateDelegate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f06a2-356">The method can be invoked by `MethodInfo.Invoke`, and delegate creation becomes possible by <xref:System.Reflection.MethodInfo.CreateDelegate%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="f06a2-357">L'applicazione del criterio `Dynamic` a un campo implica le seguenti modifiche:</span><span class="sxs-lookup"><span data-stu-id="f06a2-357">Applying the `Dynamic` policy to a field involves the following policy changes:</span></span>

- <span data-ttu-id="f06a2-358">Il tipo di ciascun attributo applicato al campo è contrassegnato con il criterio `Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-358">The type of each attribute applied to the field is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="f06a2-359">Il tipo del campo viene contrassegnato con il criterio `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-359">The type of the field is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="f06a2-360">Il tipo al quale appartiene il campo viene contrassegnato con il criterio `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-360">The type to which the field belongs is marked with the `Dynamic` policy.</span></span>

#### <a name="the-effect-of-activation-policy"></a><span data-ttu-id="f06a2-361">Effetto del criterio Activation</span><span class="sxs-lookup"><span data-stu-id="f06a2-361">The effect of Activation policy</span></span>

<span data-ttu-id="f06a2-362">L'applicazione del criterio Activation a un tipo implica le seguenti modifiche:</span><span class="sxs-lookup"><span data-stu-id="f06a2-362">Applying the Activation policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="f06a2-363">Se il tipo è un generico istanziato, la versione priva di istanze del tipo è contrassegnata con il criterio `Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-363">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="f06a2-364">Se il tipo è un delegato, il metodo `Invoke` del tipo è contrassegnato con il criterio `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-364">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="f06a2-365">I costruttori del tipo vengono contrassegnati con il criterio `Activation`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-365">Constructors of the type are marked with the `Activation` policy.</span></span>

<span data-ttu-id="f06a2-366">L'applicazione del criterio `Activation` a un metodo implica le seguenti modifiche:</span><span class="sxs-lookup"><span data-stu-id="f06a2-366">Applying the `Activation` policy to a method involves the following policy change:</span></span>

- <span data-ttu-id="f06a2-367">Il costruttore può essere richiamato dai metodi <xref:System.Reflection.ConstructorInfo.Invoke%2A?displayProperty=nameWithType> e <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f06a2-367">The constructor can be invoked by the <xref:System.Reflection.ConstructorInfo.Invoke%2A?displayProperty=nameWithType> and <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="f06a2-368">Per i metodi, il criterio `Activation` influisce solo sui costruttori.</span><span class="sxs-lookup"><span data-stu-id="f06a2-368">For methods, the `Activation` policy affects constructors only.</span></span>

<span data-ttu-id="f06a2-369">L'applicazione del criterio `Activation` a un campo non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="f06a2-369">Applying the `Activation` policy to a field has no effect.</span></span>

#### <a name="the-effect-of-serialize-policy"></a><span data-ttu-id="f06a2-370">Effetto del criterio Serialize</span><span class="sxs-lookup"><span data-stu-id="f06a2-370">The effect of Serialize policy</span></span>

<span data-ttu-id="f06a2-371">Il criterio `Serialize` consente l'utilizzo dei serializzatori basati su reflection più comuni.</span><span class="sxs-lookup"><span data-stu-id="f06a2-371">The `Serialize` policy enables the use of common reflection-based serializers.</span></span> <span data-ttu-id="f06a2-372">Tuttavia, poiché gli schemi di accesso alla reflection esatti dei serializzatori non Microsoft non sono noti a Microsoft, questo criterio potrebbe non essere completamente efficace.</span><span class="sxs-lookup"><span data-stu-id="f06a2-372">However, because the exact reflection access patterns of non-Microsoft serializers are not known to Microsoft, this policy may not be entirely effective.</span></span>

<span data-ttu-id="f06a2-373">L'applicazione del criterio `Serialize` a un tipo implica le seguenti modifiche:</span><span class="sxs-lookup"><span data-stu-id="f06a2-373">Applying the `Serialize` policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="f06a2-374">Il tipo di base del tipo viene contrassegnato con il criterio `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-374">The base type of the type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="f06a2-375">Se il tipo è un generico istanziato, la versione priva di istanze del tipo è contrassegnata con il criterio `Browse`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-375">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="f06a2-376">Se il tipo è un delegato, il metodo `Invoke` del tipo è contrassegnato con il criterio `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-376">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="f06a2-377">Se il tipo è un'enumerazione, una matrice del tipo è contrassegnata con il criterio `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-377">If the type is an enumeration, an array of the type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="f06a2-378">Se il tipo implementa <xref:System.Collections.Generic.IEnumerable%601>, `T` viene contrassegnato con il criterio `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-378">If the type implements <xref:System.Collections.Generic.IEnumerable%601>, `T` is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="f06a2-379">Se il tipo è <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.Generic.IList%601>, <xref:System.Collections.Generic.ICollection%601>, <xref:System.Collections.Generic.IReadOnlyCollection%601> o <xref:System.Collections.Generic.IReadOnlyList%601>, `T[]` e <xref:System.Collections.Generic.List%601> vengono contrassegnati con il criterio `Serialize`, ma nessuno membro del tipo di interfaccia viene contrassegnato con il criterio `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-379">If the type is <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.Generic.IList%601>, <xref:System.Collections.Generic.ICollection%601>, <xref:System.Collections.Generic.IReadOnlyCollection%601>, or <xref:System.Collections.Generic.IReadOnlyList%601>, then `T[]` and <xref:System.Collections.Generic.List%601> marked with the `Serialize` policy., but no members of the interface type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="f06a2-380">Se il tipo è <xref:System.Collections.Generic.List%601>, nessun membro del tipo viene contrassegnato con il criterio `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-380">If the type is <xref:System.Collections.Generic.List%601>, no members of the type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="f06a2-381">Se il tipo è <xref:System.Collections.Generic.IDictionary%602>, <xref:System.Collections.Generic.Dictionary%602> viene contrassegnato con il criterio `Serialize`,</span><span class="sxs-lookup"><span data-stu-id="f06a2-381">If the type is <xref:System.Collections.Generic.IDictionary%602>, <xref:System.Collections.Generic.Dictionary%602> is marked with the `Serialize` policy.</span></span> <span data-ttu-id="f06a2-382">ma nessun membro del tipo viene contrassegnato con il criterio `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-382">but no members of the type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="f06a2-383">Se il tipo è <xref:System.Collections.Generic.Dictionary%602>, nessun membro del tipo viene contrassegnato con il criterio `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-383">If the type is <xref:System.Collections.Generic.Dictionary%602>, no members of the type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="f06a2-384">Se il tipo implementa <xref:System.Collections.Generic.IDictionary%602>, `TKey` e `TValue` vengono contrassegnati con il criterio `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-384">If the type implements <xref:System.Collections.Generic.IDictionary%602>, `TKey` and `TValue` are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="f06a2-385">Ogni costruttore, ogni funzione di accesso della proprietà e ogni campo è contrassegnato con il criterio `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-385">Each constructor, each property accessor, and each field is marked with the `Serialize` policy.</span></span>

<span data-ttu-id="f06a2-386">L'applicazione del criterio `Serialize` a un metodo implica le seguenti modifiche:</span><span class="sxs-lookup"><span data-stu-id="f06a2-386">Applying the `Serialize` policy to a method involves the following policy changes:</span></span>

- <span data-ttu-id="f06a2-387">Il tipo contenitore è contrassegnato con il criterio `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-387">The containing type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="f06a2-388">Il tipo restituito del metodo è contrassegnato con il criterio `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-388">The return type of the method is marked with the `Serialize` policy.</span></span>

<span data-ttu-id="f06a2-389">L'applicazione del criterio `Serialize` a un campo implica le seguenti modifiche:</span><span class="sxs-lookup"><span data-stu-id="f06a2-389">Applying the `Serialize` policy to a field involves the following policy changes:</span></span>

- <span data-ttu-id="f06a2-390">Il tipo contenitore è contrassegnato con il criterio `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-390">The containing type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="f06a2-391">Il tipo del campo viene contrassegnato con il criterio `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="f06a2-391">The type of the field is marked with the `Serialize` policy.</span></span>

#### <a name="the-effect-of-xmlserializer-datacontractserializer-and-datacontractjsonserializer-policies"></a><span data-ttu-id="f06a2-392">Effetto dei criteri XmlSerializer, DataContractSerializer e DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="f06a2-392">The effect of XmlSerializer, DataContractSerializer, and DataContractJsonSerializer policies</span></span>

<span data-ttu-id="f06a2-393">A differenza dei criteri di `Serialize`, progettati per i serializzatori basati su Reflection, i criteri <xref:System.Xml.Serialization.XmlSerializer>, <xref:System.Runtime.Serialization.DataContractSerializer>e <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> vengono utilizzati per abilitare un set di serializzatori noti alla catena di strumenti .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f06a2-393">Unlike the `Serialize` policy, which is intended for reflection-based serializers, the <xref:System.Xml.Serialization.XmlSerializer>, <xref:System.Runtime.Serialization.DataContractSerializer>, and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> policies are used to enable a set of serializers that are known to the .NET Native tool chain.</span></span> <span data-ttu-id="f06a2-394">Questi serializzatori non vengono implementati tramite reflection, ma l'insieme di tipi che possono essere serializzati in fase di esecuzione è determinato in modo simile come tipi soggetti a reflection.</span><span class="sxs-lookup"><span data-stu-id="f06a2-394">These serializers are not implemented by using reflection, but the set of types that can be serialized at run time is determined in a similar manner as types that are reflectable.</span></span>

<span data-ttu-id="f06a2-395">L'applicazione di uno di questi criteri a un tipo consente di serializzare il tipo con il serializzatore corrispondente.</span><span class="sxs-lookup"><span data-stu-id="f06a2-395">Applying one of these policies to a type enables the type to be serialized with the matching serializer.</span></span> <span data-ttu-id="f06a2-396">Inoltre, eventuali tipi che il motore di serializzazione determina come serializzabili saranno indicati come tali.</span><span class="sxs-lookup"><span data-stu-id="f06a2-396">Also, any types that the serialization engine can statically determine as needing serialization will also be serializable.</span></span>

<span data-ttu-id="f06a2-397">Questi criteri non hanno alcun effetto sui metodi o campi.</span><span class="sxs-lookup"><span data-stu-id="f06a2-397">These policies have no effect on methods or fields.</span></span>

<span data-ttu-id="f06a2-398">Per altre informazioni, vedere la sezione relativa alle differenze nei serializzatori in [Migrating Your Windows Store App to .NET Native](migrating-your-windows-store-app-to-net-native.md) (Migrazione dell'app di Windows Store a .NET Native).</span><span class="sxs-lookup"><span data-stu-id="f06a2-398">For more information, see the "Differences in Serializers" section in [Migrating Your Windows Store App to .NET Native](migrating-your-windows-store-app-to-net-native.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f06a2-399">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f06a2-399">See also</span></span>

- [<span data-ttu-id="f06a2-400">Elementi direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="f06a2-400">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="f06a2-401">Reflection e .NET Native</span><span class="sxs-lookup"><span data-stu-id="f06a2-401">Reflection and .NET Native</span></span>](reflection-and-net-native.md)
