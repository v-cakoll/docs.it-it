---
title: Le costanti devono essere di tipo intrinseco o enumerato, non di tipo classe, struttura, parametro di tipo o matrice
ms.date: 07/20/2015
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
ms.openlocfilehash: 4d635d289ed99aed48c296c278bc546971af51da
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "42999201"
---
# <a name="constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a><span data-ttu-id="d56c8-102">Le costanti devono essere di tipo intrinseco o enumerato, non di tipo classe, struttura, parametro di tipo o matrice</span><span class="sxs-lookup"><span data-stu-id="d56c8-102">Constants must be of an intrinsic or enumerated type, not a class, structure, type parameter, or array type</span></span>
<span data-ttu-id="d56c8-103">Si è provato a dichiarare una costante come una classe, struttura o tipo di matrice o come un parametro di tipo definito da un tipo generico che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="d56c8-103">You have attempted to declare a constant as a class, structure, or array type, or as a type parameter defined by a containing generic type.</span></span>  
  
 <span data-ttu-id="d56c8-104">Le costanti devono essere di tipo intrinseco (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, o `UShort`), o un `Enum` tipo basato su uno dei tipi integrali.</span><span class="sxs-lookup"><span data-stu-id="d56c8-104">Constants must be of an intrinsic type (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, or `UShort`), or an `Enum` type based on one of the integral types.</span></span>  
  
 <span data-ttu-id="d56c8-105">**ID errore:** BC30424</span><span class="sxs-lookup"><span data-stu-id="d56c8-105">**Error ID:** BC30424</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d56c8-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="d56c8-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="d56c8-107">Dichiarare la costante come funzione intrinseca o `Enum` tipo.</span><span class="sxs-lookup"><span data-stu-id="d56c8-107">Declare the constant as an intrinsic or `Enum` type.</span></span>  
  
2.  <span data-ttu-id="d56c8-108">Una costante può anche essere, ad esempio un valore speciale `True`, `False`, o `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="d56c8-108">A constant can also be a special value such as `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="d56c8-109">Il compilatore considera i valori predefiniti di tipo intrinseco appropriato.</span><span class="sxs-lookup"><span data-stu-id="d56c8-109">The compiler considers these predefined values to be of the appropriate intrinsic type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d56c8-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d56c8-110">See Also</span></span>  
 [<span data-ttu-id="d56c8-111">Costanti ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="d56c8-111">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [<span data-ttu-id="d56c8-112">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="d56c8-112">Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="d56c8-113">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="d56c8-113">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
