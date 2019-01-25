---
title: Variabili oggetto in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
ms.openlocfilehash: 046119664fc0277a6a5305d0cf086b4438b13f9d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685464"
---
# <a name="object-variables-in-visual-basic"></a><span data-ttu-id="4d145-102">Variabili oggetto in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4d145-102">Object Variables in Visual Basic</span></span>
<span data-ttu-id="4d145-103">Oltre ad archiviare i valori direttamente, una variabile può fare riferimento a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="4d145-103">In addition to storing values directly, a variable can refer to an object.</span></span> <span data-ttu-id="4d145-104">Si assegna un oggetto a una variabile per gli stessi motivi che si assegna un valore a una variabile:</span><span class="sxs-lookup"><span data-stu-id="4d145-104">You assign an object to a variable for the same reasons you assign any value to a variable:</span></span>  
  
-   <span data-ttu-id="4d145-105">Un nome di variabile è spesso più breve e facile da ricordare rispetto al percorso completo di metodi e proprietà necessarie per accedere all'oggetto stesso.</span><span class="sxs-lookup"><span data-stu-id="4d145-105">A variable name is often shorter and easier to remember than the full path of methods and properties necessary to access the object itself.</span></span>  
  
-   <span data-ttu-id="4d145-106">Utilizzo di una variabile che fa riferimento a un oggetto è più efficiente ripetutamente l'accesso all'oggetto stesso tramite i metodi necessari o proprietà.</span><span class="sxs-lookup"><span data-stu-id="4d145-106">Using a variable that refers to an object is more efficient than repeatedly accessing the object itself through the necessary methods or properties.</span></span>  
  
-   <span data-ttu-id="4d145-107">È possibile modificare una variabile per fare riferimento ad altri oggetti durante l'esecuzione di codice.</span><span class="sxs-lookup"><span data-stu-id="4d145-107">You can change a variable to refer to other objects while your code is running.</span></span>  
  
## <a name="making-code-shorter"></a><span data-ttu-id="4d145-108">Abbreviazione del codice</span><span class="sxs-lookup"><span data-stu-id="4d145-108">Making Code Shorter</span></span>  
 <span data-ttu-id="4d145-109">È possibile usare le variabili oggetto per abbreviare il codice da digitare.</span><span class="sxs-lookup"><span data-stu-id="4d145-109">You can use object variables to shorten the code you have to type.</span></span> <span data-ttu-id="4d145-110">L'esempio seguente usa il percorso completo di proprietà e metodi per accedere a un <xref:System.Windows.Forms.Control> oggetto.</span><span class="sxs-lookup"><span data-stu-id="4d145-110">The following example uses the full path of methods and properties to access a <xref:System.Windows.Forms.Control> object.</span></span>  
  
```  
' Assume Me is a valid Form, or replace Me with a valid Form.  
Me.ActiveForm.ActiveControl.Text = "Test"  
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)  
Me.ActiveForm.ActiveControl.Show()  
```  
  
 <span data-ttu-id="4d145-111">È possibile abbreviare questo codice e aumentare la velocità di esecuzione, se si usa una variabile oggetto per il controllo.</span><span class="sxs-lookup"><span data-stu-id="4d145-111">You can shorten this code, and speed up execution, if you use an object variable for the control.</span></span> <span data-ttu-id="4d145-112">È necessario dichiarare la variabile oggetto con la classe specifica che si intende assegnare ad esso (`Control` in questo caso).</span><span class="sxs-lookup"><span data-stu-id="4d145-112">You should declare the object variable with the specific class that you intend to assign to it (`Control` in this case).</span></span> <span data-ttu-id="4d145-113">Una volta che si assegna un oggetto alla variabile, è possibile trattare l'esattamente come si considera l'oggetto a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="4d145-113">Once you assign an object to the variable, you can treat it exactly the same as you treat the object to which it refers.</span></span> <span data-ttu-id="4d145-114">È possibile impostare o recuperare le proprietà dell'oggetto o usare uno qualsiasi dei relativi metodi.</span><span class="sxs-lookup"><span data-stu-id="4d145-114">You can set or retrieve the properties of the object or use any of its methods.</span></span> <span data-ttu-id="4d145-115">Nell'esempio seguente usa una variabile oggetto per semplificare il codice nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="4d145-115">The following example uses an object variable to simplify the code in the preceding example.</span></span>  
  
```  
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl  
ctrlActv.Text = "Test"  
ctrlActv.Location = New Point(100, 100)  
ctrlActv.Show()  
```  
  
## <a name="see-also"></a><span data-ttu-id="4d145-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d145-116">See also</span></span>
- [<span data-ttu-id="4d145-117">Dichiarazione di variabile</span><span class="sxs-lookup"><span data-stu-id="4d145-117">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="4d145-118">Procedura: Velocizzare l'accesso a un oggetto con un percorso di qualificazione lungo</span><span class="sxs-lookup"><span data-stu-id="4d145-118">How to: Speed Up Access to an Object with a Long Qualification Path</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)
- [<span data-ttu-id="4d145-119">Dichiarazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="4d145-119">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="4d145-120">Assegnazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="4d145-120">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="4d145-121">Valori di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="4d145-121">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
