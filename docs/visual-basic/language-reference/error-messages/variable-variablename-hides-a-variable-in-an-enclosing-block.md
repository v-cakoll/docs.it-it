---
title: Variabile &#39; &lt;variablename&gt;&#39; nasconde una variabile in un blocco di inclusione
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords: BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2af570cd002b4be4e15a7c03b0ffc2ff84ba3982
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="variable-39ltvariablenamegt39-hides-a-variable-in-an-enclosing-block"></a><span data-ttu-id="bdade-102">Variabile &#39; &lt;variablename&gt;&#39; nasconde una variabile in un blocco di inclusione</span><span class="sxs-lookup"><span data-stu-id="bdade-102">Variable &#39;&lt;variablename&gt;&#39; hides a variable in an enclosing block</span></span>
<span data-ttu-id="bdade-103">Una variabile è incluso in un blocco ha lo stesso nome di un'altra variabile locale.</span><span class="sxs-lookup"><span data-stu-id="bdade-103">A variable enclosed in a block has the same name as another local variable.</span></span>  
  
 <span data-ttu-id="bdade-104">**ID errore:** BC30616</span><span class="sxs-lookup"><span data-stu-id="bdade-104">**Error ID:** BC30616</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bdade-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="bdade-105">To correct this error</span></span>  
  
-   <span data-ttu-id="bdade-106">Rinominare la variabile nel blocco in modo che non sia lo stesso come qualsiasi altra variabile locale.</span><span class="sxs-lookup"><span data-stu-id="bdade-106">Rename the variable in the enclosed block so that it is not the same as any other local variables.</span></span> <span data-ttu-id="bdade-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bdade-107">For example:</span></span>  
  
    ```  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
-   <span data-ttu-id="bdade-108">Una causa comune di questo errore è l'utilizzo di `Catch e As Exception` all'interno di un gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="bdade-108">A common cause for this error is the use of `Catch e As Exception` inside an event handler.</span></span> <span data-ttu-id="bdade-109">In questo caso, assegnare un nome di `Catch` variabile del blocco `ex` anziché `e`.</span><span class="sxs-lookup"><span data-stu-id="bdade-109">If this is the case, name the `Catch` block variable `ex` rather than `e`.</span></span>  
  
-   <span data-ttu-id="bdade-110">Un'altra causa comune di questo errore viene eseguito un tentativo di accedere a una variabile locale dichiarata all'interno di un `Try` blocco in un apposito `Catch` blocco.</span><span class="sxs-lookup"><span data-stu-id="bdade-110">Another common source of this error is an attempt to access a local variable declared within a `Try` block in a separate `Catch` block.</span></span> <span data-ttu-id="bdade-111">Per risolvere il problema, dichiarare la variabile all'esterno di `Try...Catch...Finally` struttura.</span><span class="sxs-lookup"><span data-stu-id="bdade-111">To correct this, declare the variable outside the `Try...Catch...Finally` structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdade-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bdade-112">See Also</span></span>  
 [<span data-ttu-id="bdade-113">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="bdade-113">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="bdade-114">Dichiarazione di variabile</span><span class="sxs-lookup"><span data-stu-id="bdade-114">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
