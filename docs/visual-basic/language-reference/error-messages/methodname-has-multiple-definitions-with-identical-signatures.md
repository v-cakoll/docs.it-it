---
title: "&#39; &lt;NomeMetodo&gt;&#39; dispone di più definizioni con firme identiche"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords: BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1a71d51690d6318a559a94ac81de625289d7587d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="39ltmethodnamegt39-has-multiple-definitions-with-identical-signatures"></a><span data-ttu-id="8b2d5-102">&#39; &lt;NomeMetodo&gt;&#39; dispone di più definizioni con firme identiche</span><span class="sxs-lookup"><span data-stu-id="8b2d5-102">&#39;&lt;methodname&gt;&#39; has multiple definitions with identical signatures</span></span>
<span data-ttu-id="8b2d5-103">Oggetto `Function` o `Sub` dichiarazione di routine utilizza l'elenco di procedure identiche nome e l'argomento di una dichiarazione precedente.</span><span class="sxs-lookup"><span data-stu-id="8b2d5-103">A `Function` or `Sub` procedure declaration uses the identical procedure name and argument list as a previous declaration.</span></span> <span data-ttu-id="8b2d5-104">Una possibile causa è un tentativo di eseguire l'overload di routine originale.</span><span class="sxs-lookup"><span data-stu-id="8b2d5-104">One possible cause is an attempt to overload the original procedure.</span></span> <span data-ttu-id="8b2d5-105">Le routine di overload devono avere elenchi di argomenti diverso.</span><span class="sxs-lookup"><span data-stu-id="8b2d5-105">Overloaded procedures must have different argument lists.</span></span>  
  
 <span data-ttu-id="8b2d5-106">**ID errore:** BC30269</span><span class="sxs-lookup"><span data-stu-id="8b2d5-106">**Error ID:** BC30269</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8b2d5-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="8b2d5-107">To correct this error</span></span>  
  
-   <span data-ttu-id="8b2d5-108">Modificare il nome della stored procedure o l'elenco di argomenti o rimuovere la dichiarazione duplicata.</span><span class="sxs-lookup"><span data-stu-id="8b2d5-108">Change the procedure name or the argument list, or remove the duplicate declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b2d5-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b2d5-109">See Also</span></span>  
 [<span data-ttu-id="8b2d5-110">Riferimenti a elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="8b2d5-110">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="8b2d5-111">Considerazioni sull'overload di routine</span><span class="sxs-lookup"><span data-stu-id="8b2d5-111">Considerations in Overloading Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
