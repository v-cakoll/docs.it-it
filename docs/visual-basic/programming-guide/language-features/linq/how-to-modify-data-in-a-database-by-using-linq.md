---
title: 'Procedura: modificare dati in un database utilizzando LINQ (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- inserting rows [LINQ to SQL]
- deleting rows [LINQ to SQL]
- updating rows [LINQ to SQL]
- inserting data [Visual Basic]
- deleting data
- data [Visual Basic], updating
- updating data [LINQ]
- queries [LINQ in Visual Basic], data changes in database
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: cf52635f-0c1b-46c3-aff1-bdf181cf19b1
ms.openlocfilehash: ebf0ed1be8d74b60b7e626db996e7cefb1c01131
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524520"
---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a>Procedura: modificare dati in un database utilizzando LINQ (Visual Basic)

Con le query LINQ (Language-Integrated Query) è possibile accedere facilmente alle informazioni sul database e modificare i valori nel database.

Nell'esempio seguente viene illustrato come creare una nuova applicazione che recupera e aggiorna le informazioni in un database SQL Server.

Negli esempi di questo argomento viene utilizzato il database di esempio Northwind. Se il database non è presente nel computer di sviluppo, è possibile scaricarlo dall'area download Microsoft. Per istruzioni, vedere [download di database di esempio](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).

### <a name="to-create-a-connection-to-a-database"></a>Per creare una connessione a un database

1. In Visual Studio aprire **Esplora server** /**Esplora database** facendo clic sul menu **visualizza** , quindi selezionare **Esplora server** /**Esplora database**.

2. Fare clic con il pulsante destro del mouse su **connessioni dati** in **Esplora server** /**Esplora database**e scegliere **Aggiungi connessione**.

3. Specificare una connessione valida al database di esempio Northwind.

### <a name="to-add-a-project-with-a-linq-to-sql-file"></a>Per aggiungere un progetto con un file di LINQ to SQL

1. In Visual Studio scegliere **Nuovo** dal menu **File** e quindi fare clic su **Progetto**. Selezionare Visual Basic **Windows Forms applicazione** come tipo di progetto.

2. Nel menu **Progetto** fare clic su **Aggiungi nuovo elemento**. Selezionare il modello di elemento **classi LINQ to SQL** .

3. Denominare il file `northwind.dbml`. Fare clic su **Aggiungi**. Il Object Relational Designer (O/R Designer) viene aperto per il file di `northwind.dbml`.

### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a>Per aggiungere tabelle per eseguire query e modifiche nella finestra di progettazione

1. In **Esplora server** /**Esplora database**espandere la connessione al database Northwind. Espandere la cartella **tabelle** .

     Se la finestra di progettazione di O/R è stata chiusa, è possibile riaprirla facendo doppio clic sul file `northwind.dbml` aggiunto in precedenza.

2. Fare clic sulla tabella Customers e trascinarla nel riquadro sinistro della finestra di progettazione.

     La finestra di progettazione crea un nuovo oggetto Customer per il progetto.

3. Salvare le modifiche e chiudere la finestra di progettazione.

4. Salvare il progetto.

### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a>Per aggiungere codice per modificare il database e visualizzare i risultati

1. Dalla **casella degli strumenti**trascinare un controllo <xref:System.Windows.Forms.DataGridView> nel Windows Form predefinito per il progetto Form1.

2. Quando sono state aggiunte tabelle a Progettazione relazionale oggetti, nella finestra di progettazione è stato aggiunto un oggetto <xref:System.Data.Linq.DataContext> al progetto. Questo oggetto contiene codice che è possibile utilizzare per accedere alla tabella Customers. Contiene anche codice che definisce un oggetto Customer locale e una raccolta Customers per la tabella. L'oggetto <xref:System.Data.Linq.DataContext> per il progetto viene denominato in base al nome del file con estensione dbml. Per questo progetto, l'oggetto <xref:System.Data.Linq.DataContext> è denominato `northwindDataContext`.

     È possibile creare un'istanza dell'oggetto <xref:System.Data.Linq.DataContext> nel codice e cercare e modificare la raccolta Customers specificata da O/R Designer. Le modifiche apportate alla raccolta Customers non vengono riflesse nel database fino a quando non vengono inviate chiamando il metodo di <xref:System.Data.Linq.DataContext.SubmitChanges%2A> dell'oggetto <xref:System.Data.Linq.DataContext>.

     Fare doppio clic su Windows Form, Form1, per aggiungere codice all'evento <xref:System.Windows.Forms.Form.Load> per eseguire una query sulla tabella Customers esposta come proprietà del <xref:System.Data.Linq.DataContext>. Aggiungere il codice seguente:

    ```vb
    Private db As northwindDataContext

    Private Sub Form1_Load(ByVal sender As System.Object,
                           ByVal e As System.EventArgs
                          ) Handles MyBase.Load
      db = New northwindDataContext()

      RefreshData()
    End Sub

    Private Sub RefreshData()
      Dim customers = From cust In db.Customers
                      Where cust.City(0) = "W"
                      Select cust

      DataGridView1.DataSource = customers
    End Sub
    ```

3. Dalla **casella degli strumenti**Trascinare tre controlli <xref:System.Windows.Forms.Button> nel form. Selezionare il primo controllo `Button`. Nella finestra **Proprietà** impostare la `Name` del controllo `Button` su `AddButton` e la `Text` su `Add`. Selezionare il secondo pulsante e impostare la proprietà `Name` su `UpdateButton` e la proprietà `Text` su `Update`. Selezionare il terzo pulsante e impostare la proprietà `Name` su `DeleteButton` e la proprietà `Text` su `Delete`.

4. Fare doppio clic sul pulsante **Aggiungi** per aggiungere il codice al relativo evento `Click`. Aggiungere il codice seguente:

    ```vb
    Private Sub AddButton_Click(ByVal sender As System.Object,
                                ByVal e As System.EventArgs
                               ) Handles AddButton.Click
      Dim cust As New Customer With {
        .City = "Wellington",
        .CompanyName = "Blue Yonder Airlines",
        .ContactName = "Jill Frank",
        .Country = "New Zealand",
        .CustomerID = "JILLF"}

      db.Customers.InsertOnSubmit(cust)

      Try
        db.SubmitChanges()
      Catch
        ' Handle exception.
      End Try

      RefreshData()
    End Sub
    ```

5. Fare doppio clic sul pulsante **Aggiorna** per aggiungere codice al relativo evento `Click`. Aggiungere il codice seguente:

    ```vb
    Private Sub UpdateButton_Click(ByVal sender As System.Object, _
                                   ByVal e As System.EventArgs
                                  ) Handles UpdateButton.Click
      Dim updateCust = (From cust In db.Customers
                        Where cust.CustomerID = "JILLF").ToList()(0)

      updateCust.ContactName = "Jill Shrader"
      updateCust.Country = "Wales"
      updateCust.CompanyName = "Red Yonder Airlines"
      updateCust.City = "Cardiff"

      Try
        db.SubmitChanges()
      Catch
        ' Handle exception.
      End Try

      RefreshData()
    End Sub
    ```

6. Fare doppio clic sul pulsante **Elimina** per aggiungere codice al relativo evento `Click`. Aggiungere il codice seguente:

    ```vb
    Private Sub DeleteButton_Click(ByVal sender As System.Object, _
                                   ByVal e As System.EventArgs
                                  ) Handles DeleteButton.Click
      Dim deleteCust = (From cust In db.Customers
                        Where cust.CustomerID = "JILLF").ToList()(0)

      db.Customers.DeleteOnSubmit(deleteCust)

      Try
        db.SubmitChanges()
      Catch
        ' Handle exception.
      End Try

      RefreshData()
    End Sub
    ```

7. Premere F5 per eseguire il progetto. Fare clic su **Aggiungi** per aggiungere un nuovo record. Fare clic su **Aggiorna** per modificare il nuovo record. Fare clic su **Elimina** per eliminare il nuovo record.

## <a name="see-also"></a>Vedere anche

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Query](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Metodi DataContext (O/R Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [Procedura: Assegnare stored procedure per eseguire aggiornamenti, inserimenti ed eliminazioni (O/R Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
