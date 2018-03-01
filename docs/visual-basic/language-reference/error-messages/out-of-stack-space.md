---
title: Spazio dello stack insufficiente (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID28
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3959c24aa4e95204e156a9863ef0ce237af1fcda
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="out-of-stack-space-visual-basic"></a><span data-ttu-id="8e551-102">Spazio dello stack insufficiente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e551-102">Out of stack space (Visual Basic)</span></span>
<span data-ttu-id="8e551-103">Lo stack è un'area di lavoro di memoria aumenta e si ridotta dinamicamente con le richieste del programma in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8e551-103">The stack is a working area of memory that grows and shrinks dynamically with the demands of your executing program.</span></span> <span data-ttu-id="8e551-104">Sono stati superati i limiti.</span><span class="sxs-lookup"><span data-stu-id="8e551-104">Its limits have been exceeded.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8e551-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="8e551-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="8e551-106">Verificare che le procedure non sono eccessivamente annidate.</span><span class="sxs-lookup"><span data-stu-id="8e551-106">Check that procedures are not nested too deeply.</span></span>  
  
2.  <span data-ttu-id="8e551-107">Verificare che le routine ricorsive terminino correttamente.</span><span class="sxs-lookup"><span data-stu-id="8e551-107">Make sure recursive procedures terminate properly.</span></span>  
  
3.  <span data-ttu-id="8e551-108">Se le variabili locali richiedono uno spazio più a quello disponibile, provare a dichiarare alcune variabili a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="8e551-108">If local variables require more local variable space than is available, try declaring some variables at the module level.</span></span> <span data-ttu-id="8e551-109">È anche possibile dichiarare tutte le variabili nella procedura static facendo precedere il `Property`, `Sub`, o `Function` parola chiave with `Static`.</span><span class="sxs-lookup"><span data-stu-id="8e551-109">You can also declare all variables in the procedure static by preceding the `Property`, `Sub`, or `Function` keyword with `Static`.</span></span> <span data-ttu-id="8e551-110">Oppure è possibile utilizzare il `Static` istruzione per dichiarare le variabili statiche singoli all'interno delle procedure.</span><span class="sxs-lookup"><span data-stu-id="8e551-110">Or you can use the `Static` statement to declare individual static variables within procedures.</span></span>  
  
4.  <span data-ttu-id="8e551-111">Ridefinire alcune stringhe a lunghezza fissa come stringhe a lunghezza variabile, come stringhe a lunghezza fissa richiedono più spazio di stack di stringhe a lunghezza variabile.</span><span class="sxs-lookup"><span data-stu-id="8e551-111">Redefine some of your fixed-length strings as variable-length strings, as fixed-length strings use more stack space than variable-length strings.</span></span> <span data-ttu-id="8e551-112">È inoltre possibile definire la stringa a livello di modulo in cui è necessario nessuno spazio dello stack.</span><span class="sxs-lookup"><span data-stu-id="8e551-112">You can also define the string at module level where it requires no stack space.</span></span>  
  
5.  <span data-ttu-id="8e551-113">Controllare il numero di nidificata `DoEvents` chiamate di funzioni, utilizzando il `Calls` finestra di dialogo per visualizzare le routine attive nello stack.</span><span class="sxs-lookup"><span data-stu-id="8e551-113">Check the number of nested `DoEvents` function calls, by using the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
6.  <span data-ttu-id="8e551-114">Assicurarsi che non si determinava "cascata di eventi" generando un evento che chiama una routine evento già nello stack.</span><span class="sxs-lookup"><span data-stu-id="8e551-114">Make sure you did not cause an "event cascade" by triggering an event that calls an event procedure already on the stack.</span></span> <span data-ttu-id="8e551-115">Una catena di eventi è simile a una chiamata di routine ricorsiva non terminata, ma è meno ovvio, poiché la chiamata viene effettuata da [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] invece di una chiamata esplicita nel codice.</span><span class="sxs-lookup"><span data-stu-id="8e551-115">An event cascade is similar to an unterminated recursive procedure call, but it is less obvious, since the call is made by [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] rather than an explicit call in the code.</span></span> <span data-ttu-id="8e551-116">Utilizzare il `Calls` finestra di dialogo per visualizzare le routine attive nello stack.</span><span class="sxs-lookup"><span data-stu-id="8e551-116">Use the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e551-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e551-117">See Also</span></span>  
 [<span data-ttu-id="8e551-118">Finestra Memoria</span><span class="sxs-lookup"><span data-stu-id="8e551-118">Memory Windows</span></span>](/visualstudio/debugger/memory-windows)
