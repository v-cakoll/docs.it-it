---
title: "'<keyword>' è valido solo all'interno di un metodo di istanza"
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: af3bc95e2db88577c7c53e4b58fb60aed8a83453
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267644"
---
# <a name="keyword-is-valid-only-within-an-instance-method"></a><span data-ttu-id="01ea7-102">'\<parola chiave >' è valido solo all'interno di un metodo di istanza</span><span class="sxs-lookup"><span data-stu-id="01ea7-102">'\<keyword>' is valid only within an instance method</span></span>
<span data-ttu-id="01ea7-103">Il `Me`, `MyClass`, e `MyBase` parole chiave fanno riferimento alle istanze di classe specifica.</span><span class="sxs-lookup"><span data-stu-id="01ea7-103">The `Me`, `MyClass`, and `MyBase` keywords refer to specific class instances.</span></span> <span data-ttu-id="01ea7-104">È possibile utilizzarle all'interno di un oggetto condiviso `Function` o `Sub` procedure.</span><span class="sxs-lookup"><span data-stu-id="01ea7-104">You cannot use them inside a shared `Function` or `Sub` procedure.</span></span>  
  
 <span data-ttu-id="01ea7-105">**ID errore:** BC30043</span><span class="sxs-lookup"><span data-stu-id="01ea7-105">**Error ID:** BC30043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="01ea7-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="01ea7-106">To correct this error</span></span>  
  
-   <span data-ttu-id="01ea7-107">Rimuovere la parola chiave dalla routine oppure rimuovere il `Shared` parola chiave dalla dichiarazione di routine.</span><span class="sxs-lookup"><span data-stu-id="01ea7-107">Remove the keyword from the procedure, or remove the `Shared` keyword from the procedure declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01ea7-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01ea7-108">See also</span></span>
- [<span data-ttu-id="01ea7-109">Assegnazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="01ea7-109">Object Variable Assignment</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="01ea7-110">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="01ea7-110">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="01ea7-111">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="01ea7-111">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
