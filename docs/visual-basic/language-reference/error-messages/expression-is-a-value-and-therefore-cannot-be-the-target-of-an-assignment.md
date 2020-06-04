---
title: L'espressione è un valore, quindi non può essere la destinazione di un'assegnazione
ms.date: 07/20/2015
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords:
- BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
ms.openlocfilehash: 9e4dbaf2f2800454c673cd58ddec4cf0f6e5c6b9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409507"
---
# <a name="expression-is-a-value-and-therefore-cannot-be-the-target-of-an-assignment"></a><span data-ttu-id="46af4-102">L'espressione è un valore, quindi non può essere la destinazione di un'assegnazione</span><span class="sxs-lookup"><span data-stu-id="46af4-102">Expression is a value and therefore cannot be the target of an assignment</span></span>

<span data-ttu-id="46af4-103">Un'istruzione tenta di assegnare un valore a un'espressione.</span><span class="sxs-lookup"><span data-stu-id="46af4-103">A statement attempts to assign a value to an expression.</span></span> <span data-ttu-id="46af4-104">È possibile assegnare un valore solo a una variabile scrivibile, a una proprietà o a un elemento di matrice in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="46af4-104">You can assign a value only to a writable variable, property, or array element at run time.</span></span> <span data-ttu-id="46af4-105">Nell'esempio seguente viene illustrato come può verificarsi l'errore.</span><span class="sxs-lookup"><span data-stu-id="46af4-105">The following example illustrates how this error can occur.</span></span>

```vb
Dim yesterday As Integer
ReadOnly maximum As Integer = 45
yesterday + 1 = DatePart(DateInterval.Day, Now)
' The preceding line is an ERROR because of an expression on the left.
maximum = 50
' The preceding line is an ERROR because maximum is declared ReadOnly.
```

<span data-ttu-id="46af4-106">Esempi simili possono essere applicati alle proprietà e agli elementi di matrice.</span><span class="sxs-lookup"><span data-stu-id="46af4-106">Similar examples could apply to properties and array elements.</span></span>

<span data-ttu-id="46af4-107">**Accesso indiretto.**</span><span class="sxs-lookup"><span data-stu-id="46af4-107">**Indirect Access.**</span></span> <span data-ttu-id="46af4-108">L'accesso indiretto tramite un tipo di valore può anche generare questo errore.</span><span class="sxs-lookup"><span data-stu-id="46af4-108">Indirect access through a value type can also generate this error.</span></span> <span data-ttu-id="46af4-109">Si consideri l'esempio di codice seguente, che tenta di impostare il valore di <xref:System.Drawing.Point> accedendo indirettamente tramite <xref:System.Windows.Forms.Control.Location%2A> .</span><span class="sxs-lookup"><span data-stu-id="46af4-109">Consider the following code example, which attempts to set the value of <xref:System.Drawing.Point> by accessing it indirectly through <xref:System.Windows.Forms.Control.Location%2A>.</span></span>

```vb
' Assume this code runs inside Form1.
Dim exitButton As New System.Windows.Forms.Button()
exitButton.Text = "Exit this form"
exitButton.Location.X = 140
' The preceding line is an ERROR because of no storage for Location.
```

<span data-ttu-id="46af4-110">L'ultima istruzione dell'esempio precedente ha esito negativo perché crea solo un'allocazione temporanea per la <xref:System.Drawing.Point> struttura restituita dalla <xref:System.Windows.Forms.Control.Location%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="46af4-110">The last statement of the preceding example fails because it creates only a temporary allocation for the <xref:System.Drawing.Point> structure returned by the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span> <span data-ttu-id="46af4-111">Una struttura è un tipo di valore e la struttura temporanea non viene mantenuta dopo l'esecuzione dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="46af4-111">A structure is a value type, and the temporary structure is not retained after the statement runs.</span></span> <span data-ttu-id="46af4-112">Il problema viene risolto dichiarando e utilizzando una variabile per <xref:System.Windows.Forms.Control.Location%2A> , che consente di creare un'allocazione più permanente per la <xref:System.Drawing.Point> struttura.</span><span class="sxs-lookup"><span data-stu-id="46af4-112">The problem is resolved by declaring and using a variable for <xref:System.Windows.Forms.Control.Location%2A>, which creates a more permanent allocation for the <xref:System.Drawing.Point> structure.</span></span> <span data-ttu-id="46af4-113">Nell'esempio seguente viene illustrato il codice in grado di sostituire l'ultima istruzione dell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="46af4-113">The following example shows code that can replace the last statement of the preceding example.</span></span>

```vb
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)
exitButton.Location = exitLocation
```

<span data-ttu-id="46af4-114">**ID errore:** BC30068</span><span class="sxs-lookup"><span data-stu-id="46af4-114">**Error ID:** BC30068</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="46af4-115">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="46af4-115">To correct this error</span></span>

- <span data-ttu-id="46af4-116">Se l'istruzione assegna un valore a un'espressione, sostituire l'espressione con una singola variabile scrivibile, una proprietà o un elemento di matrice.</span><span class="sxs-lookup"><span data-stu-id="46af4-116">If the statement assigns a value to an expression, replace the expression with a single writable variable, property, or array element.</span></span>

- <span data-ttu-id="46af4-117">Se l'istruzione consente l'accesso indiretto tramite un tipo di valore (in genere una struttura), creare una variabile che contenga il tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="46af4-117">If the statement makes indirect access through a value type (usually a structure), create a variable to hold the value type.</span></span>

- <span data-ttu-id="46af4-118">Assegnare la struttura appropriata (o un altro tipo di valore) alla variabile.</span><span class="sxs-lookup"><span data-stu-id="46af4-118">Assign the appropriate structure (or other value type) to the variable.</span></span>

- <span data-ttu-id="46af4-119">Utilizzare la variabile per accedere alla proprietà per assegnarle un valore.</span><span class="sxs-lookup"><span data-stu-id="46af4-119">Use the variable to access the property to assign it a value.</span></span>

## <a name="see-also"></a><span data-ttu-id="46af4-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46af4-120">See also</span></span>

- [<span data-ttu-id="46af4-121">Operatori ed espressioni</span><span class="sxs-lookup"><span data-stu-id="46af4-121">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="46af4-122">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="46af4-122">Statements</span></span>](../../programming-guide/language-features/statements.md)
- [<span data-ttu-id="46af4-123">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="46af4-123">Troubleshooting Procedures</span></span>](../../programming-guide/language-features/procedures/troubleshooting-procedures.md)
