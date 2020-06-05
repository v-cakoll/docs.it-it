---
title: 'Procedura: chiamare una routine che non restituisce un valore'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: 514d6e576b9b782387840ae04dcefa00de876aa9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388738"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a><span data-ttu-id="60718-102">Procedura: chiamare una routine che non restituisce un valore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="60718-102">How to: Call a Procedure that Does Not Return a Value (Visual Basic)</span></span>
<span data-ttu-id="60718-103">Una `Sub` routine non restituisce un valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="60718-103">A `Sub` procedure does not return a value to the calling code.</span></span> <span data-ttu-id="60718-104">Viene chiamato in modo esplicito con un'istruzione di chiamata autonoma.</span><span class="sxs-lookup"><span data-stu-id="60718-104">You call it explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="60718-105">Non è possibile chiamarlo utilizzando semplicemente il nome all'interno di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="60718-105">You cannot call it by simply using its name within an expression.</span></span>  
  
### <a name="to-call-a-sub-procedure"></a><span data-ttu-id="60718-106">Per chiamare una procedura secondaria</span><span class="sxs-lookup"><span data-stu-id="60718-106">To call a Sub procedure</span></span>  
  
1. <span data-ttu-id="60718-107">Specificare il nome della `Sub` procedura.</span><span class="sxs-lookup"><span data-stu-id="60718-107">Specify the name of the `Sub` procedure.</span></span>  
  
2. <span data-ttu-id="60718-108">Seguire il nome della procedura con le parentesi per racchiudere l'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="60718-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="60718-109">Se non è presente alcun argomento, è possibile omettere facoltativamente le parentesi.</span><span class="sxs-lookup"><span data-stu-id="60718-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="60718-110">Tuttavia, l'utilizzo delle parentesi rende il codice più semplice da leggere.</span><span class="sxs-lookup"><span data-stu-id="60718-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="60718-111">Inserire gli argomenti nell'elenco di argomenti tra parentesi, separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="60718-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="60718-112">Assicurarsi di specificare gli argomenti nello stesso ordine in cui la `Sub` procedura definisce i parametri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="60718-112">Be sure you supply the arguments in the same order that the `Sub` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="60718-113">Nell'esempio seguente viene chiamata la <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> funzione Visual Basic per attivare una finestra dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="60718-113">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> function to activate an application window.</span></span> <span data-ttu-id="60718-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>accetta il titolo della finestra come unico argomento.</span><span class="sxs-lookup"><span data-stu-id="60718-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> takes the window title as its sole argument.</span></span> <span data-ttu-id="60718-115">Non restituisce un valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="60718-115">It does not return a value to the calling code.</span></span> <span data-ttu-id="60718-116">Se un processo del blocco note non è in esecuzione, nell'esempio viene generata un'eccezione <xref:System.ArgumentException> .</span><span class="sxs-lookup"><span data-stu-id="60718-116">If a Notepad process is not running, the example throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="60718-117">Nella `Shell` procedura si presuppone che le applicazioni si trovino nei percorsi specificati.</span><span class="sxs-lookup"><span data-stu-id="60718-117">The `Shell` procedure assumes the applications are in the paths specified.</span></span>  
  
     [!code-vb[VbVbalrCatRef#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCatRef/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="60718-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60718-118">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [<span data-ttu-id="60718-119">Procedure</span><span class="sxs-lookup"><span data-stu-id="60718-119">Procedures</span></span>](./index.md)
- [<span data-ttu-id="60718-120">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="60718-120">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="60718-121">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="60718-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="60718-122">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="60718-122">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="60718-123">Procedura: Creare una routine</span><span class="sxs-lookup"><span data-stu-id="60718-123">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)
- [<span data-ttu-id="60718-124">Procedura: chiamare una routine che restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="60718-124">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="60718-125">Procedura: chiamare un gestore eventi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="60718-125">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
