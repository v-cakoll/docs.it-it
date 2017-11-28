---
title: "&#39; Ottieni &#39; funzione di accesso della proprietà &#39; &lt;propertyname&gt;&#39; non è accessibile"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31103
- bc31103
helpviewer_keywords: BC31103
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 167e040570af1fc78ce48f5e930e54981ba909ae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="39get39-accessor-of-property-39ltpropertynamegt39-is-not-accessible"></a><span data-ttu-id="bc061-102">&#39; Ottieni &#39; funzione di accesso della proprietà &#39; &lt;propertyname&gt;&#39; non è accessibile</span><span class="sxs-lookup"><span data-stu-id="bc061-102">&#39;Get&#39; accessor of property &#39;&lt;propertyname&gt;&#39; is not accessible</span></span>
<span data-ttu-id="bc061-103">Un'istruzione tenta di recuperare il valore di una proprietà quando dispone di accesso per la proprietà `Get` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="bc061-103">A statement attempts to retrieve the value of a property when it does not have access to the property's `Get` procedure.</span></span>  
  
 <span data-ttu-id="bc061-104">Se il [l'istruzione Get](../../../visual-basic/language-reference/statements/get-statement.md) è contrassegnata con un accesso più restrittivo livello relativa [istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md), un tentativo di leggere il valore della proprietà potrebbe non riuscire nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bc061-104">If the [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md) is marked with a more restrictive access level than its [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), an attempt to read the property value could fail in the following cases:</span></span>  
  
-   <span data-ttu-id="bc061-105">Il `Get` è contrassegnata [privata](../../../visual-basic/language-reference/modifiers/private.md) e il codice chiamante è di fuori della classe o struttura in cui la proprietà è definita.</span><span class="sxs-lookup"><span data-stu-id="bc061-105">The `Get` statement is marked [Private](../../../visual-basic/language-reference/modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>  
  
-   <span data-ttu-id="bc061-106">Il `Get` è contrassegnata [Protected](../../../visual-basic/language-reference/modifiers/protected.md) e il codice chiamante non nella classe o struttura in cui la proprietà è definita, né in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="bc061-106">The `Get` statement is marked [Protected](../../../visual-basic/language-reference/modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>  
  
-   <span data-ttu-id="bc061-107">Il `Get` è contrassegnata [Friend](../../../visual-basic/language-reference/modifiers/friend.md) e il codice chiamante non è presente nello stesso assembly in cui la proprietà è definita.</span><span class="sxs-lookup"><span data-stu-id="bc061-107">The `Get` statement is marked [Friend](../../../visual-basic/language-reference/modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>  
  
 <span data-ttu-id="bc061-108">**ID errore:** BC31103</span><span class="sxs-lookup"><span data-stu-id="bc061-108">**Error ID:** BC31103</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bc061-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="bc061-109">To correct this error</span></span>  
  
-   <span data-ttu-id="bc061-110">Se si dispone di controllo del codice sorgente che definisce la proprietà, si consideri la dichiarazione di `Get` procedure con lo stesso livello di accesso della proprietà stessa.</span><span class="sxs-lookup"><span data-stu-id="bc061-110">If you have control of the source code defining the property, consider declaring the `Get` procedure with the same access level as the property itself.</span></span>  
  
-   <span data-ttu-id="bc061-111">Se non si dispone del controllo del codice sorgente che definisce la proprietà o se è necessario limitare il `Get` procedure livello di accesso più la proprietà stessa, provare a spostare l'istruzione che legge il valore della proprietà per un'area di codice che dispone di un accesso migliore per il proprietà.</span><span class="sxs-lookup"><span data-stu-id="bc061-111">If you do not have control of the source code defining the property, or you must restrict the `Get` procedure access level more than the property itself, try to move the statement that reads the property value to a region of code that has better access to the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc061-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc061-112">See Also</span></span>  
 [<span data-ttu-id="bc061-113">Routine Property</span><span class="sxs-lookup"><span data-stu-id="bc061-113">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [<span data-ttu-id="bc061-114">Procedura: Dichiarare una proprietà con livelli di accesso misti</span><span class="sxs-lookup"><span data-stu-id="bc061-114">How to: Declare a Property with Mixed Access Levels</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
