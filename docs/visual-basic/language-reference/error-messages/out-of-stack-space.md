---
title: Spazio dello stack insufficiente (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID28
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
ms.openlocfilehash: 29dbdf74808fc98bb856483c3fd8e3a09a72113b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59318793"
---
# <a name="out-of-stack-space-visual-basic"></a><span data-ttu-id="97c89-102">Spazio dello stack insufficiente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97c89-102">Out of stack space (Visual Basic)</span></span>
<span data-ttu-id="97c89-103">Lo stack è un'area di lavoro di memoria aumenta e si ridotta dinamicamente con le esigenze del programma in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="97c89-103">The stack is a working area of memory that grows and shrinks dynamically with the demands of your executing program.</span></span> <span data-ttu-id="97c89-104">Sono stati superati i limiti massimi.</span><span class="sxs-lookup"><span data-stu-id="97c89-104">Its limits have been exceeded.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="97c89-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="97c89-105">To correct this error</span></span>  
  
1. <span data-ttu-id="97c89-106">Verificare che le procedure non elaborati annidate troppo profondamente.</span><span class="sxs-lookup"><span data-stu-id="97c89-106">Check that procedures are not nested too deeply.</span></span>  
  
2. <span data-ttu-id="97c89-107">Assicurarsi che le routine ricorsive terminino correttamente.</span><span class="sxs-lookup"><span data-stu-id="97c89-107">Make sure recursive procedures terminate properly.</span></span>  
  
3. <span data-ttu-id="97c89-108">Se le variabili locali richiedono uno spazio più a quello disponibile, provare a dichiarare alcune variabili a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="97c89-108">If local variables require more local variable space than is available, try declaring some variables at the module level.</span></span> <span data-ttu-id="97c89-109">È anche possibile dichiarare come statici tutte le variabili nella procedura facendo precedere il `Property`, `Sub`, o `Function` parola chiave with `Static`.</span><span class="sxs-lookup"><span data-stu-id="97c89-109">You can also declare all variables in the procedure static by preceding the `Property`, `Sub`, or `Function` keyword with `Static`.</span></span> <span data-ttu-id="97c89-110">In alternativa è possibile usare il `Static` dichiarare singole variabili statiche all'interno delle routine dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="97c89-110">Or you can use the `Static` statement to declare individual static variables within procedures.</span></span>  
  
4. <span data-ttu-id="97c89-111">Ridefinire alcune delle stringhe a lunghezza fissa sotto forma di stringhe a lunghezza variabile, come stringhe a lunghezza fissa utilizzino più spazio di stack più stringhe a lunghezza variabile.</span><span class="sxs-lookup"><span data-stu-id="97c89-111">Redefine some of your fixed-length strings as variable-length strings, as fixed-length strings use more stack space than variable-length strings.</span></span> <span data-ttu-id="97c89-112">È anche possibile definire la stringa a livello di modulo in cui è non necessario alcun spazio dello stack.</span><span class="sxs-lookup"><span data-stu-id="97c89-112">You can also define the string at module level where it requires no stack space.</span></span>  
  
5. <span data-ttu-id="97c89-113">Controllare il numero di annidato `DoEvents` chiamate a funzioni, usando il `Calls` finestra di dialogo per visualizzare quali procedure attive nello stack.</span><span class="sxs-lookup"><span data-stu-id="97c89-113">Check the number of nested `DoEvents` function calls, by using the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
6. <span data-ttu-id="97c89-114">Assicurarsi che non si ha provocato una "catena di eventi" generando un evento che chiama una routine evento già nello stack.</span><span class="sxs-lookup"><span data-stu-id="97c89-114">Make sure you did not cause an "event cascade" by triggering an event that calls an event procedure already on the stack.</span></span> <span data-ttu-id="97c89-115">Una catena di eventi è simile a una chiamata di routine ricorsive senza terminazione, ma è meno ovvio, poiché viene effettuata la chiamata da Visual Basic piuttosto che una chiamata esplicita nel codice.</span><span class="sxs-lookup"><span data-stu-id="97c89-115">An event cascade is similar to an unterminated recursive procedure call, but it is less obvious, since the call is made by Visual Basic rather than an explicit call in the code.</span></span> <span data-ttu-id="97c89-116">Usare il `Calls` finestra di dialogo per visualizzare quali procedure attive nello stack.</span><span class="sxs-lookup"><span data-stu-id="97c89-116">Use the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97c89-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97c89-117">See also</span></span>

- [<span data-ttu-id="97c89-118">Finestra Memoria</span><span class="sxs-lookup"><span data-stu-id="97c89-118">Memory Windows</span></span>](/visualstudio/debugger/memory-windows)
