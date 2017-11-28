---
title: "&#39; &lt;parola chiave&gt;&#39; è valido solo all'interno di un metodo di istanza"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords: BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a61314c036cec0fd1412a9c844a610fbd1401add
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="39ltkeywordgt39-is-valid-only-within-an-instance-method"></a><span data-ttu-id="a40e3-102">&#39; &lt;parola chiave&gt;&#39; è valido solo all'interno di un metodo di istanza</span><span class="sxs-lookup"><span data-stu-id="a40e3-102">&#39;&lt;keyword&gt;&#39; is valid only within an instance method</span></span>
<span data-ttu-id="a40e3-103">Il `Me`, `MyClass`, e `MyBase` parole chiave fanno riferimento a istanze di classe specifico.</span><span class="sxs-lookup"><span data-stu-id="a40e3-103">The `Me`, `MyClass`, and `MyBase` keywords refer to specific class instances.</span></span> <span data-ttu-id="a40e3-104">Non possono essere utilizzati all'interno di un oggetto condiviso `Function` o `Sub` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="a40e3-104">You cannot use them inside a shared `Function` or `Sub` procedure.</span></span>  
  
 <span data-ttu-id="a40e3-105">**ID errore:** BC30043</span><span class="sxs-lookup"><span data-stu-id="a40e3-105">**Error ID:** BC30043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a40e3-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="a40e3-106">To correct this error</span></span>  
  
-   <span data-ttu-id="a40e3-107">Rimuovere la parola chiave dalla routine oppure rimuovere il `Shared` parola chiave dalla dichiarazione di routine.</span><span class="sxs-lookup"><span data-stu-id="a40e3-107">Remove the keyword from the procedure, or remove the `Shared` keyword from the procedure declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a40e3-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a40e3-108">See Also</span></span>  
 [<span data-ttu-id="a40e3-109">Assegnazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="a40e3-109">Object Variable Assignment</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [<span data-ttu-id="a40e3-110">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="a40e3-110">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [<span data-ttu-id="a40e3-111">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="a40e3-111">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
