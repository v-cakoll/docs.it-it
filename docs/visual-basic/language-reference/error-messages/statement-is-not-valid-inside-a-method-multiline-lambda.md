---
title: "Istruzione non è valida all'interno di un'espressione lambda su più righe di metodo"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 80673fc7a1497b4148a6505d29581c6403115558
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a><span data-ttu-id="02932-102">Istruzione non valida all'interno di un metodo/espressione lambda su più righe</span><span class="sxs-lookup"><span data-stu-id="02932-102">Statement is not valid inside a method/multiline lambda</span></span>
<span data-ttu-id="02932-103">L'istruzione non è valido all'interno di un `Sub`, `Function`, proprietà `Get`, o proprietà `Set` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="02932-103">The statement is not valid within a `Sub`, `Function`, property `Get`, or property `Set` procedure.</span></span> <span data-ttu-id="02932-104">Alcune istruzioni possono essere inseriti a livello di modulo o classe.</span><span class="sxs-lookup"><span data-stu-id="02932-104">Some statements can be placed at the module or class level.</span></span> <span data-ttu-id="02932-105">Altri, ad esempio `Option Strict`, è necessario essere a livello di spazio dei nomi e precedere tutte le altre dichiarazioni.</span><span class="sxs-lookup"><span data-stu-id="02932-105">Others, such as `Option Strict`, must be at namespace level and precede all other declarations.</span></span>  
  
 <span data-ttu-id="02932-106">**ID errore:** BC30024</span><span class="sxs-lookup"><span data-stu-id="02932-106">**Error ID:** BC30024</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="02932-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="02932-107">To correct this error</span></span>  
  
-   <span data-ttu-id="02932-108">Rimuovere l'istruzione dalla routine.</span><span class="sxs-lookup"><span data-stu-id="02932-108">Remove the statement from the procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02932-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02932-109">See Also</span></span>  
 [<span data-ttu-id="02932-110">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="02932-110">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="02932-111">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="02932-111">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="02932-112">Istruzione Get</span><span class="sxs-lookup"><span data-stu-id="02932-112">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)  
 [<span data-ttu-id="02932-113">Istruzione Set</span><span class="sxs-lookup"><span data-stu-id="02932-113">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
