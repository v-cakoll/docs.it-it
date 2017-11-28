---
title: "L'inferenza di tipi nullable non è supportata in questo contesto"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords: BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e7a5450d812260d3916296dff56abee27b3d586c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="8dd6d-102">L'inferenza di tipi nullable non è supportata in questo contesto</span><span class="sxs-lookup"><span data-stu-id="8dd6d-102">Nullable type inference is not supported in this context</span></span>
<span data-ttu-id="8dd6d-103">Tipi di valore e le strutture possono essere dichiarate nullable.</span><span class="sxs-lookup"><span data-stu-id="8dd6d-103">Value types and structures can be declared nullable.</span></span>  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 <span data-ttu-id="8dd6d-104">Tuttavia, è possibile usare la dichiarazione che ammette valori null in combinazione con l'inferenza del tipo.</span><span class="sxs-lookup"><span data-stu-id="8dd6d-104">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="8dd6d-105">Negli esempi seguenti generano questo errore.</span><span class="sxs-lookup"><span data-stu-id="8dd6d-105">The following examples cause this error.</span></span>  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 <span data-ttu-id="8dd6d-106">**ID errore:** BC36629</span><span class="sxs-lookup"><span data-stu-id="8dd6d-106">**Error ID:** BC36629</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8dd6d-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="8dd6d-107">To correct this error</span></span>  
  
-   <span data-ttu-id="8dd6d-108">Utilizzare un `As` clausola per dichiarare la variabile come nullable.</span><span class="sxs-lookup"><span data-stu-id="8dd6d-108">Use an `As` clause to declare the variable as nullable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dd6d-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8dd6d-109">See Also</span></span>  
 [<span data-ttu-id="8dd6d-110">Tipi di valori nullable</span><span class="sxs-lookup"><span data-stu-id="8dd6d-110">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [<span data-ttu-id="8dd6d-111">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="8dd6d-111">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
