---
title: Impossibile convertire il valore di tipo 'type1' in 'type2'
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: f19f157bd4c76f481aa3232bc33c2a0c6ac21367
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400279"
---
# <a name="value-of-type-type1-cannot-be-converted-to-type2"></a><span data-ttu-id="d4937-102">Impossibile convertire il valore di tipo 'type1' in 'type2'</span><span class="sxs-lookup"><span data-stu-id="d4937-102">Value of type 'type1' cannot be converted to 'type2'</span></span>
<span data-ttu-id="d4937-103">Non è possibile convertire il valore di tipo ' tipo1' in ' tipo2'.</span><span class="sxs-lookup"><span data-stu-id="d4937-103">Value of type 'type1' cannot be converted to 'type2'.</span></span> <span data-ttu-id="d4937-104">È possibile usare la proprietà' value ' per ottenere il valore stringa del primo elemento di ' \<parentElement> '.</span><span class="sxs-lookup"><span data-stu-id="d4937-104">You can use the 'Value' property to get the string value of the first element of '\<parentElement>'.</span></span>  
  
 <span data-ttu-id="d4937-105">Si è provato a eseguire implicitamente il cast di un valore letterale XML a un tipo specifico.</span><span class="sxs-lookup"><span data-stu-id="d4937-105">An attempt has been made to implicitly cast an XML literal to a specific type.</span></span> <span data-ttu-id="d4937-106">Non è possibile eseguire implicitamente il cast del valore letterale XML al tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="d4937-106">The XML literal cannot be implicitly cast to the specified type.</span></span>  
  
 <span data-ttu-id="d4937-107">**ID errore:** BC31194</span><span class="sxs-lookup"><span data-stu-id="d4937-107">**Error ID:** BC31194</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d4937-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="d4937-108">To correct this error</span></span>  
  
- <span data-ttu-id="d4937-109">Usare la proprietà `Value` del valore letterale XML per fare riferimento al relativo valore come `String`.</span><span class="sxs-lookup"><span data-stu-id="d4937-109">Use the `Value` property of the XML literal to reference its value as a `String`.</span></span> <span data-ttu-id="d4937-110">Usare la funzione `CType` , un'altra funzione di conversione del tipo oppure la classe <xref:System.Convert> per eseguire il cast del valore come tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="d4937-110">Use the `CType` function, another type conversion function, or the <xref:System.Convert> class to cast the value as the specified type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4937-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4937-111">See also</span></span>

- <xref:System.Convert>
- [<span data-ttu-id="d4937-112">CString</span><span class="sxs-lookup"><span data-stu-id="d4937-112">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="d4937-113">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="d4937-113">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="d4937-114">XML</span><span class="sxs-lookup"><span data-stu-id="d4937-114">XML</span></span>](../../programming-guide/language-features/xml/index.md)
