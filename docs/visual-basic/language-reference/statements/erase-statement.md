---
title: Istruzione Erase (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: cab3da4465b4671d203036c2d9bcd40662dc234a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54522440"
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="53d32-102">Istruzione Erase (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53d32-102">Erase Statement (Visual Basic)</span></span>
<span data-ttu-id="53d32-103">Utilizzato per rilasciare le variabili di matrice e deallocare la memoria usata per i relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="53d32-103">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53d32-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="53d32-104">Syntax</span></span>  
  
```  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="53d32-105">Parti</span><span class="sxs-lookup"><span data-stu-id="53d32-105">Parts</span></span>  
 `arraylist`  
 <span data-ttu-id="53d32-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="53d32-106">Required.</span></span> <span data-ttu-id="53d32-107">Elenco di variabili di matrice da cancellare.</span><span class="sxs-lookup"><span data-stu-id="53d32-107">List of array variables to be erased.</span></span> <span data-ttu-id="53d32-108">Nel caso di più variabili, è possibile separarle mediante virgole.</span><span class="sxs-lookup"><span data-stu-id="53d32-108">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53d32-109">Note</span><span class="sxs-lookup"><span data-stu-id="53d32-109">Remarks</span></span>  
 <span data-ttu-id="53d32-110">Il `Erase` istruzione può essere specificata solo a livello di routine.</span><span class="sxs-lookup"><span data-stu-id="53d32-110">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="53d32-111">Ciò significa che è possibile rilasciare le matrici all'interno di una routine, ma non a livello di classe o modulo.</span><span class="sxs-lookup"><span data-stu-id="53d32-111">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="53d32-112">Il `Erase` istruzione equivale all'assegnazione `Nothing` a ogni variabile di matrice.</span><span class="sxs-lookup"><span data-stu-id="53d32-112">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53d32-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="53d32-113">Example</span></span>  
 <span data-ttu-id="53d32-114">L'esempio seguente usa il `Erase` istruzione per due matrici di cancellare e liberare la memoria (1000 e 100 elementi, rispettivamente).</span><span class="sxs-lookup"><span data-stu-id="53d32-114">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="53d32-115">Il `ReDim` istruzione quindi assegna una nuova istanza della matrice nella matrice tridimensionale.</span><span class="sxs-lookup"><span data-stu-id="53d32-115">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/erase-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="53d32-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53d32-116">See also</span></span>
- [<span data-ttu-id="53d32-117">Nothing</span><span class="sxs-lookup"><span data-stu-id="53d32-117">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="53d32-118">Istruzione ReDim</span><span class="sxs-lookup"><span data-stu-id="53d32-118">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
