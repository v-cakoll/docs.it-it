---
title: Istruzione non valida all'interno di un'espressione lambda su più righe (metodo)
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: 994cafc44a37d16d0f70caec560f530c6a836ec0
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841563"
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a><span data-ttu-id="f7665-102">Istruzione non valida all'interno di un metodo/espressione lambda su più righe</span><span class="sxs-lookup"><span data-stu-id="f7665-102">Statement is not valid inside a method/multiline lambda</span></span>
<span data-ttu-id="f7665-103">L'istruzione non è valido all'interno di un `Sub`, `Function`, proprietà `Get`, o proprietà `Set` procedure.</span><span class="sxs-lookup"><span data-stu-id="f7665-103">The statement is not valid within a `Sub`, `Function`, property `Get`, or property `Set` procedure.</span></span> <span data-ttu-id="f7665-104">Alcune istruzioni possono essere inseriti a livello di classe o modulo.</span><span class="sxs-lookup"><span data-stu-id="f7665-104">Some statements can be placed at the module or class level.</span></span> <span data-ttu-id="f7665-105">Altri, ad esempio `Option Strict`, devono essere a livello di spazio dei nomi e precedere tutte le altre dichiarazioni.</span><span class="sxs-lookup"><span data-stu-id="f7665-105">Others, such as `Option Strict`, must be at namespace level and precede all other declarations.</span></span>  
  
 <span data-ttu-id="f7665-106">**ID errore:** BC30024</span><span class="sxs-lookup"><span data-stu-id="f7665-106">**Error ID:** BC30024</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f7665-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f7665-107">To correct this error</span></span>  
  
-   <span data-ttu-id="f7665-108">Rimuovere l'istruzione della procedura.</span><span class="sxs-lookup"><span data-stu-id="f7665-108">Remove the statement from the procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7665-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7665-109">See also</span></span>

- [<span data-ttu-id="f7665-110">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="f7665-110">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="f7665-111">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="f7665-111">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="f7665-112">Istruzione Get</span><span class="sxs-lookup"><span data-stu-id="f7665-112">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="f7665-113">Istruzione Set</span><span class="sxs-lookup"><span data-stu-id="f7665-113">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
