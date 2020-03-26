---
title: L'inferenza di tipi nullable non è supportata in questo contesto
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 42bde0b1843e52bbc16118bb056ade791591904e
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249500"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="f0297-102">L'inferenza di tipi nullable non è supportata in questo contesto</span><span class="sxs-lookup"><span data-stu-id="f0297-102">Nullable type inference is not supported in this context</span></span>
<span data-ttu-id="f0297-103">I tipi di valore e le strutture possono essere dichiarati nullable.</span><span class="sxs-lookup"><span data-stu-id="f0297-103">Value types and structures can be declared nullable.</span></span>  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 <span data-ttu-id="f0297-104">Tuttavia, non è possibile utilizzare la dichiarazione nullable in combinazione con l'inferenza del tipo.</span><span class="sxs-lookup"><span data-stu-id="f0297-104">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="f0297-105">Gli esempi seguenti causano questo errore.</span><span class="sxs-lookup"><span data-stu-id="f0297-105">The following examples cause this error.</span></span>  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 <span data-ttu-id="f0297-106">**ID errore:** BC36629 (informazioni in inglese)</span><span class="sxs-lookup"><span data-stu-id="f0297-106">**Error ID:** BC36629</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f0297-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f0297-107">To correct this error</span></span>  
  
- <span data-ttu-id="f0297-108">Utilizzare `As` una clausola per dichiarare la variabile come tipo di valore nullable.</span><span class="sxs-lookup"><span data-stu-id="f0297-108">Use an `As` clause to declare the variable as a nullable value type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0297-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0297-109">See also</span></span>

- [<span data-ttu-id="f0297-110">Tipi di valore nullableNullable Value Types</span><span class="sxs-lookup"><span data-stu-id="f0297-110">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="f0297-111">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="f0297-111">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
