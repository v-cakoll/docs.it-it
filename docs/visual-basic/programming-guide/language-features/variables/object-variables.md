---
title: Variabili oggetto in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 44689d649a381618e5d6c934deb2b7b9bea463ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="object-variables-in-visual-basic"></a><span data-ttu-id="2514e-102">Variabili oggetto in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2514e-102">Object Variables in Visual Basic</span></span>
<span data-ttu-id="2514e-103">Oltre ad archiviare i valori direttamente, una variabile può fare riferimento a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="2514e-103">In addition to storing values directly, a variable can refer to an object.</span></span> <span data-ttu-id="2514e-104">Si assegna un oggetto a una variabile per gli stessi motivi che si assegna un valore a una variabile:</span><span class="sxs-lookup"><span data-stu-id="2514e-104">You assign an object to a variable for the same reasons you assign any value to a variable:</span></span>  
  
-   <span data-ttu-id="2514e-105">Un nome di variabile è spesso più brevi e facili da ricordare rispetto al percorso completo di metodi e proprietà necessarie per accedere all'oggetto stesso.</span><span class="sxs-lookup"><span data-stu-id="2514e-105">A variable name is often shorter and easier to remember than the full path of methods and properties necessary to access the object itself.</span></span>  
  
-   <span data-ttu-id="2514e-106">Utilizzo di una variabile che fa riferimento a un oggetto è più efficiente dell'accesso più volte l'oggetto stesso tramite i metodi necessari o proprietà.</span><span class="sxs-lookup"><span data-stu-id="2514e-106">Using a variable that refers to an object is more efficient than repeatedly accessing the object itself through the necessary methods or properties.</span></span>  
  
-   <span data-ttu-id="2514e-107">È possibile modificare una variabile per fare riferimento ad altri oggetti durante l'esecuzione di codice.</span><span class="sxs-lookup"><span data-stu-id="2514e-107">You can change a variable to refer to other objects while your code is running.</span></span>  
  
## <a name="making-code-shorter"></a><span data-ttu-id="2514e-108">Abbreviazione del codice</span><span class="sxs-lookup"><span data-stu-id="2514e-108">Making Code Shorter</span></span>  
 <span data-ttu-id="2514e-109">È possibile utilizzare variabili oggetto per abbreviare il codice da digitare.</span><span class="sxs-lookup"><span data-stu-id="2514e-109">You can use object variables to shorten the code you have to type.</span></span> <span data-ttu-id="2514e-110">Nell'esempio seguente viene utilizzato il percorso completo di metodi e proprietà per accedere a un <xref:System.Windows.Forms.Control> oggetto.</span><span class="sxs-lookup"><span data-stu-id="2514e-110">The following example uses the full path of methods and properties to access a <xref:System.Windows.Forms.Control> object.</span></span>  
  
```  
' Assume Me is a valid Form, or replace Me with a valid Form.  
Me.ActiveForm.ActiveControl.Text = "Test"  
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)  
Me.ActiveForm.ActiveControl.Show()  
```  
  
 <span data-ttu-id="2514e-111">È possibile abbreviare il codice e velocizzare l'esecuzione, se si utilizza una variabile oggetto per il controllo.</span><span class="sxs-lookup"><span data-stu-id="2514e-111">You can shorten this code, and speed up execution, if you use an object variable for the control.</span></span> <span data-ttu-id="2514e-112">È necessario dichiarare la variabile oggetto con la classe specifica che si desidera assegnare a esso (`Control` in questo caso).</span><span class="sxs-lookup"><span data-stu-id="2514e-112">You should declare the object variable with the specific class that you intend to assign to it (`Control` in this case).</span></span> <span data-ttu-id="2514e-113">Quando si assegna un oggetto alla variabile, è possibile considerarlo esattamente lo stesso usato per l'oggetto a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="2514e-113">Once you assign an object to the variable, you can treat it exactly the same as you treat the object to which it refers.</span></span> <span data-ttu-id="2514e-114">È possibile impostare o recuperare le proprietà dell'oggetto o utilizzare uno qualsiasi dei relativi metodi.</span><span class="sxs-lookup"><span data-stu-id="2514e-114">You can set or retrieve the properties of the object or use any of its methods.</span></span> <span data-ttu-id="2514e-115">Nell'esempio seguente viene utilizzata una variabile oggetto per semplificare il codice nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="2514e-115">The following example uses an object variable to simplify the code in the preceding example.</span></span>  
  
```  
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl  
ctrlActv.Text = "Test"  
ctrlActv.Location = New Point(100, 100)  
ctrlActv.Show()  
```  
  
## <a name="see-also"></a><span data-ttu-id="2514e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2514e-116">See Also</span></span>  
 [<span data-ttu-id="2514e-117">Dichiarazione di variabile</span><span class="sxs-lookup"><span data-stu-id="2514e-117">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="2514e-118">Procedura: Velocizzare l'accesso a un oggetto con un percorso di qualificazione lungo</span><span class="sxs-lookup"><span data-stu-id="2514e-118">How to: Speed Up Access to an Object with a Long Qualification Path</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)  
 [<span data-ttu-id="2514e-119">Dichiarazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="2514e-119">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [<span data-ttu-id="2514e-120">Assegnazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="2514e-120">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [<span data-ttu-id="2514e-121">Valori di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="2514e-121">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
