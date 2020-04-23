---
title: Gestione di xml:space in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 886f906b6d1e3a10920dbf52e36bf76324c5a9f2
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071437"
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="c4b43-102">Gestione di xml:space in XAML</span><span class="sxs-lookup"><span data-stu-id="c4b43-102">xml:space Handling in XAML</span></span>

<span data-ttu-id="c4b43-103">L'attributo `xml:space` è un attributo definito in XML che dichiara il comportamento significativo di elaborazione degli spazi vuoti all'interno di un elemento oggetto.</span><span class="sxs-lookup"><span data-stu-id="c4b43-103">The `xml:space` attribute is an XML-defined attribute that declares the significant white-space processing behavior within an object element.</span></span> <span data-ttu-id="c4b43-104">Questo comportamento è rilevante per tutto il contenuto `xml:space` (testo interno) contenuto all'interno dell'elemento in cui viene dichiarato e anche gli ambiti per gli elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="c4b43-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="c4b43-105">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="c4b43-105">XAML Attribute Usage</span></span>

```xaml
<object xml:space="preserve" />
```

 <span data-ttu-id="c4b43-106">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="c4b43-106">\- or -</span></span>

```xaml
<object xml:space="default" />
```

## <a name="remarks"></a><span data-ttu-id="c4b43-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c4b43-107">Remarks</span></span>

<span data-ttu-id="c4b43-108">La definizione `xml:space` per l'attributo in XAML, inclusi i due valori possibili, è derivata da `xml:space` come definito come "attributo speciale" dalle specifiche W3C per XML.</span><span class="sxs-lookup"><span data-stu-id="c4b43-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>

<span data-ttu-id="c4b43-109">Il valore predefinito `xml:space` dell'attributo `"default"`è il valore letterale .</span><span class="sxs-lookup"><span data-stu-id="c4b43-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="c4b43-110">Per il `"default"`valore `xml:space` o se non viene indicato affatto, il comportamento dell'analisi degli spazi vuoti significativi è la gestione predefinita, come definito nell'argomento Elaborazione degli spazi vuoti [in XAML.](white-space-processing.md)</span><span class="sxs-lookup"><span data-stu-id="c4b43-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant white-space parsing is the default handling, as defined in the topic [White-space processing in XAML](white-space-processing.md).</span></span>

<span data-ttu-id="c4b43-111">Per mantenere gli spazi vuoti `xml:space="preserve"` all'interno del contenuto dell'elemento oggetto, specificare su tale elemento oggetto.</span><span class="sxs-lookup"><span data-stu-id="c4b43-111">To preserve white space within object element content, specify `xml:space="preserve"` on that object element.</span></span>

<span data-ttu-id="c4b43-112">Nella maggior parte `xml:space` delle interpretazioni, gli effetti dell'attributo e il valore dell'attributo hanno come ambito gli elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="c4b43-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>

<span data-ttu-id="c4b43-113">Per una descrizione completa dell'elaborazione degli spazi vuoti in XAML, vedere [Elaborazione degli spazi vuoti in XAML.](white-space-processing.md)</span><span class="sxs-lookup"><span data-stu-id="c4b43-113">For a complete discussion of white-space processing in XAML, see [White-space processing in XAML](white-space-processing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c4b43-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4b43-114">See also</span></span>

- [<span data-ttu-id="c4b43-115">Elaborazione degli spazi vuoti in XAML</span><span class="sxs-lookup"><span data-stu-id="c4b43-115">White-space processing in XAML</span></span>](white-space-processing.md)
- [<span data-ttu-id="c4b43-116">Panoramica di XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="c4b43-116">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
