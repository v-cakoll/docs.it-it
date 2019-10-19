---
title: 'Procedura: eliminare una risorsa di sistema (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Using statement [Visual Basic], disposing of system resources
- Visual Basic code, control flow
- system resources, disposing of
- resources [Visual Basic], disposing of system
- system resources
- Using statement [Visual Basic], Using...End Using
- Using block
ms.assetid: 8be2b239-8090-419b-8e7e-bcaa75b0ecc8
ms.openlocfilehash: c780ee1a174ad044593960bc30a3ee2e1f929390
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583138"
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a><span data-ttu-id="c4e58-102">Procedura: eliminare una risorsa di sistema (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4e58-102">How to: Dispose of a System Resource (Visual Basic)</span></span>
<span data-ttu-id="c4e58-103">È possibile usare un blocco di `Using` per garantire che il sistema elimini una risorsa quando il codice esce dal blocco.</span><span class="sxs-lookup"><span data-stu-id="c4e58-103">You can use a `Using` block to guarantee that the system disposes of a resource when your code exits the block.</span></span> <span data-ttu-id="c4e58-104">Questa opzione è utile se si usa una risorsa di sistema che usa una quantità elevata di memoria o che anche altri componenti desiderano usare.</span><span class="sxs-lookup"><span data-stu-id="c4e58-104">This is useful if you are using a system resource that consumes a large amount of memory, or that other components also want to use.</span></span>  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a><span data-ttu-id="c4e58-105">Per eliminare una connessione al database al termine del codice</span><span class="sxs-lookup"><span data-stu-id="c4e58-105">To dispose of a database connection when your code is finished with it</span></span>  
  
1. <span data-ttu-id="c4e58-106">Assicurarsi di includere l' [istruzione Imports appropriata (tipo e spazio dei nomi .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) per la connessione al database all'inizio del file di origine (in questo caso, <xref:System.Data.SqlClient>).</span><span class="sxs-lookup"><span data-stu-id="c4e58-106">Make sure you include the appropriate [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) for the database connection at the beginning of your source file (in this case, <xref:System.Data.SqlClient>).</span></span>  
  
2. <span data-ttu-id="c4e58-107">Creare un blocco di `Using` con le istruzioni `Using` e `End Using`.</span><span class="sxs-lookup"><span data-stu-id="c4e58-107">Create a `Using` block with the `Using` and `End Using` statements.</span></span> <span data-ttu-id="c4e58-108">All'interno del blocco, inserire il codice che gestisce la connessione al database.</span><span class="sxs-lookup"><span data-stu-id="c4e58-108">Inside the block, put the code that deals with the database connection.</span></span>  
  
3. <span data-ttu-id="c4e58-109">Dichiarare la connessione e crearne un'istanza come parte dell'istruzione `Using`.</span><span class="sxs-lookup"><span data-stu-id="c4e58-109">Declare the connection and create an instance of it as part of the `Using` statement.</span></span>  
  
    ```vb  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     <span data-ttu-id="c4e58-110">Il sistema elimina la risorsa indipendentemente dal modo in cui si esce dal blocco, incluso il caso di un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="c4e58-110">The system disposes of the resource no matter how you exit the block, including the case of an unhandled exception.</span></span>  
  
     <span data-ttu-id="c4e58-111">Si noti che non è possibile accedere a `sqc` dall'esterno del blocco `Using`, perché il relativo ambito è limitato al blocco.</span><span class="sxs-lookup"><span data-stu-id="c4e58-111">Note that you cannot access `sqc` from outside the `Using` block, because its scope is limited to the block.</span></span>  
  
     <span data-ttu-id="c4e58-112">È possibile utilizzare la stessa tecnica in una risorsa di sistema, ad esempio un handle di file o un wrapper COM.</span><span class="sxs-lookup"><span data-stu-id="c4e58-112">You can use this same technique on a system resource such as a file handle or a COM wrapper.</span></span> <span data-ttu-id="c4e58-113">Utilizzare un blocco di `Using` quando si desidera assicurarsi di lasciare la risorsa disponibile per altri componenti dopo aver terminato il blocco `Using`.</span><span class="sxs-lookup"><span data-stu-id="c4e58-113">You use a `Using` block when you want to be sure to leave the resource available for other components after you have exited the `Using` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4e58-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4e58-114">See also</span></span>

- <xref:System.Data.SqlClient.SqlConnection>
- [<span data-ttu-id="c4e58-115">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="c4e58-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="c4e58-116">Strutture decisionali</span><span class="sxs-lookup"><span data-stu-id="c4e58-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="c4e58-117">Strutture di ciclo</span><span class="sxs-lookup"><span data-stu-id="c4e58-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="c4e58-118">Altre strutture di controllo</span><span class="sxs-lookup"><span data-stu-id="c4e58-118">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="c4e58-119">Strutture di controllo annidate</span><span class="sxs-lookup"><span data-stu-id="c4e58-119">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="c4e58-120">Istruzione Using</span><span class="sxs-lookup"><span data-stu-id="c4e58-120">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)
