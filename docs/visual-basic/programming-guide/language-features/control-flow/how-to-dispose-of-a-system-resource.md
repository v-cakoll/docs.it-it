---
title: 'Procedura: eliminare una risorsa di sistema (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Using statement [Visual Basic], disposing of system resources
- Visual Basic code, control flow
- system resources, disposing of
- resources [Visual Basic], disposing of system
- system resources
- Using statement [Visual Basic], Using...End Using
- Using block
ms.assetid: 8be2b239-8090-419b-8e7e-bcaa75b0ecc8
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5b5c65c9d123c6f481852eb249cb4d479a180c5b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a><span data-ttu-id="65c2d-102">Procedura: eliminare una risorsa di sistema (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65c2d-102">How to: Dispose of a System Resource (Visual Basic)</span></span>
<span data-ttu-id="65c2d-103">È possibile utilizzare un `Using` blocco per garantire che il sistema elimina una risorsa quando il codice esce dal blocco.</span><span class="sxs-lookup"><span data-stu-id="65c2d-103">You can use a `Using` block to guarantee that the system disposes of a resource when your code exits the block.</span></span> <span data-ttu-id="65c2d-104">Ciò è utile se si utilizza una risorsa di sistema che utilizza una grande quantità di memoria o che anche altri componenti desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="65c2d-104">This is useful if you are using a system resource that consumes a large amount of memory, or that other components also want to use.</span></span>  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a><span data-ttu-id="65c2d-105">Per eliminare una connessione al database quando il codice è finito di usarlo</span><span class="sxs-lookup"><span data-stu-id="65c2d-105">To dispose of a database connection when your code is finished with it</span></span>  
  
1.  <span data-ttu-id="65c2d-106">Assicurarsi di includere appropriata [istruzione Imports (tipo e Namespace .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) per la connessione al database all'inizio del file di origine (in questo caso, <xref:System.Data.SqlClient>).</span><span class="sxs-lookup"><span data-stu-id="65c2d-106">Make sure you include the appropriate [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) for the database connection at the beginning of your source file (in this case, <xref:System.Data.SqlClient>).</span></span>  
  
2.  <span data-ttu-id="65c2d-107">Creare un `Using` blocco con il `Using` e `End Using` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="65c2d-107">Create a `Using` block with the `Using` and `End Using` statements.</span></span> <span data-ttu-id="65c2d-108">All'interno del blocco, inserire il codice che gestisce la connessione al database.</span><span class="sxs-lookup"><span data-stu-id="65c2d-108">Inside the block, put the code that deals with the database connection.</span></span>  
  
3.  <span data-ttu-id="65c2d-109">Dichiarare la connessione e creare un'istanza come parte di `Using` istruzione.</span><span class="sxs-lookup"><span data-stu-id="65c2d-109">Declare the connection and create an instance of it as part of the `Using` statement.</span></span>  
  
    ```  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     <span data-ttu-id="65c2d-110">Il sistema elimina la risorsa indipendentemente da come si esce dal blocco, incluso il caso di un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="65c2d-110">The system disposes of the resource no matter how you exit the block, including the case of an unhandled exception.</span></span>  
  
     <span data-ttu-id="65c2d-111">Si noti che è possibile accedere a `sqc` di fuori di `Using` blocco, perché il relativo ambito è limitato al blocco.</span><span class="sxs-lookup"><span data-stu-id="65c2d-111">Note that you cannot access `sqc` from outside the `Using` block, because its scope is limited to the block.</span></span>  
  
     <span data-ttu-id="65c2d-112">È possibile utilizzare la stessa tecnica su una risorsa di sistema, ad esempio un handle di file o un oggetto COM wrapper.</span><span class="sxs-lookup"><span data-stu-id="65c2d-112">You can use this same technique on a system resource such as a file handle or a COM wrapper.</span></span> <span data-ttu-id="65c2d-113">Si utilizza un `Using` blocco quando si desidera assicurarsi che la risorsa disponibile per altri componenti dopo la chiusura di `Using` blocco.</span><span class="sxs-lookup"><span data-stu-id="65c2d-113">You use a `Using` block when you want to be sure to leave the resource available for other components after you have exited the `Using` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65c2d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65c2d-114">See Also</span></span>  
 <xref:System.Data.SqlClient.SqlConnection>  
 [<span data-ttu-id="65c2d-115">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="65c2d-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="65c2d-116">Strutture decisionali</span><span class="sxs-lookup"><span data-stu-id="65c2d-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="65c2d-117">Strutture di ciclo</span><span class="sxs-lookup"><span data-stu-id="65c2d-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="65c2d-118">Altre strutture di controllo</span><span class="sxs-lookup"><span data-stu-id="65c2d-118">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)  
 [<span data-ttu-id="65c2d-119">Strutture di controllo annidate</span><span class="sxs-lookup"><span data-stu-id="65c2d-119">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="65c2d-120">Istruzione Using</span><span class="sxs-lookup"><span data-stu-id="65c2d-120">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)
