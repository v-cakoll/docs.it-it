---
title: L'inferenza di tipi nullable non è supportata in questo contesto
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 52e5391fbcf30a4dada4d64a0e810c900ea85806
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409387"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="007e8-102">L'inferenza di tipi nullable non è supportata in questo contesto</span><span class="sxs-lookup"><span data-stu-id="007e8-102">Nullable type inference is not supported in this context</span></span>
<span data-ttu-id="007e8-103">I tipi di valore e le strutture possono essere dichiarati nullable.</span><span class="sxs-lookup"><span data-stu-id="007e8-103">Value types and structures can be declared nullable.</span></span>  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 <span data-ttu-id="007e8-104">Tuttavia, non è possibile usare la dichiarazione nullable in combinazione con l'inferenza del tipo.</span><span class="sxs-lookup"><span data-stu-id="007e8-104">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="007e8-105">Nell'esempio seguente viene generato questo errore.</span><span class="sxs-lookup"><span data-stu-id="007e8-105">The following examples cause this error.</span></span>  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 <span data-ttu-id="007e8-106">**ID errore:** BC36629</span><span class="sxs-lookup"><span data-stu-id="007e8-106">**Error ID:** BC36629</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="007e8-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="007e8-107">To correct this error</span></span>  
  
- <span data-ttu-id="007e8-108">Usare una `As` clausola per dichiarare la variabile come tipo di valore Nullable.</span><span class="sxs-lookup"><span data-stu-id="007e8-108">Use an `As` clause to declare the variable as a nullable value type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="007e8-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="007e8-109">See also</span></span>

- [<span data-ttu-id="007e8-110">Tipi di valore Nullable</span><span class="sxs-lookup"><span data-stu-id="007e8-110">Nullable Value Types</span></span>](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="007e8-111">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="007e8-111">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
