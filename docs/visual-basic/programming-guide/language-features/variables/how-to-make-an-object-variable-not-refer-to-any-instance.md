---
title: 'Procedura: Impostare una variabile oggetto non fa riferimento a qualsiasi istanza (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: 820d4cb9d17bf467d257bfbba5f43f07228c0b4f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663565"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a><span data-ttu-id="3e2e1-102">Procedura: Impostare una variabile oggetto non fa riferimento a qualsiasi istanza (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3e2e1-102">How to: Make an Object Variable Not Refer to Any Instance (Visual Basic)</span></span>
<span data-ttu-id="3e2e1-103">È possibile annullare l'associazione di una variabile di oggetto da qualsiasi istanza dell'oggetto impostandolo su [Nothing](../../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="3e2e1-103">You can disassociate an object variable from any object instance by setting it to [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a><span data-ttu-id="3e2e1-104">Per annullare l'associazione di una variabile di oggetto da qualsiasi istanza dell'oggetto</span><span class="sxs-lookup"><span data-stu-id="3e2e1-104">To disassociate an object variable from any object instance</span></span>  
  
- <span data-ttu-id="3e2e1-105">Impostare la variabile `Nothing` in un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="3e2e1-105">Set the variable to `Nothing` in an assignment statement.</span></span>  
  
    ```  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a><span data-ttu-id="3e2e1-106">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="3e2e1-106">Robust Programming</span></span>  
 <span data-ttu-id="3e2e1-107">Se il codice tenta di accedere a un membro di una variabile oggetto che è stata impostata su `Nothing`, un <xref:System.NullReferenceException> si verifica.</span><span class="sxs-lookup"><span data-stu-id="3e2e1-107">If your code tries to access a member of an object variable that has been set to `Nothing`, a <xref:System.NullReferenceException> occurs.</span></span> <span data-ttu-id="3e2e1-108">Se si imposta una variabile oggetto `Nothing` frequentemente, o se è possibile la variabile non è inizializzata, è consigliabile racchiudere gli accessi ai membri in un `Try...Catch...Finally` blocco.</span><span class="sxs-lookup"><span data-stu-id="3e2e1-108">If you set an object variable to `Nothing` frequently, or if it is possible the variable is not initialized, it is a good idea to enclose member accesses in a `Try...Catch...Finally` block.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="3e2e1-109">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3e2e1-109">.NET Framework Security</span></span>  
 <span data-ttu-id="3e2e1-110">Se si usa una variabile oggetto per gli oggetti che contengono dati riservati o sensibili, è possibile impostare la variabile `Nothing` quando non si attivamente con uno di questi oggetti.</span><span class="sxs-lookup"><span data-stu-id="3e2e1-110">If you use an object variable for objects that contain confidential or sensitive data, you can set the variable to `Nothing` when you are not actively dealing with one of those objects.</span></span> <span data-ttu-id="3e2e1-111">In questo modo si riduce la probabilità di codice dannoso di ottenere l'accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="3e2e1-111">This reduces the chance of malicious code gaining access to the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e2e1-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e2e1-112">See also</span></span>

- <xref:System.NullReferenceException>
- [<span data-ttu-id="3e2e1-113">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="3e2e1-113">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="3e2e1-114">Assegnazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="3e2e1-114">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="3e2e1-115">Nothing</span><span class="sxs-lookup"><span data-stu-id="3e2e1-115">Nothing</span></span>](../../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="3e2e1-116">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="3e2e1-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
