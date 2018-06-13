---
title: Gestione di xml:space in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], whitespace processing
- xml:space attribute [XAML Services]
- whitespace processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: af971ad9ea74e123b939ff8d8488e4e45c5d4aed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563467"
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="086fd-102">Gestione di xml:space in XAML</span><span class="sxs-lookup"><span data-stu-id="086fd-102">xml:space Handling in XAML</span></span>
<span data-ttu-id="086fd-103">Il `xml:space` attributo è un attributo basato su XML che dichiara il comportamento di elaborazione degli spazi vuoti significativi all'interno di un elemento dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="086fd-103">The `xml:space` attribute is an XML-defined attribute that declares the significant whitespace processing behavior within an object element.</span></span> <span data-ttu-id="086fd-104">Questo comportamento è pertinente per tutto il contenuto (testo interno) all'interno dell'elemento in cui `xml:space` viene dichiarato e definisce l'ambito per gli elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="086fd-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="086fd-105">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="086fd-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 <span data-ttu-id="086fd-106">\- oppure -</span><span class="sxs-lookup"><span data-stu-id="086fd-106">\- or -</span></span>  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a><span data-ttu-id="086fd-107">Note</span><span class="sxs-lookup"><span data-stu-id="086fd-107">Remarks</span></span>  
 <span data-ttu-id="086fd-108">La definizione per il `xml:space` attributo in XAML, inclusi i due valori possibili è derivato da `xml:space` definito come "attributo speciale" dalle specifiche W3C per XML.</span><span class="sxs-lookup"><span data-stu-id="086fd-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>  
  
 <span data-ttu-id="086fd-109">Il valore predefinito di `xml:space` attributo è il valore letterale `"default"`.</span><span class="sxs-lookup"><span data-stu-id="086fd-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="086fd-110">Per il valore `"default"`, o se `xml:space` non è indicato, il comportamento di analisi degli spazi vuoti significativi è la gestione predefinita, come definito nell'argomento [elaborazione degli spazi vuoti in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="086fd-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant whitespace parsing is the default handling, as defined in the topic [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span></span>  
  
 <span data-ttu-id="086fd-111">Per mantenere gli spazi vuoti all'interno di contenuto dell'elemento oggetto, specificare `xml:space="preserve"` nell'elemento oggetto.</span><span class="sxs-lookup"><span data-stu-id="086fd-111">To preserve whitespace within object element content, specify `xml:space="preserve"` on that object element.</span></span>  
  
 <span data-ttu-id="086fd-112">Nella maggior parte delle interpretazioni, il `xml:space` gli effetti dell'attributo e il valore dell'attributo sono limitati agli elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="086fd-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>  
  
 <span data-ttu-id="086fd-113">Per una descrizione completa di spazi di elaborazione in XAML, vedere [elaborazione degli spazi vuoti in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="086fd-113">For a complete discussion of whitespace processing in XAML, see [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="086fd-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="086fd-114">See Also</span></span>  
 [<span data-ttu-id="086fd-115">Elaborazione degli spazi vuoti in XAML</span><span class="sxs-lookup"><span data-stu-id="086fd-115">Whitespace Processing in XAML</span></span>](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)  
 [<span data-ttu-id="086fd-116">Cenni preliminari su XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="086fd-116">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
