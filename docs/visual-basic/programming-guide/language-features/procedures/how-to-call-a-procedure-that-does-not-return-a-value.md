---
title: 'Procedura: chiamare una routine che non restituisce un valore (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- procedure calls, returning values
- Visual Basic code, procedures
- procedures, calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
caps.latest.revision: 17
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
ms.openlocfilehash: 26120b763d2ecedb3aa43adb08e4c87c2b1e0be1
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a><span data-ttu-id="7e9ea-102">Procedura: chiamare una routine che non restituisce un valore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7e9ea-102">How to: Call a Procedure that Does Not Return a Value (Visual Basic)</span></span>
<span data-ttu-id="7e9ea-103">Oggetto `Sub` procedure non restituisce un valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="7e9ea-103">A `Sub` procedure does not return a value to the calling code.</span></span> <span data-ttu-id="7e9ea-104">Si chiama in modo esplicito con un'istruzione di chiamata autonoma.</span><span class="sxs-lookup"><span data-stu-id="7e9ea-104">You call it explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="7e9ea-105">È possibile effettuare la chiamata utilizzando semplicemente il nome all'interno di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="7e9ea-105">You cannot call it by simply using its name within an expression.</span></span>  
  
### <a name="to-call-a-sub-procedure"></a><span data-ttu-id="7e9ea-106">Per chiamare una routine Sub</span><span class="sxs-lookup"><span data-stu-id="7e9ea-106">To call a Sub procedure</span></span>  
  
1.  <span data-ttu-id="7e9ea-107">Nome del file di `Sub` procedura.</span><span class="sxs-lookup"><span data-stu-id="7e9ea-107">Specify the name of the `Sub` procedure.</span></span>  
  
2.  <span data-ttu-id="7e9ea-108">Aggiungere il nome tra parentesi per racchiudere l'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="7e9ea-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="7e9ea-109">Se non sono presenti argomenti, è possibile omettere le parentesi.</span><span class="sxs-lookup"><span data-stu-id="7e9ea-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="7e9ea-110">Tuttavia, l'utilizzo delle parentesi rende il codice più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="7e9ea-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="7e9ea-111">Inserire gli argomenti nell'elenco di argomenti all'interno delle parentesi, separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="7e9ea-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="7e9ea-112">Assicurarsi di inserire gli argomenti nello stesso ordine in cui la `Sub` procedura definisce i parametri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="7e9ea-112">Be sure you supply the arguments in the same order that the `Sub` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="7e9ea-113">Nell'esempio seguente viene chiamato il [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>funzione per attivare una finestra dell'applicazione.</xref:Microsoft.VisualBasic.Interaction.AppActivate%2A></span><span class="sxs-lookup"><span data-stu-id="7e9ea-113">The following example calls the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> function to activate an application window.</span></span> <span data-ttu-id="7e9ea-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>accetta il titolo della finestra come unico argomento.</xref:Microsoft.VisualBasic.Interaction.AppActivate%2A></span><span class="sxs-lookup"><span data-stu-id="7e9ea-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> takes the window title as its sole argument.</span></span> <span data-ttu-id="7e9ea-115">Non restituire un valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="7e9ea-115">It does not return a value to the calling code.</span></span> <span data-ttu-id="7e9ea-116">Se non viene eseguito un processo Blocco note, viene generata una <xref:System.ArgumentException>.</xref:System.ArgumentException></span><span class="sxs-lookup"><span data-stu-id="7e9ea-116">If a Notepad process is not running, the example throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="7e9ea-117">Il `Shell` procedura presuppone che le applicazioni siano nei percorsi specificati.</span><span class="sxs-lookup"><span data-stu-id="7e9ea-117">The `Shell` procedure assumes the applications are in the paths specified.</span></span>  
  
     <span data-ttu-id="7e9ea-118">[!code-vb[VbVbalrCatRef&#11;](./codesnippet/VisualBasic/how-to-call-a-procedure-that-does-not-return-a-value_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="7e9ea-118">[!code-vb[VbVbalrCatRef#11](./codesnippet/VisualBasic/how-to-call-a-procedure-that-does-not-return-a-value_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e9ea-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e9ea-119">See Also</span></span>  
 <span data-ttu-id="7e9ea-120"><xref:Microsoft.VisualBasic.Interaction.Shell%2A></xref:Microsoft.VisualBasic.Interaction.Shell%2A></span><span class="sxs-lookup"><span data-stu-id="7e9ea-120"><xref:Microsoft.VisualBasic.Interaction.Shell%2A></span></span>   
 <span data-ttu-id="7e9ea-121"><xref:System.ArgumentException></xref:System.ArgumentException></span><span class="sxs-lookup"><span data-stu-id="7e9ea-121"><xref:System.ArgumentException></span></span>   
<span data-ttu-id="7e9ea-122"> [Procedure](./index.md) </span><span class="sxs-lookup"><span data-stu-id="7e9ea-122"> [Procedures](./index.md) </span></span>  
<span data-ttu-id="7e9ea-123"> [Sub (routine)](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="7e9ea-123"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="7e9ea-124"> [Gli argomenti e parametri di routine](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="7e9ea-124"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="7e9ea-125"> [Sub (istruzione)](../../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="7e9ea-125"> [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="7e9ea-126"> [Procedura: creare una stored Procedure](./how-to-create-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="7e9ea-126"> [How to: Create a Procedure](./how-to-create-a-procedure.md) </span></span>  
<span data-ttu-id="7e9ea-127"> [Procedura: chiamare una routine che restituisce un valore](./how-to-call-a-procedure-that-returns-a-value.md) </span><span class="sxs-lookup"><span data-stu-id="7e9ea-127"> [How to: Call a Procedure That Returns a Value](./how-to-call-a-procedure-that-returns-a-value.md) </span></span>  
<span data-ttu-id="7e9ea-128"> [Procedura: chiamare un gestore eventi in Visual Basic](./how-to-call-an-event-handler.md)</span><span class="sxs-lookup"><span data-stu-id="7e9ea-128"> [How to: Call an Event Handler in Visual Basic](./how-to-call-an-event-handler.md)</span></span>
