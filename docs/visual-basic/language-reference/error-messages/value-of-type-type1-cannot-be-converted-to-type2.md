---
title: Valore di tipo &#39;type1&#39; non può essere convertito in &#39;type2&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: 657e0feb675e15b9ece00d40c3d1ebe932a29099
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568288"
---
# <a name="value-of-type-39type139-cannot-be-converted-to-39type239"></a><span data-ttu-id="e4688-102">Valore di tipo &#39;type1&#39; non può essere convertito in &#39;type2&#39;</span><span class="sxs-lookup"><span data-stu-id="e4688-102">Value of type &#39;type1&#39; cannot be converted to &#39;type2&#39;</span></span>
<span data-ttu-id="e4688-103">Valore di tipo 'type1' non può essere convertito in 'type2'.</span><span class="sxs-lookup"><span data-stu-id="e4688-103">Value of type 'type1' cannot be converted to 'type2'.</span></span> <span data-ttu-id="e4688-104">È possibile usare la proprietà 'Value' per ottenere il valore di stringa del primo elemento di '\<ElementoPadre >'.</span><span class="sxs-lookup"><span data-stu-id="e4688-104">You can use the 'Value' property to get the string value of the first element of '\<parentElement>'.</span></span>  
  
 <span data-ttu-id="e4688-105">Si è provato a eseguire implicitamente il cast di un valore letterale XML a un tipo specifico.</span><span class="sxs-lookup"><span data-stu-id="e4688-105">An attempt has been made to implicitly cast an XML literal to a specific type.</span></span> <span data-ttu-id="e4688-106">Non è possibile eseguire implicitamente il cast del valore letterale XML al tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="e4688-106">The XML literal cannot be implicitly cast to the specified type.</span></span>  
  
 <span data-ttu-id="e4688-107">**ID errore:** BC31194</span><span class="sxs-lookup"><span data-stu-id="e4688-107">**Error ID:** BC31194</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e4688-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="e4688-108">To correct this error</span></span>  
  
-   <span data-ttu-id="e4688-109">Usare la proprietà `Value` del valore letterale XML per fare riferimento al relativo valore come `String`.</span><span class="sxs-lookup"><span data-stu-id="e4688-109">Use the `Value` property of the XML literal to reference its value as a `String`.</span></span> <span data-ttu-id="e4688-110">Usare la funzione `CType` , un'altra funzione di conversione del tipo oppure la classe <xref:System.Convert> per eseguire il cast del valore come tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="e4688-110">Use the `CType` function, another type conversion function, or the <xref:System.Convert> class to cast the value as the specified type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4688-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4688-111">See also</span></span>
- <xref:System.Convert>
- [<span data-ttu-id="e4688-112">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="e4688-112">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="e4688-113">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="e4688-113">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="e4688-114">XML</span><span class="sxs-lookup"><span data-stu-id="e4688-114">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
