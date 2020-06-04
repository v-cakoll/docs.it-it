---
title: Istruzione non valida all'interno di un metodo/espressione lambda su più righe
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: f3c43d640259d5e1af545e2610088aab5d70453d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396246"
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a><span data-ttu-id="4eda7-102">Istruzione non valida all'interno di un metodo/espressione lambda su più righe</span><span class="sxs-lookup"><span data-stu-id="4eda7-102">Statement is not valid inside a method/multiline lambda</span></span>
<span data-ttu-id="4eda7-103">L'istruzione non è valida all'interno di una `Sub` `Function` `Get` routine Property,, o `Set` .</span><span class="sxs-lookup"><span data-stu-id="4eda7-103">The statement is not valid within a `Sub`, `Function`, property `Get`, or property `Set` procedure.</span></span> <span data-ttu-id="4eda7-104">È possibile inserire alcune istruzioni a livello di modulo o di classe.</span><span class="sxs-lookup"><span data-stu-id="4eda7-104">Some statements can be placed at the module or class level.</span></span> <span data-ttu-id="4eda7-105">Altri, ad esempio `Option Strict` , devono essere a livello di spazio dei nomi e precedere tutte le altre dichiarazioni.</span><span class="sxs-lookup"><span data-stu-id="4eda7-105">Others, such as `Option Strict`, must be at namespace level and precede all other declarations.</span></span>  
  
 <span data-ttu-id="4eda7-106">**ID errore:** BC30024</span><span class="sxs-lookup"><span data-stu-id="4eda7-106">**Error ID:** BC30024</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4eda7-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="4eda7-107">To correct this error</span></span>  
  
- <span data-ttu-id="4eda7-108">Rimuovere l'istruzione dalla procedura.</span><span class="sxs-lookup"><span data-stu-id="4eda7-108">Remove the statement from the procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eda7-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4eda7-109">See also</span></span>

- [<span data-ttu-id="4eda7-110">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="4eda7-110">Sub Statement</span></span>](../statements/sub-statement.md)
- [<span data-ttu-id="4eda7-111">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="4eda7-111">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="4eda7-112">Istruzione Get</span><span class="sxs-lookup"><span data-stu-id="4eda7-112">Get Statement</span></span>](../statements/get-statement.md)
- [<span data-ttu-id="4eda7-113">Istruzione set</span><span class="sxs-lookup"><span data-stu-id="4eda7-113">Set Statement</span></span>](../statements/set-statement.md)
