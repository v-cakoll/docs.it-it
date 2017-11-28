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
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a>Procedura: eliminare una risorsa di sistema (Visual Basic)
È possibile utilizzare un `Using` blocco per garantire che il sistema elimina una risorsa quando il codice esce dal blocco. Ciò è utile se si utilizza una risorsa di sistema che utilizza una grande quantità di memoria o che anche altri componenti desidera utilizzare.  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a>Per eliminare una connessione al database quando il codice è finito di usarlo  
  
1.  Assicurarsi di includere appropriata [istruzione Imports (tipo e Namespace .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) per la connessione al database all'inizio del file di origine (in questo caso, <xref:System.Data.SqlClient>).  
  
2.  Creare un `Using` blocco con il `Using` e `End Using` istruzioni. All'interno del blocco, inserire il codice che gestisce la connessione al database.  
  
3.  Dichiarare la connessione e creare un'istanza come parte di `Using` istruzione.  
  
    ```  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     Il sistema elimina la risorsa indipendentemente da come si esce dal blocco, incluso il caso di un'eccezione non gestita.  
  
     Si noti che è possibile accedere a `sqc` di fuori di `Using` blocco, perché il relativo ambito è limitato al blocco.  
  
     È possibile utilizzare la stessa tecnica su una risorsa di sistema, ad esempio un handle di file o un oggetto COM wrapper. Si utilizza un `Using` blocco quando si desidera assicurarsi che la risorsa disponibile per altri componenti dopo la chiusura di `Using` blocco.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Data.SqlClient.SqlConnection>  
 [Flusso di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [Strutture decisionali](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [Strutture di ciclo](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Altre strutture di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)  
 [Strutture di controllo annidate](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Istruzione Using](../../../../visual-basic/language-reference/statements/using-statement.md)
