---
title: L'inferenza di tipi nullable non è supportata in questo contesto
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 7dffc5233656257cd892f573a2f8b9f91d781c21
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611891"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="fdf70-102">L'inferenza di tipi nullable non è supportata in questo contesto</span><span class="sxs-lookup"><span data-stu-id="fdf70-102">Nullable type inference is not supported in this context</span></span>
<span data-ttu-id="fdf70-103">Strutture e tipi di valore possono essere dichiarate nullable.</span><span class="sxs-lookup"><span data-stu-id="fdf70-103">Value types and structures can be declared nullable.</span></span>  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 <span data-ttu-id="fdf70-104">Tuttavia, è possibile usare la dichiarazione che ammette valori null in combinazione con l'inferenza del tipo.</span><span class="sxs-lookup"><span data-stu-id="fdf70-104">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="fdf70-105">Gli esempi seguenti causano questo errore.</span><span class="sxs-lookup"><span data-stu-id="fdf70-105">The following examples cause this error.</span></span>  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 <span data-ttu-id="fdf70-106">**ID errore:** BC36629</span><span class="sxs-lookup"><span data-stu-id="fdf70-106">**Error ID:** BC36629</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fdf70-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="fdf70-107">To correct this error</span></span>  
  
-   <span data-ttu-id="fdf70-108">Usare un `As` clausola per dichiarare la variabile come nullable.</span><span class="sxs-lookup"><span data-stu-id="fdf70-108">Use an `As` clause to declare the variable as nullable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdf70-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fdf70-109">See also</span></span>
- [<span data-ttu-id="fdf70-110">Tipi di valori nullable</span><span class="sxs-lookup"><span data-stu-id="fdf70-110">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="fdf70-111">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="fdf70-111">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
