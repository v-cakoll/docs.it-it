---
title: Spazio dello stack insufficiente
ms.date: 07/20/2015
f1_keywords:
- vbrID28
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
ms.openlocfilehash: 9ae604a9727413f2705d42a4b68f5a50b7dd3feb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349189"
---
# <a name="out-of-stack-space-visual-basic"></a><span data-ttu-id="44dff-102">Spazio dello stack insufficiente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="44dff-102">Out of stack space (Visual Basic)</span></span>
<span data-ttu-id="44dff-103">Lo stack è un'area di lavoro di memoria che aumenta e compatta dinamicamente con le esigenze del programma in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="44dff-103">The stack is a working area of memory that grows and shrinks dynamically with the demands of your executing program.</span></span> <span data-ttu-id="44dff-104">Sono stati superati i limiti.</span><span class="sxs-lookup"><span data-stu-id="44dff-104">Its limits have been exceeded.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="44dff-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="44dff-105">To correct this error</span></span>  
  
1. <span data-ttu-id="44dff-106">Verificare che le procedure non siano annidate troppo profondamente.</span><span class="sxs-lookup"><span data-stu-id="44dff-106">Check that procedures are not nested too deeply.</span></span>  
  
2. <span data-ttu-id="44dff-107">Verificare che le procedure ricorsive vengano terminate correttamente.</span><span class="sxs-lookup"><span data-stu-id="44dff-107">Make sure recursive procedures terminate properly.</span></span>  
  
3. <span data-ttu-id="44dff-108">Se le variabili locali richiedono più spazio variabile locale rispetto a quanto disponibile, provare a dichiarare alcune variabili a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="44dff-108">If local variables require more local variable space than is available, try declaring some variables at the module level.</span></span> <span data-ttu-id="44dff-109">È anche possibile dichiarare tutte le variabili nella procedura statica precedendo la parola chiave `Property`, `Sub`o `Function` con `Static`.</span><span class="sxs-lookup"><span data-stu-id="44dff-109">You can also declare all variables in the procedure static by preceding the `Property`, `Sub`, or `Function` keyword with `Static`.</span></span> <span data-ttu-id="44dff-110">In alternativa, è possibile usare l'istruzione `Static` per dichiarare singole variabili statiche all'interno delle procedure.</span><span class="sxs-lookup"><span data-stu-id="44dff-110">Or you can use the `Static` statement to declare individual static variables within procedures.</span></span>  
  
4. <span data-ttu-id="44dff-111">Ridefinire alcune stringhe a lunghezza fissa come stringhe a lunghezza variabile, poiché le stringhe a lunghezza fissa utilizzano più spazio dello stack rispetto alle stringhe a lunghezza variabile.</span><span class="sxs-lookup"><span data-stu-id="44dff-111">Redefine some of your fixed-length strings as variable-length strings, as fixed-length strings use more stack space than variable-length strings.</span></span> <span data-ttu-id="44dff-112">È anche possibile definire la stringa a livello di modulo, in cui non è necessario spazio dello stack.</span><span class="sxs-lookup"><span data-stu-id="44dff-112">You can also define the string at module level where it requires no stack space.</span></span>  
  
5. <span data-ttu-id="44dff-113">Controllare il numero di chiamate di funzione annidate `DoEvents` usando la finestra di dialogo `Calls` per visualizzare le procedure attive nello stack.</span><span class="sxs-lookup"><span data-stu-id="44dff-113">Check the number of nested `DoEvents` function calls, by using the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
6. <span data-ttu-id="44dff-114">Assicurarsi che non sia stato causato un evento "Cascade" tramite l'attivazione di un evento che chiama una routine di evento già presente nello stack.</span><span class="sxs-lookup"><span data-stu-id="44dff-114">Make sure you did not cause an "event cascade" by triggering an event that calls an event procedure already on the stack.</span></span> <span data-ttu-id="44dff-115">Un evento Cascade è simile a una chiamata di routine ricorsiva senza terminazione, ma è meno ovvio, perché la chiamata viene eseguita da Visual Basic anziché da una chiamata esplicita nel codice.</span><span class="sxs-lookup"><span data-stu-id="44dff-115">An event cascade is similar to an unterminated recursive procedure call, but it is less obvious, since the call is made by Visual Basic rather than an explicit call in the code.</span></span> <span data-ttu-id="44dff-116">Utilizzare la finestra di dialogo `Calls` per visualizzare le procedure attive nello stack.</span><span class="sxs-lookup"><span data-stu-id="44dff-116">Use the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44dff-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44dff-117">See also</span></span>

- [<span data-ttu-id="44dff-118">Finestra Memoria</span><span class="sxs-lookup"><span data-stu-id="44dff-118">Memory Windows</span></span>](/visualstudio/debugger/memory-windows)
