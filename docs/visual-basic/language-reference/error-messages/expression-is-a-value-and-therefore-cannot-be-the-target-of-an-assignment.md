---
title: L'espressione è un valore, quindi non può essere la destinazione di un'assegnazione
ms.date: 07/20/2015
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords:
- BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
ms.openlocfilehash: 3027be6ee4ed3664b81c661b6a086a3604573833
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826133"
---
# <a name="expression-is-a-value-and-therefore-cannot-be-the-target-of-an-assignment"></a><span data-ttu-id="178c9-102">L'espressione è un valore, quindi non può essere la destinazione di un'assegnazione</span><span class="sxs-lookup"><span data-stu-id="178c9-102">Expression is a value and therefore cannot be the target of an assignment</span></span>
<span data-ttu-id="178c9-103">Un'istruzione prova ad assegnare un valore a un'espressione.</span><span class="sxs-lookup"><span data-stu-id="178c9-103">A statement attempts to assign a value to an expression.</span></span> <span data-ttu-id="178c9-104">È possibile assegnare un valore solo a una variabile scrivibile, una proprietà o un elemento della matrice in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="178c9-104">You can assign a value only to a writable variable, property, or array element at run time.</span></span> <span data-ttu-id="178c9-105">Nell'esempio seguente viene illustrato come questo errore può verificarsi.</span><span class="sxs-lookup"><span data-stu-id="178c9-105">The following example illustrates how this error can occur.</span></span>  
  
```  
Dim yesterday As Integer  
ReadOnly maximum As Integer = 45  
yesterday + 1 = DatePart(DateInterval.Day, Now)  
' The preceding line is an ERROR because of an expression on the left.  
maximum = 50  
' The preceding line is an ERROR because maximum is declared ReadOnly.  
```  
  
 <span data-ttu-id="178c9-106">Esempi simili è stato possibile applicare alle proprietà e gli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="178c9-106">Similar examples could apply to properties and array elements.</span></span>  
  
 <span data-ttu-id="178c9-107">**Accesso indiretto.**</span><span class="sxs-lookup"><span data-stu-id="178c9-107">**Indirect Access.**</span></span> <span data-ttu-id="178c9-108">Accesso indiretto tramite un tipo di valore può anche generare questo errore.</span><span class="sxs-lookup"><span data-stu-id="178c9-108">Indirect access through a value type can also generate this error.</span></span> <span data-ttu-id="178c9-109">Si consideri l'esempio di codice riportato di seguito, che tenta di impostare il valore della <xref:System.Drawing.Point> accedendovi indirettamente tramite <xref:System.Windows.Forms.Control.Location%2A>.</span><span class="sxs-lookup"><span data-stu-id="178c9-109">Consider the following code example, which attempts to set the value of <xref:System.Drawing.Point> by accessing it indirectly through <xref:System.Windows.Forms.Control.Location%2A>.</span></span>  
  
```  
' Assume this code runs inside Form1.  
Dim exitButton As New System.Windows.Forms.Button()  
exitButton.Text = "Exit this form"  
exitButton.Location.X = 140  
' The preceding line is an ERROR because of no storage for Location.  
```  
  
 <span data-ttu-id="178c9-110">L'ultima istruzione dell'esempio precedente ha esito negativo perché crea solo un'allocazione temporanea per il <xref:System.Drawing.Point> struttura restituita dal <xref:System.Windows.Forms.Control.Location%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="178c9-110">The last statement of the preceding example fails because it creates only a temporary allocation for the <xref:System.Drawing.Point> structure returned by the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span> <span data-ttu-id="178c9-111">Una struttura è un tipo di valore e la struttura temporanea non viene mantenuta dopo l'esecuzione dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="178c9-111">A structure is a value type, and the temporary structure is not retained after the statement runs.</span></span> <span data-ttu-id="178c9-112">Il problema viene risolto dichiarando e utilizzando una variabile per <xref:System.Windows.Forms.Control.Location%2A>, che crea un'allocazione di più permanente per il <xref:System.Drawing.Point> struttura.</span><span class="sxs-lookup"><span data-stu-id="178c9-112">The problem is resolved by declaring and using a variable for <xref:System.Windows.Forms.Control.Location%2A>, which creates a more permanent allocation for the <xref:System.Drawing.Point> structure.</span></span> <span data-ttu-id="178c9-113">Nell'esempio seguente viene illustrato il codice che è possibile sostituire l'ultima istruzione dell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="178c9-113">The following example shows code that can replace the last statement of the preceding example.</span></span>  
  
```  
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)  
exitButton.Location = exitLocation  
```  
  
 <span data-ttu-id="178c9-114">**ID errore:** BC30068</span><span class="sxs-lookup"><span data-stu-id="178c9-114">**Error ID:** BC30068</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="178c9-115">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="178c9-115">To correct this error</span></span>  
  
-   <span data-ttu-id="178c9-116">Se l'istruzione viene assegnato un valore a un'espressione, sostituire l'espressione con una singola variabile scrivibile, proprietà o elemento di matrice.</span><span class="sxs-lookup"><span data-stu-id="178c9-116">If the statement assigns a value to an expression, replace the expression with a single writable variable, property, or array element.</span></span>  
  
-   <span data-ttu-id="178c9-117">Se l'istruzione effettua l'accesso indiretto tramite un tipo di valore (in genere una struttura), creare una variabile per contenere il tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="178c9-117">If the statement makes indirect access through a value type (usually a structure), create a variable to hold the value type.</span></span>  
  
-   <span data-ttu-id="178c9-118">Assegnare la struttura appropriata (o altro tipo di valore) alla variabile.</span><span class="sxs-lookup"><span data-stu-id="178c9-118">Assign the appropriate structure (or other value type) to the variable.</span></span>  
  
-   <span data-ttu-id="178c9-119">Usare la variabile per accedere alla proprietà per assegnare un valore.</span><span class="sxs-lookup"><span data-stu-id="178c9-119">Use the variable to access the property to assign it a value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="178c9-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="178c9-120">See also</span></span>

- [<span data-ttu-id="178c9-121">Operatori ed espressioni</span><span class="sxs-lookup"><span data-stu-id="178c9-121">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="178c9-122">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="178c9-122">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="178c9-123">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="178c9-123">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
