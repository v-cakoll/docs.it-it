---
title: Gestione di xml:space in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 8f860f5ee42b5c1df43c4ec2b1003408bc1c0d8e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458801"
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="9d7bd-102">Gestione di xml:space in XAML</span><span class="sxs-lookup"><span data-stu-id="9d7bd-102">xml:space Handling in XAML</span></span>
<span data-ttu-id="9d7bd-103">L'attributo `xml:space` è un attributo definito da XML che dichiara il comportamento di elaborazione degli spazi vuoti significativo all'interno di un elemento oggetto.</span><span class="sxs-lookup"><span data-stu-id="9d7bd-103">The `xml:space` attribute is an XML-defined attribute that declares the significant white-space processing behavior within an object element.</span></span> <span data-ttu-id="9d7bd-104">Questo comportamento è pertinente per tutto il contenuto (testo interno) contenuto all'interno dell'elemento in cui viene dichiarata `xml:space` e anche gli ambiti agli elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="9d7bd-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="9d7bd-105">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="9d7bd-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 <span data-ttu-id="9d7bd-106">\- oppure -</span><span class="sxs-lookup"><span data-stu-id="9d7bd-106">\- or -</span></span>  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a><span data-ttu-id="9d7bd-107">Note</span><span class="sxs-lookup"><span data-stu-id="9d7bd-107">Remarks</span></span>  
 <span data-ttu-id="9d7bd-108">La definizione per l'attributo `xml:space` in XAML, inclusi i due valori possibili, deriva da `xml:space` definito come "attributo speciale" da specifiche W3C per XML.</span><span class="sxs-lookup"><span data-stu-id="9d7bd-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>  
  
 <span data-ttu-id="9d7bd-109">Il valore predefinito dell'attributo `xml:space` è il valore letterale `"default"`.</span><span class="sxs-lookup"><span data-stu-id="9d7bd-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="9d7bd-110">Per il valore `"default"`o, se `xml:space` non è indicato, il comportamento di analisi dello spazio vuoto significativo è la gestione predefinita, come definito nell'argomento [elaborazione di spazi vuoti in XAML](whitespace-processing-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="9d7bd-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant white-space parsing is the default handling, as defined in the topic [White-space processing in XAML](whitespace-processing-in-xaml.md).</span></span>  
  
 <span data-ttu-id="9d7bd-111">Per mantenere lo spazio vuoto all'interno del contenuto dell'elemento oggetto, specificare `xml:space="preserve"` sull'elemento oggetto.</span><span class="sxs-lookup"><span data-stu-id="9d7bd-111">To preserve white space within object element content, specify `xml:space="preserve"` on that object element.</span></span>  
  
 <span data-ttu-id="9d7bd-112">Nella maggior parte delle interpretazioni, gli effetti degli attributi `xml:space` e il valore dell'attributo hanno come ambito gli elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="9d7bd-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>  
  
 <span data-ttu-id="9d7bd-113">Per una descrizione completa dell'elaborazione di spazi vuoti in XAML, vedere [elaborazione di spazi vuoti in XAML](whitespace-processing-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="9d7bd-113">For a complete discussion of white-space processing in XAML, see [White-space processing in XAML](whitespace-processing-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d7bd-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d7bd-114">See also</span></span>

- [<span data-ttu-id="9d7bd-115">Elaborazione di spazi vuoti in XAML</span><span class="sxs-lookup"><span data-stu-id="9d7bd-115">White-space processing in XAML</span></span>](whitespace-processing-in-xaml.md)
- [<span data-ttu-id="9d7bd-116">Cenni preliminari su XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="9d7bd-116">XAML Overview (WPF)</span></span>](../../desktop-wpf/fundamentals/xaml.md)
