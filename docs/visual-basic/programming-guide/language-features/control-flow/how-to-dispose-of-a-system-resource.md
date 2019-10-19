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
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a>Procedura: eliminare una risorsa di sistema (Visual Basic)
È possibile usare un blocco di `Using` per garantire che il sistema elimini una risorsa quando il codice esce dal blocco. Questa opzione è utile se si usa una risorsa di sistema che usa una quantità elevata di memoria o che anche altri componenti desiderano usare.  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a>Per eliminare una connessione al database al termine del codice  
  
1. Assicurarsi di includere l' [istruzione Imports appropriata (tipo e spazio dei nomi .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) per la connessione al database all'inizio del file di origine (in questo caso, <xref:System.Data.SqlClient>).  
  
2. Creare un blocco di `Using` con le istruzioni `Using` e `End Using`. All'interno del blocco, inserire il codice che gestisce la connessione al database.  
  
3. Dichiarare la connessione e crearne un'istanza come parte dell'istruzione `Using`.  
  
    ```vb  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     Il sistema elimina la risorsa indipendentemente dal modo in cui si esce dal blocco, incluso il caso di un'eccezione non gestita.  
  
     Si noti che non è possibile accedere a `sqc` dall'esterno del blocco `Using`, perché il relativo ambito è limitato al blocco.  
  
     È possibile utilizzare la stessa tecnica in una risorsa di sistema, ad esempio un handle di file o un wrapper COM. Utilizzare un blocco di `Using` quando si desidera assicurarsi di lasciare la risorsa disponibile per altri componenti dopo aver terminato il blocco `Using`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Data.SqlClient.SqlConnection>
- [Flusso di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Strutture decisionali](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Strutture di ciclo](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Altre strutture di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [Strutture di controllo annidate](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Istruzione Using](../../../../visual-basic/language-reference/statements/using-statement.md)
