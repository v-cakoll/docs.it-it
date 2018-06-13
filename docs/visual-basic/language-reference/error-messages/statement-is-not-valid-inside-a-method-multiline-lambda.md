---
title: Istruzione non è valida all'interno di un'espressione lambda su più righe di metodo
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: cef5beea16c8589a884b7d3533e0543454783999
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33598855"
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a><span data-ttu-id="351bf-102">Istruzione non valida all'interno di un metodo/espressione lambda su più righe</span><span class="sxs-lookup"><span data-stu-id="351bf-102">Statement is not valid inside a method/multiline lambda</span></span>
<span data-ttu-id="351bf-103">L'istruzione non è valido all'interno di un `Sub`, `Function`, proprietà `Get`, o proprietà `Set` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="351bf-103">The statement is not valid within a `Sub`, `Function`, property `Get`, or property `Set` procedure.</span></span> <span data-ttu-id="351bf-104">Alcune istruzioni possono essere inseriti a livello di modulo o classe.</span><span class="sxs-lookup"><span data-stu-id="351bf-104">Some statements can be placed at the module or class level.</span></span> <span data-ttu-id="351bf-105">Altri, ad esempio `Option Strict`, è necessario essere a livello di spazio dei nomi e precedere tutte le altre dichiarazioni.</span><span class="sxs-lookup"><span data-stu-id="351bf-105">Others, such as `Option Strict`, must be at namespace level and precede all other declarations.</span></span>  
  
 <span data-ttu-id="351bf-106">**ID errore:** BC30024</span><span class="sxs-lookup"><span data-stu-id="351bf-106">**Error ID:** BC30024</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="351bf-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="351bf-107">To correct this error</span></span>  
  
-   <span data-ttu-id="351bf-108">Rimuovere l'istruzione dalla routine.</span><span class="sxs-lookup"><span data-stu-id="351bf-108">Remove the statement from the procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="351bf-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="351bf-109">See Also</span></span>  
 [<span data-ttu-id="351bf-110">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="351bf-110">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="351bf-111">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="351bf-111">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="351bf-112">Istruzione Get</span><span class="sxs-lookup"><span data-stu-id="351bf-112">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)  
 [<span data-ttu-id="351bf-113">Istruzione Set</span><span class="sxs-lookup"><span data-stu-id="351bf-113">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
