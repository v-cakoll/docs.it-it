---
title: Variabili oggetto in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
ms.openlocfilehash: 8383261c1806732c4c8abea9834000f003a848a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649113"
---
# <a name="object-variables-in-visual-basic"></a><span data-ttu-id="618f2-102">Variabili oggetto in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="618f2-102">Object Variables in Visual Basic</span></span>
<span data-ttu-id="618f2-103">Oltre ad archiviare i valori direttamente, una variabile può fare riferimento a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="618f2-103">In addition to storing values directly, a variable can refer to an object.</span></span> <span data-ttu-id="618f2-104">Si assegna un oggetto a una variabile per gli stessi motivi che si assegna un valore a una variabile:</span><span class="sxs-lookup"><span data-stu-id="618f2-104">You assign an object to a variable for the same reasons you assign any value to a variable:</span></span>  
  
-   <span data-ttu-id="618f2-105">Un nome di variabile è spesso più brevi e facili da ricordare rispetto al percorso completo di metodi e proprietà necessarie per accedere all'oggetto stesso.</span><span class="sxs-lookup"><span data-stu-id="618f2-105">A variable name is often shorter and easier to remember than the full path of methods and properties necessary to access the object itself.</span></span>  
  
-   <span data-ttu-id="618f2-106">Utilizzo di una variabile che fa riferimento a un oggetto è più efficiente dell'accesso più volte l'oggetto stesso tramite i metodi necessari o proprietà.</span><span class="sxs-lookup"><span data-stu-id="618f2-106">Using a variable that refers to an object is more efficient than repeatedly accessing the object itself through the necessary methods or properties.</span></span>  
  
-   <span data-ttu-id="618f2-107">È possibile modificare una variabile per fare riferimento ad altri oggetti durante l'esecuzione di codice.</span><span class="sxs-lookup"><span data-stu-id="618f2-107">You can change a variable to refer to other objects while your code is running.</span></span>  
  
## <a name="making-code-shorter"></a><span data-ttu-id="618f2-108">Abbreviazione del codice</span><span class="sxs-lookup"><span data-stu-id="618f2-108">Making Code Shorter</span></span>  
 <span data-ttu-id="618f2-109">È possibile utilizzare variabili oggetto per abbreviare il codice da digitare.</span><span class="sxs-lookup"><span data-stu-id="618f2-109">You can use object variables to shorten the code you have to type.</span></span> <span data-ttu-id="618f2-110">Nell'esempio seguente viene utilizzato il percorso completo di metodi e proprietà per accedere a un <xref:System.Windows.Forms.Control> oggetto.</span><span class="sxs-lookup"><span data-stu-id="618f2-110">The following example uses the full path of methods and properties to access a <xref:System.Windows.Forms.Control> object.</span></span>  
  
```  
' Assume Me is a valid Form, or replace Me with a valid Form.  
Me.ActiveForm.ActiveControl.Text = "Test"  
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)  
Me.ActiveForm.ActiveControl.Show()  
```  
  
 <span data-ttu-id="618f2-111">È possibile abbreviare il codice e velocizzare l'esecuzione, se si utilizza una variabile oggetto per il controllo.</span><span class="sxs-lookup"><span data-stu-id="618f2-111">You can shorten this code, and speed up execution, if you use an object variable for the control.</span></span> <span data-ttu-id="618f2-112">È necessario dichiarare la variabile oggetto con la classe specifica che si desidera assegnare a esso (`Control` in questo caso).</span><span class="sxs-lookup"><span data-stu-id="618f2-112">You should declare the object variable with the specific class that you intend to assign to it (`Control` in this case).</span></span> <span data-ttu-id="618f2-113">Quando si assegna un oggetto alla variabile, è possibile considerarlo esattamente lo stesso usato per l'oggetto a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="618f2-113">Once you assign an object to the variable, you can treat it exactly the same as you treat the object to which it refers.</span></span> <span data-ttu-id="618f2-114">È possibile impostare o recuperare le proprietà dell'oggetto o utilizzare uno qualsiasi dei relativi metodi.</span><span class="sxs-lookup"><span data-stu-id="618f2-114">You can set or retrieve the properties of the object or use any of its methods.</span></span> <span data-ttu-id="618f2-115">Nell'esempio seguente viene utilizzata una variabile oggetto per semplificare il codice nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="618f2-115">The following example uses an object variable to simplify the code in the preceding example.</span></span>  
  
```  
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl  
ctrlActv.Text = "Test"  
ctrlActv.Location = New Point(100, 100)  
ctrlActv.Show()  
```  
  
## <a name="see-also"></a><span data-ttu-id="618f2-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="618f2-116">See Also</span></span>  
 [<span data-ttu-id="618f2-117">Dichiarazione di variabile</span><span class="sxs-lookup"><span data-stu-id="618f2-117">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="618f2-118">Procedura: Velocizzare l'accesso a un oggetto con un percorso di qualificazione lungo</span><span class="sxs-lookup"><span data-stu-id="618f2-118">How to: Speed Up Access to an Object with a Long Qualification Path</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)  
 [<span data-ttu-id="618f2-119">Dichiarazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="618f2-119">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [<span data-ttu-id="618f2-120">Assegnazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="618f2-120">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [<span data-ttu-id="618f2-121">Valori di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="618f2-121">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
