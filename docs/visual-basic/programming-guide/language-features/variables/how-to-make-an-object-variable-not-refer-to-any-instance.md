---
title: 'Procedura: Fare in modo che una variabile oggetto non faccia riferimento ad alcuna istanza (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: e647f2f891b06aa1767faac49b01df98ea31ec1c
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004911"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a><span data-ttu-id="e613b-102">Procedura: Fare in modo che una variabile oggetto non faccia riferimento ad alcuna istanza (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e613b-102">How to: Make an Object Variable Not Refer to Any Instance (Visual Basic)</span></span>
<span data-ttu-id="e613b-103">È possibile annullare l'associazione di una variabile oggetto da qualsiasi istanza di oggetto impostandola su [Nothing](../../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="e613b-103">You can disassociate an object variable from any object instance by setting it to [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a><span data-ttu-id="e613b-104">Per annullare l'associazione di una variabile oggetto da qualsiasi istanza di oggetto</span><span class="sxs-lookup"><span data-stu-id="e613b-104">To disassociate an object variable from any object instance</span></span>  
  
- <span data-ttu-id="e613b-105">Impostare la variabile su `Nothing` in un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="e613b-105">Set the variable to `Nothing` in an assignment statement.</span></span>  
  
    ```vb  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a><span data-ttu-id="e613b-106">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="e613b-106">Robust Programming</span></span>  
 <span data-ttu-id="e613b-107">Se il codice tenta di accedere a un membro di una variabile oggetto impostata su `Nothing`, viene generato un <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="e613b-107">If your code tries to access a member of an object variable that has been set to `Nothing`, a <xref:System.NullReferenceException> occurs.</span></span> <span data-ttu-id="e613b-108">Se si imposta una variabile oggetto su `Nothing` di frequente o se è possibile che la variabile non sia inizializzata, è consigliabile racchiudere gli accessi dei membri in un blocco `Try...Catch...Finally`.</span><span class="sxs-lookup"><span data-stu-id="e613b-108">If you set an object variable to `Nothing` frequently, or if it is possible the variable is not initialized, it is a good idea to enclose member accesses in a `Try...Catch...Finally` block.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="e613b-109">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e613b-109">.NET Framework Security</span></span>  
 <span data-ttu-id="e613b-110">Se si usa una variabile oggetto per gli oggetti che contengono dati riservati o sensibili, è possibile impostare la variabile su `Nothing` quando non si occupa attivamente di uno di questi oggetti.</span><span class="sxs-lookup"><span data-stu-id="e613b-110">If you use an object variable for objects that contain confidential or sensitive data, you can set the variable to `Nothing` when you are not actively dealing with one of those objects.</span></span> <span data-ttu-id="e613b-111">In questo modo si riduce la probabilità che il codice dannoso ottenga l'accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="e613b-111">This reduces the chance of malicious code gaining access to the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e613b-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e613b-112">See also</span></span>

- <xref:System.NullReferenceException>
- [<span data-ttu-id="e613b-113">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="e613b-113">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="e613b-114">Assegnazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="e613b-114">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="e613b-115">Nothing</span><span class="sxs-lookup"><span data-stu-id="e613b-115">Nothing</span></span>](../../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="e613b-116">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="e613b-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
