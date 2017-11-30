---
title: 'Procedura: impostare una variabile oggetto in modo che non faccia riferimento ad alcuna istanza (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3b33aef06300bf35b7138ec5b40747532a77140a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a><span data-ttu-id="b41db-102">Procedura: impostare una variabile oggetto in modo che non faccia riferimento ad alcuna istanza (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b41db-102">How to: Make an Object Variable Not Refer to Any Instance (Visual Basic)</span></span>
<span data-ttu-id="b41db-103">È possibile annullare l'associazione di una variabile oggetto a qualsiasi istanza dell'oggetto impostandolo su [nulla](../../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="b41db-103">You can disassociate an object variable from any object instance by setting it to [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a><span data-ttu-id="b41db-104">Per annullare l'associazione di una variabile oggetto a qualsiasi istanza dell'oggetto</span><span class="sxs-lookup"><span data-stu-id="b41db-104">To disassociate an object variable from any object instance</span></span>  
  
-   <span data-ttu-id="b41db-105">Impostare la variabile `Nothing` in un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="b41db-105">Set the variable to `Nothing` in an assignment statement.</span></span>  
  
    ```  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a><span data-ttu-id="b41db-106">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="b41db-106">Robust Programming</span></span>  
 <span data-ttu-id="b41db-107">Se il codice tenta di accedere a un membro di una variabile oggetto che è stata impostata su `Nothing`, <xref:System.NullReferenceException> si verifica.</span><span class="sxs-lookup"><span data-stu-id="b41db-107">If your code tries to access a member of an object variable that has been set to `Nothing`, a <xref:System.NullReferenceException> occurs.</span></span> <span data-ttu-id="b41db-108">Se si imposta una variabile oggetto `Nothing` frequentemente o se è possibile che la variabile non viene inizializzata, è consigliabile racchiudere gli accessi ai membri in un `Try...Catch...Finally` blocco.</span><span class="sxs-lookup"><span data-stu-id="b41db-108">If you set an object variable to `Nothing` frequently, or if it is possible the variable is not initialized, it is a good idea to enclose member accesses in a `Try...Catch...Finally` block.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="b41db-109">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b41db-109">.NET Framework Security</span></span>  
 <span data-ttu-id="b41db-110">Se si utilizza una variabile oggetto per gli oggetti che contengono dati riservati o sensibili, è possibile impostare la variabile `Nothing` quando non si attivamente con uno di questi oggetti.</span><span class="sxs-lookup"><span data-stu-id="b41db-110">If you use an object variable for objects that contain confidential or sensitive data, you can set the variable to `Nothing` when you are not actively dealing with one of those objects.</span></span> <span data-ttu-id="b41db-111">Ciò riduce la possibilità di codice dannoso di ottenere l'accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="b41db-111">This reduces the chance of malicious code gaining access to the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b41db-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b41db-112">See Also</span></span>  
 <xref:System.NullReferenceException>  
 [<span data-ttu-id="b41db-113">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="b41db-113">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="b41db-114">Assegnazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="b41db-114">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [<span data-ttu-id="b41db-115">Nothing</span><span class="sxs-lookup"><span data-stu-id="b41db-115">Nothing</span></span>](../../../../visual-basic/language-reference/nothing.md)  
 [<span data-ttu-id="b41db-116">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="b41db-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="b41db-117">Risoluzione dei problemi relativi ad eccezioni: System.NullReferenceException</span><span class="sxs-lookup"><span data-stu-id="b41db-117">Troubleshooting Exceptions: System.NullReferenceException</span></span>](http://msdn.microsoft.com/library/4822b0b4-8105-43fb-887a-3cc51ff02899)
