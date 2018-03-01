---
title: Le costanti devono essere di tipo intrinseco o enumerato, non di tipo classe, struttura, parametro di tipo o matrice
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 702472751810c2d2bd08ece944ef0ffafc2049b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a><span data-ttu-id="f24a6-102">Le costanti devono essere di tipo intrinseco o enumerato, non di tipo classe, struttura, parametro di tipo o matrice</span><span class="sxs-lookup"><span data-stu-id="f24a6-102">Constants must be of an intrinsic or enumerated type, not a class, structure, type parameter, or array type</span></span>
<span data-ttu-id="f24a6-103">Si è provato a dichiarare una costante come una classe, struttura o tipo di matrice o come un parametro di tipo definito da un tipo generico contenitore.</span><span class="sxs-lookup"><span data-stu-id="f24a6-103">You have attempted to declare a constant as a class, structure, or array type, or as a type parameter defined by a containing generic type.</span></span>  
  
 <span data-ttu-id="f24a6-104">Le costanti devono essere di tipo intrinseco (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, o `UShort`), o un `Enum` tipo basato su uno dei tipi integrali.</span><span class="sxs-lookup"><span data-stu-id="f24a6-104">Constants must be of an intrinsic type (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, or `UShort`), or an `Enum` type based on one of the integral types.</span></span>  
  
 <span data-ttu-id="f24a6-105">**ID errore:** BC30424</span><span class="sxs-lookup"><span data-stu-id="f24a6-105">**Error ID:** BC30424</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f24a6-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f24a6-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="f24a6-107">Dichiarare la costante come funzione intrinseca o `Enum` tipo.</span><span class="sxs-lookup"><span data-stu-id="f24a6-107">Declare the constant as an intrinsic or `Enum` type.</span></span>  
  
2.  <span data-ttu-id="f24a6-108">Una costante può anche essere un valore speciale, ad esempio `True`, `False`, o `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="f24a6-108">A constant can also be a special value such as `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="f24a6-109">Il compilatore considera questi valori predefiniti per essere di tipo intrinseco appropriato.</span><span class="sxs-lookup"><span data-stu-id="f24a6-109">The compiler considers these predefined values to be of the appropriate intrinsic type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f24a6-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f24a6-110">See Also</span></span>  
 [<span data-ttu-id="f24a6-111">Costanti ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="f24a6-111">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [<span data-ttu-id="f24a6-112">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="f24a6-112">Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="f24a6-113">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="f24a6-113">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)
