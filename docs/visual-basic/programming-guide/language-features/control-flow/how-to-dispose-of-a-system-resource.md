---
title: 'Procedura: Eliminare una risorsa di sistema (Visual Basic)'
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
ms.openlocfilehash: 798650bbefc0c5b2ac097b87ab44a2b380117939
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523220"
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a>Procedura: Eliminare una risorsa di sistema (Visual Basic)
È possibile usare un `Using` blocco per garantire che il sistema elimina una risorsa quando il codice esce dal blocco. Ciò è utile se si usa una risorsa di sistema che utilizza una grande quantità di memoria o che altri componenti inoltre desiderano utilizzare.  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a>Per eliminare una connessione al database quando il codice ha finito di usarlo  
  
1.  Assicurarsi di includere l'appropriato [istruzione Imports (tipo e Namespace .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) per la connessione al database all'inizio del file di origine (in questo caso, <xref:System.Data.SqlClient>).  
  
2.  Creare un `Using` blocco con i `Using` e `End Using` istruzioni. All'interno del blocco, inserire il codice che gestisce la connessione al database.  
  
3.  Dichiarare la connessione e crearne un'istanza come parte di `Using` istruzione.  
  
    ```  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     Il sistema elimina le risorse, indipendentemente dal modo in cui si esce dal blocco, incluso il caso di un'eccezione non gestita.  
  
     Si noti che non è possibile accedere `sqc` all'esterno di `Using` blocca, perché il relativo ambito è limitato al blocco.  
  
     È possibile usare questa stessa tecnica su una risorsa di sistema, ad esempio un handle di file o un wrapper COM. Si utilizza un `Using` bloccare quando si desidera essere sicuri che la risorsa disponibile per gli altri componenti dopo la chiusura di `Using` blocco.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Data.SqlClient.SqlConnection>
- [Flusso di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Strutture decisionali](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Strutture di ciclo](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Altre strutture di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [Strutture di controllo annidate](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Istruzione Using](../../../../visual-basic/language-reference/statements/using-statement.md)
