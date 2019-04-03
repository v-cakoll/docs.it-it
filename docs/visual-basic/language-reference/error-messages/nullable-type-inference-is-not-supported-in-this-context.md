---
title: L'inferenza di tipi nullable non è supportata in questo contesto
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 9f7f878649d8b96f050b56d5b878eb3d67e027ff
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819242"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="b8a76-102">L'inferenza di tipi nullable non è supportata in questo contesto</span><span class="sxs-lookup"><span data-stu-id="b8a76-102">Nullable type inference is not supported in this context</span></span>
<span data-ttu-id="b8a76-103">Strutture e tipi di valore possono essere dichiarate nullable.</span><span class="sxs-lookup"><span data-stu-id="b8a76-103">Value types and structures can be declared nullable.</span></span>  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 <span data-ttu-id="b8a76-104">Tuttavia, è possibile usare la dichiarazione che ammette valori null in combinazione con l'inferenza del tipo.</span><span class="sxs-lookup"><span data-stu-id="b8a76-104">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="b8a76-105">Gli esempi seguenti causano questo errore.</span><span class="sxs-lookup"><span data-stu-id="b8a76-105">The following examples cause this error.</span></span>  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 <span data-ttu-id="b8a76-106">**ID errore:** BC36629</span><span class="sxs-lookup"><span data-stu-id="b8a76-106">**Error ID:** BC36629</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b8a76-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="b8a76-107">To correct this error</span></span>  
  
-   <span data-ttu-id="b8a76-108">Usare un `As` clausola per dichiarare la variabile come nullable.</span><span class="sxs-lookup"><span data-stu-id="b8a76-108">Use an `As` clause to declare the variable as nullable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8a76-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8a76-109">See also</span></span>

- [<span data-ttu-id="b8a76-110">Tipi di valori nullable</span><span class="sxs-lookup"><span data-stu-id="b8a76-110">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="b8a76-111">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="b8a76-111">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
