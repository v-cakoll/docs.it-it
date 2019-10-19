---
title: Istruzione Erase (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 7dec2a859f664ee8dcbb305082ec33aeacbaccb4
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583393"
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="35b0d-102">Istruzione Erase (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="35b0d-102">Erase Statement (Visual Basic)</span></span>
<span data-ttu-id="35b0d-103">Usato per rilasciare le variabili di matrice e deallocare la memoria usata per i relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="35b0d-103">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35b0d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="35b0d-104">Syntax</span></span>  
  
```vb  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="35b0d-105">Parti</span><span class="sxs-lookup"><span data-stu-id="35b0d-105">Parts</span></span>  
 `arraylist`  
 <span data-ttu-id="35b0d-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="35b0d-106">Required.</span></span> <span data-ttu-id="35b0d-107">Elenco di variabili di matrice da cancellare.</span><span class="sxs-lookup"><span data-stu-id="35b0d-107">List of array variables to be erased.</span></span> <span data-ttu-id="35b0d-108">Nel caso di più variabili, è possibile separarle mediante virgole.</span><span class="sxs-lookup"><span data-stu-id="35b0d-108">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35b0d-109">Note</span><span class="sxs-lookup"><span data-stu-id="35b0d-109">Remarks</span></span>  
 <span data-ttu-id="35b0d-110">L'istruzione `Erase` può essere visualizzata solo a livello di routine.</span><span class="sxs-lookup"><span data-stu-id="35b0d-110">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="35b0d-111">Ciò significa che è possibile rilasciare matrici all'interno di una routine ma non a livello di classe o di modulo.</span><span class="sxs-lookup"><span data-stu-id="35b0d-111">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="35b0d-112">L'istruzione `Erase` equivale a assegnare `Nothing` a ogni variabile di matrice.</span><span class="sxs-lookup"><span data-stu-id="35b0d-112">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35b0d-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="35b0d-113">Example</span></span>  
 <span data-ttu-id="35b0d-114">Nell'esempio seguente viene utilizzata l'istruzione `Erase` per cancellare due matrici e liberare la relativa memoria (rispettivamente gli elementi di archiviazione 1000 e 100).</span><span class="sxs-lookup"><span data-stu-id="35b0d-114">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="35b0d-115">L'istruzione `ReDim` assegna quindi una nuova istanza di matrice alla matrice tridimensionale.</span><span class="sxs-lookup"><span data-stu-id="35b0d-115">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="35b0d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35b0d-116">See also</span></span>

- [<span data-ttu-id="35b0d-117">Nothing</span><span class="sxs-lookup"><span data-stu-id="35b0d-117">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="35b0d-118">Istruzione ReDim</span><span class="sxs-lookup"><span data-stu-id="35b0d-118">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
