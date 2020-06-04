---
title: Variabili oggetto
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
ms.openlocfilehash: a5e61f9308d3484dc228a7d09cc2fd30a2f41b35
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410335"
---
# <a name="object-variables-in-visual-basic"></a><span data-ttu-id="f4e3e-102">Variabili oggetto in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f4e3e-102">Object Variables in Visual Basic</span></span>

<span data-ttu-id="f4e3e-103">Oltre a archiviare direttamente i valori, una variabile può fare riferimento a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="f4e3e-103">In addition to storing values directly, a variable can refer to an object.</span></span> <span data-ttu-id="f4e3e-104">Si assegna un oggetto a una variabile per gli stessi motivi per cui si assegna un valore a una variabile:</span><span class="sxs-lookup"><span data-stu-id="f4e3e-104">You assign an object to a variable for the same reasons you assign any value to a variable:</span></span>

- <span data-ttu-id="f4e3e-105">Un nome di variabile è spesso più breve e più facile da ricordare rispetto al percorso completo dei metodi e delle proprietà necessari per accedere all'oggetto stesso.</span><span class="sxs-lookup"><span data-stu-id="f4e3e-105">A variable name is often shorter and easier to remember than the full path of methods and properties necessary to access the object itself.</span></span>

- <span data-ttu-id="f4e3e-106">L'uso di una variabile che fa riferimento a un oggetto è più efficiente rispetto all'accesso ripetuto ripetutamente all'oggetto tramite le proprietà o i metodi necessari.</span><span class="sxs-lookup"><span data-stu-id="f4e3e-106">Using a variable that refers to an object is more efficient than repeatedly accessing the object itself through the necessary methods or properties.</span></span>

- <span data-ttu-id="f4e3e-107">È possibile modificare una variabile in modo che faccia riferimento ad altri oggetti mentre il codice è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f4e3e-107">You can change a variable to refer to other objects while your code is running.</span></span>

## <a name="making-code-shorter"></a><span data-ttu-id="f4e3e-108">Creazione di codice più breve</span><span class="sxs-lookup"><span data-stu-id="f4e3e-108">Making Code Shorter</span></span>

<span data-ttu-id="f4e3e-109">È possibile utilizzare le variabili oggetto per abbreviare il codice che è necessario digitare.</span><span class="sxs-lookup"><span data-stu-id="f4e3e-109">You can use object variables to shorten the code you have to type.</span></span> <span data-ttu-id="f4e3e-110">Nell'esempio seguente viene usato il percorso completo dei metodi e delle proprietà per accedere a un <xref:System.Windows.Forms.Control> oggetto.</span><span class="sxs-lookup"><span data-stu-id="f4e3e-110">The following example uses the full path of methods and properties to access a <xref:System.Windows.Forms.Control> object.</span></span>

```vb
' Assume Me is a valid Form, or replace Me with a valid Form.
Me.ActiveForm.ActiveControl.Text = "Test"
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)
Me.ActiveForm.ActiveControl.Show()
```

<span data-ttu-id="f4e3e-111">È possibile abbreviare questo codice e velocizzare l'esecuzione, se si usa una variabile oggetto per il controllo.</span><span class="sxs-lookup"><span data-stu-id="f4e3e-111">You can shorten this code, and speed up execution, if you use an object variable for the control.</span></span> <span data-ttu-id="f4e3e-112">È necessario dichiarare la variabile oggetto con la classe specifica a cui si desidera assegnarla ( `Control` in questo caso).</span><span class="sxs-lookup"><span data-stu-id="f4e3e-112">You should declare the object variable with the specific class that you intend to assign to it (`Control` in this case).</span></span> <span data-ttu-id="f4e3e-113">Una volta assegnato un oggetto alla variabile, è possibile considerarlo esattamente come si tratta dell'oggetto a cui fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="f4e3e-113">Once you assign an object to the variable, you can treat it exactly the same as you treat the object to which it refers.</span></span> <span data-ttu-id="f4e3e-114">È possibile impostare o recuperare le proprietà dell'oggetto o utilizzare uno dei relativi metodi.</span><span class="sxs-lookup"><span data-stu-id="f4e3e-114">You can set or retrieve the properties of the object or use any of its methods.</span></span> <span data-ttu-id="f4e3e-115">Nell'esempio seguente viene usata una variabile oggetto per semplificare il codice nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="f4e3e-115">The following example uses an object variable to simplify the code in the preceding example.</span></span>

```vb
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl
ctrlActv.Text = "Test"
ctrlActv.Location = New Point(100, 100)
ctrlActv.Show()
```

## <a name="see-also"></a><span data-ttu-id="f4e3e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4e3e-116">See also</span></span>

- [<span data-ttu-id="f4e3e-117">Dichiarazione di variabile</span><span class="sxs-lookup"><span data-stu-id="f4e3e-117">Variable Declaration</span></span>](variable-declaration.md)
- [<span data-ttu-id="f4e3e-118">Procedura: velocizzare l'accesso a un oggetto con un percorso di qualificazione lungo</span><span class="sxs-lookup"><span data-stu-id="f4e3e-118">How to: Speed Up Access to an Object with a Long Qualification Path</span></span>](how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)
- [<span data-ttu-id="f4e3e-119">Dichiarazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="f4e3e-119">Object Variable Declaration</span></span>](object-variable-declaration.md)
- [<span data-ttu-id="f4e3e-120">Assegnazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="f4e3e-120">Object Variable Assignment</span></span>](object-variable-assignment.md)
- [<span data-ttu-id="f4e3e-121">Valori di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="f4e3e-121">Object Variable Values</span></span>](object-variable-values.md)
