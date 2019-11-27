---
title: 'Procedura: chiamare una stored procedure utilizzando LINQ'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
ms.openlocfilehash: f91ccda1842887b3785ce304fd41bdd020a55479
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345032"
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a>Procedura: chiamare una stored procedure utilizzando LINQ (Visual Basic)
LINQ (Language-Integrated Query) consente di accedere facilmente alle informazioni sul database, inclusi oggetti di database quali stored procedure.  
  
 Nell'esempio seguente viene illustrato come creare un'applicazione che chiama un stored procedure in un database SQL Server. Nell'esempio viene illustrato come chiamare due diverse stored procedure nel database. Ogni procedura restituisce i risultati di una query. Una procedura accetta parametri di input e l'altra procedura non accetta parametri.  
  
 Negli esempi di questo argomento viene utilizzato il database di esempio Northwind. Se questo database non è presente nel computer di sviluppo, è possibile scaricarlo dal Microsoft Download Center. Per istruzioni, vedere [download di database di esempio](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>Per creare una connessione a un database  
  
1. In Visual Studio aprire **Esplora server**/**Esplora database** scegliendo **Esplora server**/**Esplora database** dal menu **Visualizza** .  
  
2. Fare clic con il pulsante destro del mouse su **connessioni dati** in **Esplora server**/**Esplora database** , quindi scegliere **Aggiungi connessione**.  
  
3. Specificare una connessione valida al database di esempio Northwind.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Per aggiungere un progetto che contiene un file di LINQ to SQL  
  
1. In Visual Studio scegliere **Nuovo** dal menu **File** e quindi fare clic su **Progetto**. Selezionare Visual Basic **Windows Forms applicazione** come tipo di progetto.  
  
2. Nel menu **Progetto** fare clic su **Aggiungi nuovo elemento**. Selezionare il modello di elemento **classi LINQ to SQL** .  
  
3. Denominare il file `northwind.dbml`. Fare clic su **Add**. Il Object Relational Designer (O/R Designer) viene aperto per il file Northwind. dbml.  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a>Per aggiungere stored procedure a Progettazione relazionale di O/R  
  
1. In **Esplora server**/**Esplora database**espandere la connessione al database Northwind. Espandere la cartella **stored procedure** .  
  
     Se la finestra di progettazione di O/R è stata chiusa, è possibile riaprirla facendo doppio clic sul file Northwind. dbml aggiunto in precedenza.  
  
2. Fare clic su **Sales by Year** stored procedure e trascinarlo nel riquadro destro della finestra di progettazione. Fare clic sui **dieci prodotti più costosi** stored procedure trascinarli nel riquadro destro della finestra di progettazione.  
  
3. Salvare le modifiche e chiudere la finestra di progettazione.  
  
4. Salvare il progetto.  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a>Per aggiungere codice per visualizzare i risultati delle stored procedure  
  
1. Dalla **casella degli strumenti**trascinare un controllo <xref:System.Windows.Forms.DataGridView> nel Windows Form predefinito per il progetto Form1.  
  
2. Fare doppio clic su Form1 per aggiungere codice al relativo evento `Load`.  
  
3. Quando sono state aggiunte stored procedure a Progettazione relazionale oggetti, nella finestra di progettazione è stato aggiunto un oggetto <xref:System.Data.Linq.DataContext> per il progetto. Questo oggetto contiene il codice necessario per accedere a tali procedure. L'oggetto <xref:System.Data.Linq.DataContext> per il progetto viene denominato in base al nome del file con estensione dbml. Per questo progetto, l'oggetto <xref:System.Data.Linq.DataContext> è denominato `northwindDataContext`.  
  
     È possibile creare un'istanza del <xref:System.Data.Linq.DataContext> nel codice e chiamare i metodi di stored procedure specificati da O/R Designer. Per eseguire l'associazione all'oggetto <xref:System.Windows.Forms.DataGridView>, potrebbe essere necessario forzare l'esecuzione immediata della query chiamando il metodo <xref:System.Linq.Enumerable.ToList%2A> sui risultati della stored procedure.  
  
     Aggiungere il codice seguente all'evento `Load` per chiamare una delle stored procedure esposte come metodi per il contesto dati.  
  
     [!code-vb[VbLINQtoSQLHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#1)]  
    [!code-vb[VbLINQtoSQLHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#2)]  
  
4. Premere F5 per eseguire il progetto e visualizzare i risultati.  
  
## <a name="see-also"></a>Vedere anche

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Query](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Metodi DataContext (O/R Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [Procedura: Assegnare stored procedure per eseguire aggiornamenti, inserimenti ed eliminazioni (O/R Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
