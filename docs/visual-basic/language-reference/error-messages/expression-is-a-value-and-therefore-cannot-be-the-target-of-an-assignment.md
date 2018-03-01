---
title: "L'espressione è un valore, quindi non può essere la destinazione di un'assegnazione"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords:
- BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bec3e2d298160bd0b459dc3b7ef93b94648e439a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="expression-is-a-value-and-therefore-cannot-be-the-target-of-an-assignment"></a><span data-ttu-id="2dcc5-102">L'espressione è un valore, quindi non può essere la destinazione di un'assegnazione</span><span class="sxs-lookup"><span data-stu-id="2dcc5-102">Expression is a value and therefore cannot be the target of an assignment</span></span>
<span data-ttu-id="2dcc5-103">Un'istruzione tenta di assegnare un valore a un'espressione.</span><span class="sxs-lookup"><span data-stu-id="2dcc5-103">A statement attempts to assign a value to an expression.</span></span> <span data-ttu-id="2dcc5-104">È possibile assegnare un valore solo a una variabile scrivibile, una proprietà o un elemento della matrice in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2dcc5-104">You can assign a value only to a writable variable, property, or array element at run time.</span></span> <span data-ttu-id="2dcc5-105">Nell'esempio seguente viene illustrato come questo errore può verificarsi.</span><span class="sxs-lookup"><span data-stu-id="2dcc5-105">The following example illustrates how this error can occur.</span></span>  
  
```  
Dim yesterday As Integer  
ReadOnly maximum As Integer = 45  
yesterday + 1 = DatePart(DateInterval.Day, Now)  
' The preceding line is an ERROR because of an expression on the left.  
maximum = 50  
' The preceding line is an ERROR because maximum is declared ReadOnly.  
```  
  
 <span data-ttu-id="2dcc5-106">Esempi simili possibile applicare alle proprietà e gli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="2dcc5-106">Similar examples could apply to properties and array elements.</span></span>  
  
 <span data-ttu-id="2dcc5-107">**Accesso indiretto.**</span><span class="sxs-lookup"><span data-stu-id="2dcc5-107">**Indirect Access.**</span></span> <span data-ttu-id="2dcc5-108">Accesso indiretto attraverso un tipo di valore può inoltre generare questo errore.</span><span class="sxs-lookup"><span data-stu-id="2dcc5-108">Indirect access through a value type can also generate this error.</span></span> <span data-ttu-id="2dcc5-109">Si consideri l'esempio di codice riportato di seguito, che tenta di impostare il valore di <xref:System.Drawing.Point> accedendovi indirettamente tramite <xref:System.Windows.Forms.Control.Location%2A>.</span><span class="sxs-lookup"><span data-stu-id="2dcc5-109">Consider the following code example, which attempts to set the value of <xref:System.Drawing.Point> by accessing it indirectly through <xref:System.Windows.Forms.Control.Location%2A>.</span></span>  
  
```  
' Assume this code runs inside Form1.  
Dim exitButton As New System.Windows.Forms.Button()  
exitButton.Text = "Exit this form"  
exitButton.Location.X = 140  
' The preceding line is an ERROR because of no storage for Location.  
```  
  
 <span data-ttu-id="2dcc5-110">L'ultima istruzione dell'esempio precedente ha esito negativo poiché crea solo un'allocazione temporanea per il <xref:System.Drawing.Point> restituito dalla struttura di <xref:System.Windows.Forms.Control.Location%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="2dcc5-110">The last statement of the preceding example fails because it creates only a temporary allocation for the <xref:System.Drawing.Point> structure returned by the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span> <span data-ttu-id="2dcc5-111">Una struttura è un tipo di valore e la struttura temporanea non viene mantenuta dopo l'istruzione viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="2dcc5-111">A structure is a value type, and the temporary structure is not retained after the statement runs.</span></span> <span data-ttu-id="2dcc5-112">Il problema viene risolto dichiarando e utilizzando una variabile per <xref:System.Windows.Forms.Control.Location%2A>, che consente di creare un'allocazione più permanente per la <xref:System.Drawing.Point> struttura.</span><span class="sxs-lookup"><span data-stu-id="2dcc5-112">The problem is resolved by declaring and using a variable for <xref:System.Windows.Forms.Control.Location%2A>, which creates a more permanent allocation for the <xref:System.Drawing.Point> structure.</span></span> <span data-ttu-id="2dcc5-113">Nell'esempio seguente viene illustrato il codice che è possibile sostituire l'ultima istruzione dell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="2dcc5-113">The following example shows code that can replace the last statement of the preceding example.</span></span>  
  
```  
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)  
exitButton.Location = exitLocation  
```  
  
 <span data-ttu-id="2dcc5-114">**ID errore:** BC30068</span><span class="sxs-lookup"><span data-stu-id="2dcc5-114">**Error ID:** BC30068</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2dcc5-115">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="2dcc5-115">To correct this error</span></span>  
  
-   <span data-ttu-id="2dcc5-116">Se l'istruzione assegna un valore a un'espressione, è possibile sostituire l'espressione a una singola variabile scrivibile, una proprietà o un elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="2dcc5-116">If the statement assigns a value to an expression, replace the expression with a single writable variable, property, or array element.</span></span>  
  
-   <span data-ttu-id="2dcc5-117">Se l'istruzione effettua l'accesso indiretto attraverso un tipo di valore (in genere una struttura), creare una variabile per contenere il tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="2dcc5-117">If the statement makes indirect access through a value type (usually a structure), create a variable to hold the value type.</span></span>  
  
-   <span data-ttu-id="2dcc5-118">Assegnare la struttura appropriata (o altro tipo di valore) alla variabile.</span><span class="sxs-lookup"><span data-stu-id="2dcc5-118">Assign the appropriate structure (or other value type) to the variable.</span></span>  
  
-   <span data-ttu-id="2dcc5-119">Utilizzare la variabile per accedere alla proprietà per assegnare un valore.</span><span class="sxs-lookup"><span data-stu-id="2dcc5-119">Use the variable to access the property to assign it a value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dcc5-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2dcc5-120">See Also</span></span>  
 [<span data-ttu-id="2dcc5-121">Operatori ed espressioni</span><span class="sxs-lookup"><span data-stu-id="2dcc5-121">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="2dcc5-122">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="2dcc5-122">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 [<span data-ttu-id="2dcc5-123">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="2dcc5-123">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
