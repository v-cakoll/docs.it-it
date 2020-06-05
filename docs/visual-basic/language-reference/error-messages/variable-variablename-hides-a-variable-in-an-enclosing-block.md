---
title: La variabile '<variablename>' nasconde una variabile in un blocco di inclusione
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 474a920c9cfdfba7a8157320d9c88b8677958425
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406521"
---
# <a name="variable-variablename-hides-a-variable-in-an-enclosing-block"></a><span data-ttu-id="a5d48-102">La variabile '\<variablename>' nasconde una variabile in un blocco di inclusione</span><span class="sxs-lookup"><span data-stu-id="a5d48-102">Variable '\<variablename>' hides a variable in an enclosing block</span></span>
<span data-ttu-id="a5d48-103">Una variabile racchiusa in un blocco ha lo stesso nome di un'altra variabile locale.</span><span class="sxs-lookup"><span data-stu-id="a5d48-103">A variable enclosed in a block has the same name as another local variable.</span></span>  
  
 <span data-ttu-id="a5d48-104">**ID errore:** BC30616</span><span class="sxs-lookup"><span data-stu-id="a5d48-104">**Error ID:** BC30616</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a5d48-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="a5d48-105">To correct this error</span></span>  
  
- <span data-ttu-id="a5d48-106">Rinominare la variabile nel blocco racchiuso in modo che non corrisponda ad altre variabili locali.</span><span class="sxs-lookup"><span data-stu-id="a5d48-106">Rename the variable in the enclosed block so that it is not the same as any other local variables.</span></span> <span data-ttu-id="a5d48-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a5d48-107">For example:</span></span>  
  
    ```vb  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
- <span data-ttu-id="a5d48-108">Una cause comune di questo errore è l'uso di `Catch e As Exception` all'interno di un gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="a5d48-108">A common cause for this error is the use of `Catch e As Exception` inside an event handler.</span></span> <span data-ttu-id="a5d48-109">In tal caso, denominare la `Catch` variabile Block `ex` anziché `e` .</span><span class="sxs-lookup"><span data-stu-id="a5d48-109">If this is the case, name the `Catch` block variable `ex` rather than `e`.</span></span>  
  
- <span data-ttu-id="a5d48-110">Un'altra fonte comune di questo errore è un tentativo di accedere a una variabile locale dichiarata all'interno di un `Try` blocco in un `Catch` blocco separato.</span><span class="sxs-lookup"><span data-stu-id="a5d48-110">Another common source of this error is an attempt to access a local variable declared within a `Try` block in a separate `Catch` block.</span></span> <span data-ttu-id="a5d48-111">Per risolvere il problema, dichiarare la variabile all'esterno della `Try...Catch...Finally` struttura.</span><span class="sxs-lookup"><span data-stu-id="a5d48-111">To correct this, declare the variable outside the `Try...Catch...Finally` structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5d48-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5d48-112">See also</span></span>

- [<span data-ttu-id="a5d48-113">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="a5d48-113">Try...Catch...Finally Statement</span></span>](../statements/try-catch-finally-statement.md)
- [<span data-ttu-id="a5d48-114">Dichiarazione di variabile</span><span class="sxs-lookup"><span data-stu-id="a5d48-114">Variable Declaration</span></span>](../../programming-guide/language-features/variables/variable-declaration.md)
