---
title: "Procedura: Velocizzare l'accesso a un oggetto con un percorso di qualificazione lungo (Visual Basic)"
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
ms.openlocfilehash: b10876c22d2f6dd5832baa0d498db7c4205a3fcb
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816291"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a><span data-ttu-id="6d652-102">Procedura: Velocizzare l'accesso a un oggetto con un percorso di qualificazione lungo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6d652-102">How to: Speed Up Access to an Object with a Long Qualification Path (Visual Basic)</span></span>
<span data-ttu-id="6d652-103">Se si accede di frequente un oggetto che richiede un percorso di qualificazione dei diversi metodi e proprietà, è possibile velocizzare il codice non ripetendo il percorso di qualificazione.</span><span class="sxs-lookup"><span data-stu-id="6d652-103">If you frequently access an object that requires a qualification path of several methods and properties, you can speed up your code by not repeating the qualification path.</span></span>  
  
 <span data-ttu-id="6d652-104">Esistono due modi, è possibile evitare di ripetere il percorso di qualificazione.</span><span class="sxs-lookup"><span data-stu-id="6d652-104">There are two ways you can avoid repeating the qualification path.</span></span> <span data-ttu-id="6d652-105">È possibile assegnare l'oggetto a una variabile, oppure è possibile usarlo in un `With`... `End With` blocco.</span><span class="sxs-lookup"><span data-stu-id="6d652-105">You can assign the object to a variable, or you can use it in a `With`...`End With` block.</span></span>  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a><span data-ttu-id="6d652-106">Per velocizzare l'accesso tramite l'assegnazione a una variabile a un oggetto di qualificazione</span><span class="sxs-lookup"><span data-stu-id="6d652-106">To speed up access to a heavily qualified object by assigning it to a variable</span></span>  
  
1.  <span data-ttu-id="6d652-107">Dichiarare una variabile del tipo di oggetto cui si accede di frequente.</span><span class="sxs-lookup"><span data-stu-id="6d652-107">Declare a variable of the type of the object that you are accessing frequently.</span></span> <span data-ttu-id="6d652-108">Specificare il percorso di qualificazione nella parte di inizializzazione della dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="6d652-108">Specify the qualification path in the initialization part of the declaration.</span></span>  
  
    ```  
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl  
    ```  
  
2.  <span data-ttu-id="6d652-109">Usare la variabile per accedere ai membri dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="6d652-109">Use the variable to access the object's members.</span></span>  
  
    ```  
    ctrlActv.Text = "Test"  
    ctrlActv.Location = New Point(100, 100)  
    ctrlActv.Show()  
    ```  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a><span data-ttu-id="6d652-110">Per velocizzare l'accesso a un oggetto qualificazione usando una clausola With... Blocco End With</span><span class="sxs-lookup"><span data-stu-id="6d652-110">To speed up access to a heavily qualified object by using a With...End With block</span></span>  
  
1.  <span data-ttu-id="6d652-111">Inserire il percorso di qualificazione in un `With` istruzione.</span><span class="sxs-lookup"><span data-stu-id="6d652-111">Put the qualification path in a `With` statement.</span></span>  
  
    ```  
    With someForm.ActiveForm.ActiveControl  
    ```  
  
2.  <span data-ttu-id="6d652-112">Accedere ai membri dell'oggetto all'interno di `With` blocca, in precedenza il `End With` istruzione.</span><span class="sxs-lookup"><span data-stu-id="6d652-112">Access the object's members inside the `With` block, before the `End With` statement.</span></span>  
  
    ```  
        .Text = "Test"  
        .Location = New Point(100, 100)  
        .Show()  
    End With  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6d652-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d652-113">See also</span></span>

- [<span data-ttu-id="6d652-114">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="6d652-114">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="6d652-115">Istruzione With...End With</span><span class="sxs-lookup"><span data-stu-id="6d652-115">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
