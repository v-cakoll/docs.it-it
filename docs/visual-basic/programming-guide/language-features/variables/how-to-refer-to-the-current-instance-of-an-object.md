---
title: "Procedura: Fare riferimento all'istanza corrente di un oggetto (Visual Basic)"
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: 6c216dbc59bcad7a9f24bb01f856c3d29c288dbb
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005662"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a><span data-ttu-id="aab63-102">Procedura: Fare riferimento all'istanza corrente di un oggetto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aab63-102">How to: Refer to the Current Instance of an Object (Visual Basic)</span></span>
<span data-ttu-id="aab63-103">L' *istanza corrente* di un oggetto è l'istanza di in cui è attualmente in esecuzione il codice.</span><span class="sxs-lookup"><span data-stu-id="aab63-103">The *current instance* of an object is the instance in which the code is currently executing.</span></span>  
  
 <span data-ttu-id="aab63-104">Usare la parola chiave `Me` per fare riferimento all'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="aab63-104">You use the `Me` keyword to refer to the current instance.</span></span>  
  
### <a name="to-refer-to-the-current-instance"></a><span data-ttu-id="aab63-105">Per fare riferimento all'istanza corrente</span><span class="sxs-lookup"><span data-stu-id="aab63-105">To refer to the current instance</span></span>  
  
- <span data-ttu-id="aab63-106">Usare la parola chiave `Me` dove normalmente si usa il nome di una variabile oggetto.</span><span class="sxs-lookup"><span data-stu-id="aab63-106">Use the `Me` keyword where you would normally use the name of an object variable.</span></span>  
  
    ```vb  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     <span data-ttu-id="aab63-107">Sebbene `Me` si comportano come una variabile oggetto, non è possibile dichiararla o assegnarvi alcun elemento.</span><span class="sxs-lookup"><span data-stu-id="aab63-107">Although `Me` behaves like an object variable, you cannot declare it or assign anything to it.</span></span> <span data-ttu-id="aab63-108">`Me` fa sempre riferimento all'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="aab63-108">`Me` always refers to the current instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aab63-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aab63-109">See also</span></span>

- [<span data-ttu-id="aab63-110">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="aab63-110">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="aab63-111">Assegnazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="aab63-111">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="aab63-112">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="aab63-112">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
