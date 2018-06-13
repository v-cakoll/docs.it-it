---
title: 'Procedura: chiamare una routine che non restituisce un valore (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: cf136f1486645d6e8e4b5856c0b1baf9e99f6c50
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649048"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a><span data-ttu-id="2e26e-102">Procedura: chiamare una routine che non restituisce un valore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2e26e-102">How to: Call a Procedure that Does Not Return a Value (Visual Basic)</span></span>
<span data-ttu-id="2e26e-103">Oggetto `Sub` routine non ha restituito un valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="2e26e-103">A `Sub` procedure does not return a value to the calling code.</span></span> <span data-ttu-id="2e26e-104">Si chiama in modo esplicito con un'istruzione di chiamata autonoma.</span><span class="sxs-lookup"><span data-stu-id="2e26e-104">You call it explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="2e26e-105">È possibile effettuare la chiamata utilizzando semplicemente il nome all'interno di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="2e26e-105">You cannot call it by simply using its name within an expression.</span></span>  
  
### <a name="to-call-a-sub-procedure"></a><span data-ttu-id="2e26e-106">Per chiamare una routine Sub</span><span class="sxs-lookup"><span data-stu-id="2e26e-106">To call a Sub procedure</span></span>  
  
1.  <span data-ttu-id="2e26e-107">Nome del file di `Sub` procedura.</span><span class="sxs-lookup"><span data-stu-id="2e26e-107">Specify the name of the `Sub` procedure.</span></span>  
  
2.  <span data-ttu-id="2e26e-108">Aggiungere il nome tra parentesi per racchiudere l'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="2e26e-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="2e26e-109">Se non sono presenti argomenti, è possibile omettere le parentesi.</span><span class="sxs-lookup"><span data-stu-id="2e26e-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="2e26e-110">Tuttavia, l'utilizzo delle parentesi, il codice più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="2e26e-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="2e26e-111">Posizionare gli argomenti nell'elenco di argomenti all'interno delle parentesi, separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="2e26e-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="2e26e-112">Assicurarsi fornire gli argomenti nello stesso ordine in cui il `Sub` procedure definisce i parametri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="2e26e-112">Be sure you supply the arguments in the same order that the `Sub` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="2e26e-113">Nell'esempio seguente chiama Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> funzione per attivare una finestra dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2e26e-113">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> function to activate an application window.</span></span> <span data-ttu-id="2e26e-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> accetta il titolo della finestra come unico argomento.</span><span class="sxs-lookup"><span data-stu-id="2e26e-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> takes the window title as its sole argument.</span></span> <span data-ttu-id="2e26e-115">Non restituire un valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="2e26e-115">It does not return a value to the calling code.</span></span> <span data-ttu-id="2e26e-116">Se non è in esecuzione un processo Blocco note, viene generata una <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="2e26e-116">If a Notepad process is not running, the example throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="2e26e-117">Il `Shell` procedura presuppone che le applicazioni siano nei percorsi specificati.</span><span class="sxs-lookup"><span data-stu-id="2e26e-117">The `Shell` procedure assumes the applications are in the paths specified.</span></span>  
  
     [!code-vb[VbVbalrCatRef#11](./codesnippet/VisualBasic/how-to-call-a-procedure-that-does-not-return-a-value_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="2e26e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e26e-118">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A>  
 <xref:System.ArgumentException>  
 [<span data-ttu-id="2e26e-119">Routine</span><span class="sxs-lookup"><span data-stu-id="2e26e-119">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="2e26e-120">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="2e26e-120">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="2e26e-121">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="2e26e-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="2e26e-122">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="2e26e-122">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="2e26e-123">Procedura: Creare una routine</span><span class="sxs-lookup"><span data-stu-id="2e26e-123">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)  
 [<span data-ttu-id="2e26e-124">Procedura: Chiamare una routine che restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="2e26e-124">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)  
 [<span data-ttu-id="2e26e-125">Procedura: chiamare un gestore eventi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2e26e-125">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
