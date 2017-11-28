---
title: '&#39; AddressOf &#39; operando deve essere il nome di un metodo (senza parentesi)'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords: BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 02c996f1c94250526982e35395288b07db619db7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="39addressof39-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="57d9c-102">&#39; AddressOf &#39; operando deve essere il nome di un metodo (senza parentesi)</span><span class="sxs-lookup"><span data-stu-id="57d9c-102">&#39;AddressOf&#39; operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="57d9c-103">L'operatore `AddressOf` crea un'istanza di delegato di routine che fa riferimento a una routine specifica.</span><span class="sxs-lookup"><span data-stu-id="57d9c-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="57d9c-104">La sintassi è come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="57d9c-104">The syntax is as follows.</span></span>  
  
 <span data-ttu-id="57d9c-105">`AddressOf` `procedurename`</span><span class="sxs-lookup"><span data-stu-id="57d9c-105">`AddressOf` `procedurename`</span></span>  
  
 <span data-ttu-id="57d9c-106">È stato inserito parentesi per racchiudere l'argomento che segue `AddressOf`, che tuttavia non sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="57d9c-106">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="57d9c-107">**ID errore:** BC30577</span><span class="sxs-lookup"><span data-stu-id="57d9c-107">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="57d9c-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="57d9c-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="57d9c-109">Rimuovere le parentesi che racchiudono il seguente argomento `AddressOf`.</span><span class="sxs-lookup"><span data-stu-id="57d9c-109">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2.  <span data-ttu-id="57d9c-110">Verificare che l'argomento è un nome di metodo.</span><span class="sxs-lookup"><span data-stu-id="57d9c-110">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57d9c-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57d9c-111">See Also</span></span>  
 [<span data-ttu-id="57d9c-112">Operatore AddressOf</span><span class="sxs-lookup"><span data-stu-id="57d9c-112">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="57d9c-113">Delegati</span><span class="sxs-lookup"><span data-stu-id="57d9c-113">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
