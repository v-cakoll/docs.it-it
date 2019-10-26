---
title: Elementi (proprietà dinamica XElement)
ms.date: 10/22/2019
ms.topic: reference
apiname:
- XElement.Elements
apitype: Assembly
ms.openlocfilehash: 812adabd3bfb01fd9313ce3f35e6cb0a5e23344e
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920853"
---
# <a name="elements-xelement-dynamic-property"></a><span data-ttu-id="17daf-102">Elementi (proprietà dinamica XElement)</span><span class="sxs-lookup"><span data-stu-id="17daf-102">Elements (XElement dynamic property)</span></span>

<span data-ttu-id="17daf-103">Ottiene un indicizzatore usato per recuperare gli elementi figlio dell'elemento corrente che corrispondono al nome espanso specificato.</span><span class="sxs-lookup"><span data-stu-id="17daf-103">Gets an indexer used to retrieve the child elements of the current element that match the specified expanded name.</span></span>

## <a name="syntax"></a><span data-ttu-id="17daf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="17daf-104">Syntax</span></span>

```xaml
elem.Elements[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="17daf-105">Valore proprietà/valore restituito</span><span class="sxs-lookup"><span data-stu-id="17daf-105">Property value/return value</span></span>

<span data-ttu-id="17daf-106">Indicizzatore del tipo `IEnumerable<XElement> Item(String expandedName)`.</span><span class="sxs-lookup"><span data-stu-id="17daf-106">An indexer of the type `IEnumerable<XElement> Item(String expandedName)`.</span></span> <span data-ttu-id="17daf-107">Questo indicizzatore assume il nome espanso degli elementi figlio desiderati e restituisce gli elementi figlio corrispondenti in una raccolta <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>`.</span><span class="sxs-lookup"><span data-stu-id="17daf-107">This indexer takes the expanded name of the desired child elements and returns the matching child elements in an <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>` collection.</span></span>

## <a name="remarks"></a><span data-ttu-id="17daf-108">Note</span><span class="sxs-lookup"><span data-stu-id="17daf-108">Remarks</span></span>

<span data-ttu-id="17daf-109">Questa proprietà è equivalente al metodo <xref:System.Xml.Linq.XContainer.Elements(System.Xml.Linq.XName)?displayProperty=fullName> della classe <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="17daf-109">This property is equivalent to the <xref:System.Xml.Linq.XContainer.Elements(System.Xml.Linq.XName)?displayProperty=fullName> method of the <xref:System.Xml.Linq.XContainer> class.</span></span>

<span data-ttu-id="17daf-110">Gli elementi della raccolta restituita sono in ordine del documento dell'origine XML.</span><span class="sxs-lookup"><span data-stu-id="17daf-110">The elements in the returned collection are in XML source document order.</span></span>

<span data-ttu-id="17daf-111">Questa proprietà usa l'esecuzione posticipata.</span><span class="sxs-lookup"><span data-stu-id="17daf-111">This property uses deferred execution.</span></span>

## <a name="see-also"></a><span data-ttu-id="17daf-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17daf-112">See also</span></span>

- [<span data-ttu-id="17daf-113">Proprietà dinamiche della classe XElement</span><span class="sxs-lookup"><span data-stu-id="17daf-113">XElement class dynamic properties</span></span>](attribute-xelement-dynamic-property.md)
- [<span data-ttu-id="17daf-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="17daf-114">Element</span></span>](element-xelement-dynamic-property.md)
- [<span data-ttu-id="17daf-115">Discendenti</span><span class="sxs-lookup"><span data-stu-id="17daf-115">Descendants</span></span>](descendants-xelement-dynamic-property.md)
