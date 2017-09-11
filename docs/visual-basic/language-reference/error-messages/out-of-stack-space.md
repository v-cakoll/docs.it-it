---
title: (Visual Basic) di spazio dello stack | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID28
dev_langs:
- VB
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 256ef0c7fcb3632e0c13d12737d438225343884f
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="out-of-stack-space-visual-basic"></a><span data-ttu-id="13895-102">Spazio dello stack insufficiente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="13895-102">Out of stack space (Visual Basic)</span></span>
<span data-ttu-id="13895-103">Lo stack è un'area di lavoro di memoria aumenta e si riduce in modo dinamico alle richieste del programma in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="13895-103">The stack is a working area of memory that grows and shrinks dynamically with the demands of your executing program.</span></span> <span data-ttu-id="13895-104">I limiti sono stati superati.</span><span class="sxs-lookup"><span data-stu-id="13895-104">Its limits have been exceeded.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="13895-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="13895-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="13895-106">Verificare che le procedure non sono eccessivamente annidate.</span><span class="sxs-lookup"><span data-stu-id="13895-106">Check that procedures are not nested too deeply.</span></span>  
  
2.  <span data-ttu-id="13895-107">Assicurarsi che le routine ricorsive terminino correttamente.</span><span class="sxs-lookup"><span data-stu-id="13895-107">Make sure recursive procedures terminate properly.</span></span>  
  
3.  <span data-ttu-id="13895-108">Se le variabili locali richiedono uno spazio più a quello disponibile, provare a dichiarare alcune variabili a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="13895-108">If local variables require more local variable space than is available, try declaring some variables at the module level.</span></span> <span data-ttu-id="13895-109">È inoltre possibile dichiarare tutte le variabili nella procedura static facendo precedere il `Property`, `Sub`, o `Function` parola chiave with `Static`.</span><span class="sxs-lookup"><span data-stu-id="13895-109">You can also declare all variables in the procedure static by preceding the `Property`, `Sub`, or `Function` keyword with `Static`.</span></span> <span data-ttu-id="13895-110">Oppure è possibile utilizzare il `Static` istruzione per dichiarare variabili static individuali all'interno delle procedure.</span><span class="sxs-lookup"><span data-stu-id="13895-110">Or you can use the `Static` statement to declare individual static variables within procedures.</span></span>  
  
4.  <span data-ttu-id="13895-111">Ridefinire alcune delle stringhe a lunghezza fissa come stringhe a lunghezza variabile, come stringhe a lunghezza fissa utilizzino più spazio di stack di stringhe a lunghezza variabile.</span><span class="sxs-lookup"><span data-stu-id="13895-111">Redefine some of your fixed-length strings as variable-length strings, as fixed-length strings use more stack space than variable-length strings.</span></span> <span data-ttu-id="13895-112">È inoltre possibile definire la stringa a livello di modulo in cui richiede nessuno spazio dello stack.</span><span class="sxs-lookup"><span data-stu-id="13895-112">You can also define the string at module level where it requires no stack space.</span></span>  
  
5.  <span data-ttu-id="13895-113">Verificare il numero di nidificata `DoEvents` chiamate di funzioni, utilizzando il `Calls` la finestra di dialogo per visualizzare le routine attive nello stack.</span><span class="sxs-lookup"><span data-stu-id="13895-113">Check the number of nested `DoEvents` function calls, by using the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
6.  <span data-ttu-id="13895-114">Assicurarsi che non si ha provocato una cascata di"eventi" generando un evento che chiama una routine evento già nello stack.</span><span class="sxs-lookup"><span data-stu-id="13895-114">Make sure you did not cause an "event cascade" by triggering an event that calls an event procedure already on the stack.</span></span> <span data-ttu-id="13895-115">Una cascata di eventi è simile a una chiamata di routine ricorsiva non terminata, ma è meno ovvio, poiché la chiamata viene effettuata da [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] invece di una chiamata esplicita nel codice.</span><span class="sxs-lookup"><span data-stu-id="13895-115">An event cascade is similar to an unterminated recursive procedure call, but it is less obvious, since the call is made by [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] rather than an explicit call in the code.</span></span> <span data-ttu-id="13895-116">Utilizzare il `Calls`la finestra di dialogo per visualizzare le routine attive nello stack.</span><span class="sxs-lookup"><span data-stu-id="13895-116">Use the `Calls`dialog box to view which procedures are active on the stack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13895-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13895-117">See Also</span></span>  
 [<span data-ttu-id="13895-118">Finestra Memoria</span><span class="sxs-lookup"><span data-stu-id="13895-118">Memory Windows</span></span>](https://docs.microsoft.com/visualstudio/debugger/memory-windows)
