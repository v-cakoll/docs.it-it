---
title: 'Procedura: Chiamare una stored procedure usando LINQ'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
ms.openlocfilehash: b451642a16f36c4f7fd19c853fdfd2282f5bede5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405030"
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a>Procedura: chiamare una stored procedure utilizzando LINQ (Visual Basic)
LINQ (Language-Integrated Query) consente di accedere facilmente alle informazioni sul database, inclusi oggetti di database quali stored procedure.  
  
 Nell'esempio seguente viene illustrato come creare un'applicazione che chiama un stored procedure in un database SQL Server. Nell'esempio viene illustrato come chiamare due diverse stored procedure nel database. Ogni procedura restituisce i risultati di una query. Una procedura accetta parametri di input e l'altra procedura non accetta parametri.  
  
 Negli esempi di questo argomento viene utilizzato il database di esempio Northwind. Se questo database non è presente nel computer di sviluppo, è possibile scaricarlo dall'Area download Microsoft. Per istruzioni, vedere [download di database di esempio](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>Per creare una connessione a un database  
  
1. In Visual Studio aprire **Esplora server** / **Esplora database** facendo clic su **Esplora server** / **Esplora database** dal menu **Visualizza** .  
  
2. Fare clic con il pulsante destro del mouse su **connessioni dati** in **Esplora server** / **Esplora database** , quindi scegliere **Aggiungi connessione**.  
  
3. Specificare una connessione valida al database di esempio Northwind.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Per aggiungere un progetto che contiene un file di LINQ to SQL  
  
1. In Visual Studio scegliere **nuovo** dal menu **file** , quindi fare clic su **progetto**. Selezionare Visual Basic **Windows Forms applicazione** come tipo di progetto.  
  
2. Dal menu **Progetto** fare clic su **Aggiungi nuovo elemento**. Selezionare il modello di elemento **classi LINQ to SQL** .  
  
3. Assegnare al file il nome `northwind.dbml`. Scegliere **Aggiungi**. Il Object Relational Designer (O/R Designer) viene aperto per il file Northwind. dbml.  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a>Per aggiungere stored procedure a Progettazione relazionale di O/R  
  
1. In **Esplora server** / **Esplora database**espandere la connessione al database Northwind. Espandere la cartella **Stored procedure** .  
  
     Se la finestra di progettazione di O/R è stata chiusa, è possibile riaprirla facendo doppio clic sul file Northwind. dbml aggiunto in precedenza.  
  
2. Fare clic su **Sales by Year** stored procedure e trascinarlo nel riquadro destro della finestra di progettazione. Fare clic sui **dieci prodotti più costosi** stored procedure trascinarli nel riquadro destro della finestra di progettazione.  
  
3. Salvare le modifiche e chiudere la finestra di progettazione.  
  
4. Salvare il progetto.  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a>Per aggiungere codice per visualizzare i risultati delle stored procedure  
  
1. Dalla **casella degli strumenti**trascinare un <xref:System.Windows.Forms.DataGridView> controllo nel Windows Form predefinito per il progetto Form1.  
  
2. Fare doppio clic su Form1 per aggiungere codice al relativo `Load` evento.  
  
3. Quando sono state aggiunte stored procedure a Progettazione relazionale oggetti, nella finestra di progettazione è stato aggiunto un <xref:System.Data.Linq.DataContext> oggetto per il progetto. Questo oggetto contiene il codice necessario per accedere a tali procedure. L' <xref:System.Data.Linq.DataContext> oggetto per il progetto viene denominato in base al nome del file con estensione dbml. Per questo progetto, l' <xref:System.Data.Linq.DataContext> oggetto è denominato `northwindDataContext` .  
  
     È possibile creare un'istanza di <xref:System.Data.Linq.DataContext> nel codice e chiamare i metodi stored procedure specificati da O/R Designer. Per eseguire l'associazione all' <xref:System.Windows.Forms.DataGridView> oggetto, potrebbe essere necessario forzare l'esecuzione immediata della query chiamando il <xref:System.Linq.Enumerable.ToList%2A> metodo sui risultati della stored procedure.  
  
     Aggiungere il codice seguente all' `Load` evento per chiamare una delle stored procedure esposte come metodi per il contesto dati.  
  
     [!code-vb[VbLINQtoSQLHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#1)]  
    [!code-vb[VbLINQtoSQLHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#2)]  
  
4. Premere F5 per eseguire il progetto e visualizzare i risultati.  
  
## <a name="see-also"></a>Vedere anche

- [LINQ](index.md)
- [Query](../../../language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Metodi DataContext (O/R Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [Procedura: Assegnare stored procedure per eseguire aggiornamenti, inserimenti ed eliminazioni (O/R Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
