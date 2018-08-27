---
title: Gestione di xml:space in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 051cb6b3a314509e9593ee570fd659098670e88b
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925857"
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="a6342-102">Gestione di xml:space in XAML</span><span class="sxs-lookup"><span data-stu-id="a6342-102">xml:space Handling in XAML</span></span>
<span data-ttu-id="a6342-103">Il `xml:space` un attributo definito in XML che dichiara il comportamento di un'elaborazione significativa gli spazi vuoti all'interno di un elemento oggetto.</span><span class="sxs-lookup"><span data-stu-id="a6342-103">The `xml:space` attribute is an XML-defined attribute that declares the significant white-space processing behavior within an object element.</span></span> <span data-ttu-id="a6342-104">Questo comportamento è rilevante per tutto il contenuto (testo interno) contenuto all'interno dell'elemento in cui `xml:space` viene dichiarato e definisce l'ambito per gli elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="a6342-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="a6342-105">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="a6342-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 <span data-ttu-id="a6342-106">\- oppure -</span><span class="sxs-lookup"><span data-stu-id="a6342-106">\- or -</span></span>  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a><span data-ttu-id="a6342-107">Note</span><span class="sxs-lookup"><span data-stu-id="a6342-107">Remarks</span></span>  
 <span data-ttu-id="a6342-108">La definizione per il `xml:space` attributo in XAML tra i due valori possibili è derivato da `xml:space` definito come "attributo speciale" da specifiche W3C per XML.</span><span class="sxs-lookup"><span data-stu-id="a6342-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>  
  
 <span data-ttu-id="a6342-109">Il valore predefinito di `xml:space` attributo è il valore letterale `"default"`.</span><span class="sxs-lookup"><span data-stu-id="a6342-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="a6342-110">Per il valore `"default"`, oppure se `xml:space` non è indicato, il comportamento di analisi di spazio vuoto significativo è la gestione predefinita, come definito nell'argomento [l'elaborazione in XAML gli spazi vuoti](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="a6342-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant white-space parsing is the default handling, as defined in the topic [White-space processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span></span>  
  
 <span data-ttu-id="a6342-111">Per mantenere gli spazi vuoti all'interno di contenuto dell'elemento oggetto, specificare `xml:space="preserve"` nell'elemento oggetto.</span><span class="sxs-lookup"><span data-stu-id="a6342-111">To preserve white space within object element content, specify `xml:space="preserve"` on that object element.</span></span>  
  
 <span data-ttu-id="a6342-112">Nella maggior parte dei interpretazioni, il `xml:space` gli effetti dell'attributo e il valore dell'attributo sono limitate a elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="a6342-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>  
  
 <span data-ttu-id="a6342-113">Per informazioni dettagliate di spazio di elaborazione in XAML, vedere [l'elaborazione in XAML gli spazi vuoti](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="a6342-113">For a complete discussion of white-space processing in XAML, see [White-space processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6342-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6342-114">See Also</span></span>  
 [<span data-ttu-id="a6342-115">L'elaborazione in XAML gli spazi vuoti</span><span class="sxs-lookup"><span data-stu-id="a6342-115">White-space processing in XAML</span></span>](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)  
 [<span data-ttu-id="a6342-116">Cenni preliminari su XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="a6342-116">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
