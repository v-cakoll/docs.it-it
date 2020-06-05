---
title: Riferimenti a entità XML non supportati
ms.date: 07/20/2015
f1_keywords:
- vbc31180
- bc31180
helpviewer_keywords:
- BC31180
ms.assetid: 2a393327-d8e2-4187-85b1-642b4f53b4ae
ms.openlocfilehash: ae997d853a93999a3b29215ea1257da7a1d48c84
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406456"
---
# <a name="xml-entity-references-are-not-supported"></a><span data-ttu-id="b328c-102">Riferimenti a entità XML non supportati</span><span class="sxs-lookup"><span data-stu-id="b328c-102">XML entity references are not supported</span></span>
<span data-ttu-id="b328c-103">Un riferimento all'entità, ad esempio, `©` che non è definito nella specifica xml 1,0 è incluso come valore per un valore letterale XML.</span><span class="sxs-lookup"><span data-stu-id="b328c-103">An entity reference (for example, `©`) that is not defined in the XML 1.0 specification is included as a value for an XML literal.</span></span> <span data-ttu-id="b328c-104">`&` `"` `<` `>` `'` Nei valori letterali XML sono supportati solo i riferimenti a entità,,, e XML.</span><span class="sxs-lookup"><span data-stu-id="b328c-104">Only `&`, `"`, `<`, `>`, and `'` XML entity references are supported in XML literals.</span></span>  
  
 <span data-ttu-id="b328c-105">**ID errore:** BC31180</span><span class="sxs-lookup"><span data-stu-id="b328c-105">**Error ID:** BC31180</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b328c-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="b328c-106">To correct this error</span></span>  
  
- <span data-ttu-id="b328c-107">Rimuovere il riferimento all'entità non supportato.</span><span class="sxs-lookup"><span data-stu-id="b328c-107">Remove the unsupported entity reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b328c-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b328c-108">See also</span></span>

- [<span data-ttu-id="b328c-109">Valori letterali XML e specifica XML 1.0</span><span class="sxs-lookup"><span data-stu-id="b328c-109">XML Literals and the XML 1.0 Specification</span></span>](../../programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)
- [<span data-ttu-id="b328c-110">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="b328c-110">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="b328c-111">XML</span><span class="sxs-lookup"><span data-stu-id="b328c-111">XML</span></span>](../../programming-guide/language-features/xml/index.md)
