---
title: "'<keyword>' è valido solo all'interno di un metodo di istanza"
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: 537689405ea30bdd7c075320eba58a8723a93cdb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397402"
---
# <a name="keyword-is-valid-only-within-an-instance-method"></a><span data-ttu-id="1acf3-102">'\<keyword>' è valido solo all'interno di un metodo di istanza</span><span class="sxs-lookup"><span data-stu-id="1acf3-102">'\<keyword>' is valid only within an instance method</span></span>
<span data-ttu-id="1acf3-103">Le `Me` `MyClass` `MyBase` parole chiave, e si riferiscono a specifiche istanze di classe.</span><span class="sxs-lookup"><span data-stu-id="1acf3-103">The `Me`, `MyClass`, and `MyBase` keywords refer to specific class instances.</span></span> <span data-ttu-id="1acf3-104">Non è possibile usarli all'interno di una `Function` routine o condivisa `Sub` .</span><span class="sxs-lookup"><span data-stu-id="1acf3-104">You cannot use them inside a shared `Function` or `Sub` procedure.</span></span>  
  
 <span data-ttu-id="1acf3-105">**ID errore:** BC30043</span><span class="sxs-lookup"><span data-stu-id="1acf3-105">**Error ID:** BC30043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1acf3-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="1acf3-106">To correct this error</span></span>  
  
- <span data-ttu-id="1acf3-107">Rimuovere la parola chiave dalla routine oppure rimuovere la `Shared` parola chiave dalla dichiarazione di routine.</span><span class="sxs-lookup"><span data-stu-id="1acf3-107">Remove the keyword from the procedure, or remove the `Shared` keyword from the procedure declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1acf3-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1acf3-108">See also</span></span>

- [<span data-ttu-id="1acf3-109">Assegnazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="1acf3-109">Object Variable Assignment</span></span>](../../programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="1acf3-110">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="1acf3-110">Me, My, MyBase, and MyClass</span></span>](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="1acf3-111">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="1acf3-111">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
