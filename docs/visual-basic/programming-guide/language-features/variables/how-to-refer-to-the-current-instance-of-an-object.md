---
title: "Procedura: fare riferimento all'istanza corrente di un oggetto (Visual Basic)"
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: c1b79f1b6a9768941d6fe966c5b5886ea742f808
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648359"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a><span data-ttu-id="bc02a-102">Procedura: fare riferimento all'istanza corrente di un oggetto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc02a-102">How to: Refer to the Current Instance of an Object (Visual Basic)</span></span>
<span data-ttu-id="bc02a-103">Il *istanza corrente* di un oggetto è l'istanza in cui il codice attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="bc02a-103">The *current instance* of an object is the instance in which the code is currently executing.</span></span>  
  
 <span data-ttu-id="bc02a-104">Utilizzare il `Me` (parola chiave) per fare riferimento all'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="bc02a-104">You use the `Me` keyword to refer to the current instance.</span></span>  
  
### <a name="to-refer-to-the-current-instance"></a><span data-ttu-id="bc02a-105">Per fare riferimento all'istanza corrente</span><span class="sxs-lookup"><span data-stu-id="bc02a-105">To refer to the current instance</span></span>  
  
-   <span data-ttu-id="bc02a-106">Utilizzare il `Me` (parola chiave) in cui normalmente si utilizzerebbe il nome di una variabile oggetto.</span><span class="sxs-lookup"><span data-stu-id="bc02a-106">Use the `Me` keyword where you would normally use the name of an object variable.</span></span>  
  
    ```  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     <span data-ttu-id="bc02a-107">Sebbene `Me` si comporta come un oggetto variabile, non è possibile dichiararla o assegnarvi alcun valore.</span><span class="sxs-lookup"><span data-stu-id="bc02a-107">Although `Me` behaves like an object variable, you cannot declare it or assign anything to it.</span></span> <span data-ttu-id="bc02a-108">`Me` fa sempre riferimento all'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="bc02a-108">`Me` always refers to the current instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc02a-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc02a-109">See Also</span></span>  
 [<span data-ttu-id="bc02a-110">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="bc02a-110">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="bc02a-111">Assegnazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="bc02a-111">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [<span data-ttu-id="bc02a-112">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="bc02a-112">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
