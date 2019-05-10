---
title: Istruzione non valida all'interno di un'espressione lambda su più righe (metodo)
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: 9e6c8ddd7851aee6d9fa1928a6854f7337b867b0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64593218"
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a><span data-ttu-id="7d436-102">Istruzione non valida all'interno di un metodo/espressione lambda su più righe</span><span class="sxs-lookup"><span data-stu-id="7d436-102">Statement is not valid inside a method/multiline lambda</span></span>
<span data-ttu-id="7d436-103">L'istruzione non è valido all'interno di un `Sub`, `Function`, proprietà `Get`, o proprietà `Set` procedure.</span><span class="sxs-lookup"><span data-stu-id="7d436-103">The statement is not valid within a `Sub`, `Function`, property `Get`, or property `Set` procedure.</span></span> <span data-ttu-id="7d436-104">Alcune istruzioni possono essere inseriti a livello di classe o modulo.</span><span class="sxs-lookup"><span data-stu-id="7d436-104">Some statements can be placed at the module or class level.</span></span> <span data-ttu-id="7d436-105">Altri, ad esempio `Option Strict`, devono essere a livello di spazio dei nomi e precedere tutte le altre dichiarazioni.</span><span class="sxs-lookup"><span data-stu-id="7d436-105">Others, such as `Option Strict`, must be at namespace level and precede all other declarations.</span></span>  
  
 <span data-ttu-id="7d436-106">**ID errore:** BC30024</span><span class="sxs-lookup"><span data-stu-id="7d436-106">**Error ID:** BC30024</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7d436-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="7d436-107">To correct this error</span></span>  
  
- <span data-ttu-id="7d436-108">Rimuovere l'istruzione della procedura.</span><span class="sxs-lookup"><span data-stu-id="7d436-108">Remove the statement from the procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d436-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d436-109">See also</span></span>

- [<span data-ttu-id="7d436-110">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="7d436-110">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="7d436-111">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="7d436-111">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="7d436-112">Istruzione Get</span><span class="sxs-lookup"><span data-stu-id="7d436-112">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="7d436-113">Istruzione Set</span><span class="sxs-lookup"><span data-stu-id="7d436-113">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
