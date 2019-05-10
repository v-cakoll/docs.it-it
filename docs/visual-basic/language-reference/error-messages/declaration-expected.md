---
title: Prevista dichiarazione
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: e6f8bf2b4ce9789a1715971b8262bdd162ba8035
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64619537"
---
# <a name="declaration-expected"></a><span data-ttu-id="4ec2b-102">Prevista dichiarazione</span><span class="sxs-lookup"><span data-stu-id="4ec2b-102">Declaration expected</span></span>
<span data-ttu-id="4ec2b-103">Un'istruzione non dichiarativa, ad esempio un'assegnazione o un'istruzione di ciclo, si verifica all'esterno di qualsiasi routine.</span><span class="sxs-lookup"><span data-stu-id="4ec2b-103">A nondeclarative statement, such as an assignment or loop statement, occurs outside any procedure.</span></span> <span data-ttu-id="4ec2b-104">Solo le dichiarazioni sono consentite alle routine esterne.</span><span class="sxs-lookup"><span data-stu-id="4ec2b-104">Only declarations are allowed outside procedures.</span></span>  
  
 <span data-ttu-id="4ec2b-105">In alternativa, un elemento di programmazione è dichiarato senza una parola chiave di dichiarazione, ad esempio `Dim` o `Const`.</span><span class="sxs-lookup"><span data-stu-id="4ec2b-105">Alternatively, a programming element is declared without a declaration keyword such as `Dim` or `Const`.</span></span>  
  
 <span data-ttu-id="4ec2b-106">**ID errore:** BC30188</span><span class="sxs-lookup"><span data-stu-id="4ec2b-106">**Error ID:** BC30188</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4ec2b-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="4ec2b-107">To correct this error</span></span>  
  
- <span data-ttu-id="4ec2b-108">Spostare l'istruzione non dichiarativa per il corpo di una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="4ec2b-108">Move the nondeclarative statement to the body of a procedure.</span></span>  
  
- <span data-ttu-id="4ec2b-109">Iniziare la dichiarazione con una parola chiave di dichiarazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="4ec2b-109">Begin the declaration with an appropriate declaration keyword.</span></span>  
  
- <span data-ttu-id="4ec2b-110">Assicurarsi che una parola chiave di dichiarazione non è errata.</span><span class="sxs-lookup"><span data-stu-id="4ec2b-110">Ensure that a declaration keyword is not misspelled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ec2b-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ec2b-111">See also</span></span>

- [<span data-ttu-id="4ec2b-112">Routine</span><span class="sxs-lookup"><span data-stu-id="4ec2b-112">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="4ec2b-113">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="4ec2b-113">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
