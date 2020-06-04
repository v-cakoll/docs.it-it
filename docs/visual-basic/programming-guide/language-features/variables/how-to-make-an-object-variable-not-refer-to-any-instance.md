---
title: 'Procedura: impostare una variabile oggetto in modo che non faccia riferimento ad alcuna istanza'
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: cce2e59cb76652937868a731ad308872d1aba2f3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410451"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a><span data-ttu-id="190b9-102">Procedura: impostare una variabile oggetto in modo che non faccia riferimento ad alcuna istanza (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="190b9-102">How to: Make an Object Variable Not Refer to Any Instance (Visual Basic)</span></span>
<span data-ttu-id="190b9-103">È possibile annullare l'associazione di una variabile oggetto da qualsiasi istanza di oggetto impostandola su [Nothing](../../../language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="190b9-103">You can disassociate an object variable from any object instance by setting it to [Nothing](../../../language-reference/nothing.md).</span></span>  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a><span data-ttu-id="190b9-104">Per annullare l'associazione di una variabile oggetto da qualsiasi istanza di oggetto</span><span class="sxs-lookup"><span data-stu-id="190b9-104">To disassociate an object variable from any object instance</span></span>  
  
- <span data-ttu-id="190b9-105">Impostare la variabile su `Nothing` in un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="190b9-105">Set the variable to `Nothing` in an assignment statement.</span></span>  
  
    ```vb  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a><span data-ttu-id="190b9-106">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="190b9-106">Robust Programming</span></span>  
 <span data-ttu-id="190b9-107">Se il codice tenta di accedere a un membro di una variabile oggetto impostata su `Nothing` , <xref:System.NullReferenceException> si verifica un.</span><span class="sxs-lookup"><span data-stu-id="190b9-107">If your code tries to access a member of an object variable that has been set to `Nothing`, a <xref:System.NullReferenceException> occurs.</span></span> <span data-ttu-id="190b9-108">Se si imposta una variabile oggetto su di `Nothing` frequente o se è possibile che la variabile non sia inizializzata, è consigliabile racchiudere gli accessi dei membri in un `Try...Catch...Finally` blocco.</span><span class="sxs-lookup"><span data-stu-id="190b9-108">If you set an object variable to `Nothing` frequently, or if it is possible the variable is not initialized, it is a good idea to enclose member accesses in a `Try...Catch...Finally` block.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="190b9-109">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="190b9-109">.NET Framework Security</span></span>  
 <span data-ttu-id="190b9-110">Se si usa una variabile oggetto per gli oggetti che contengono dati riservati o sensibili, è possibile impostare la variabile su `Nothing` quando non si sta lavorando attivamente a uno di questi oggetti.</span><span class="sxs-lookup"><span data-stu-id="190b9-110">If you use an object variable for objects that contain confidential or sensitive data, you can set the variable to `Nothing` when you are not actively dealing with one of those objects.</span></span> <span data-ttu-id="190b9-111">In questo modo si riduce la probabilità che il codice dannoso ottenga l'accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="190b9-111">This reduces the chance of malicious code gaining access to the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="190b9-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="190b9-112">See also</span></span>

- <xref:System.NullReferenceException>
- [<span data-ttu-id="190b9-113">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="190b9-113">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="190b9-114">Assegnazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="190b9-114">Object Variable Assignment</span></span>](object-variable-assignment.md)
- [<span data-ttu-id="190b9-115">Nothing</span><span class="sxs-lookup"><span data-stu-id="190b9-115">Nothing</span></span>](../../../language-reference/nothing.md)
- [<span data-ttu-id="190b9-116">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="190b9-116">Try...Catch...Finally Statement</span></span>](../../../language-reference/statements/try-catch-finally-statement.md)
