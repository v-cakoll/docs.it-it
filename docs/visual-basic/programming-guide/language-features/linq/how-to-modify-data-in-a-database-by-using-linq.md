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
ms.openlocfilehash: 617bb62f9009c507658b5d1262657cb4dfa860e9
ms.sourcegitcommit: d955cb4c681d68cf301d410925d83f25172ece86
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2018
ms.locfileid: "34827111"
---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a>Procedura: modificare dati in un database utilizzando LINQ (Visual Basic)
Language-Integrated Query (LINQ) in query rendono più semplice accedere alle informazioni di database e modificare i valori presenti nel database.  
  
 Nell'esempio seguente viene illustrato come creare una nuova applicazione che recupera e aggiorna le informazioni in un database di SQL Server.  
  
 Gli esempi in questo argomento usano il database di esempio Northwind. Se non è il database nel computer di sviluppo, è possibile scaricare da Microsoft Download Center. Per istruzioni, vedere [download dei database di esempio](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
### <a name="to-create-a-connection-to-a-database"></a>Per creare una connessione a un database  
  
1.  In Visual Studio, aprire **Esplora Server**/**Esplora Database** facendo il **vista** menu e quindi selezionare **Esplora Server** / **Esplora database**.  
  
2.  Fare doppio clic su **connessioni dati** in **Esplora Server**/**Esplora Database**, fare clic su **Aggiungi connessione**.  
  
3.  Specificare una connessione valida al database di esempio Northwind.  
  
### <a name="to-add-a-project-with-a-linq-to-sql-file"></a>Per aggiungere un progetto con una LINQ file SQL  
  
1.  In Visual Studio scegliere **Nuovo** dal menu **File** e quindi fare clic su **Progetto**. Selezionare Visual Basic **Windows Forms Application** come tipo di progetto.  
  
2.  Nel menu **Progetto** fare clic su **Aggiungi nuovo elemento**. Selezionare il **classi LINQ to SQL** modello di elemento.  
  
3.  Denominare il file `northwind.dbml`. Fare clic su **Aggiungi**. Viene aperto il Object Relational Designer (O/R Designer) per il `northwind.dbml` file.  
  
### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a>Per aggiungere tabelle per eseguire query e modificare nella finestra di progettazione  
  
1.  In **Esplora Server**/**Esplora Database**, espandere la connessione al database Northwind. Espandere il **tabelle** cartella.  
  
     Se è stato chiuso O/R Designer, è possibile riaprirlo facendo doppio clic su di `northwind.dbml` file aggiunto in precedenza.  
  
2.  Fare clic sulla tabella di clienti e trascinarlo nel riquadro sinistro della finestra di progettazione.  
  
     La finestra di progettazione crea un nuovo oggetto Customer per il progetto.  
  
3.  Salvare le modifiche e chiudere la finestra di progettazione.  
  
4.  Salvare il progetto.  
  
### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a>Per aggiungere il codice per modificare il database e visualizzare i risultati  
  
1.  Dal **della casella degli strumenti**, trascinare un <xref:System.Windows.Forms.DataGridView> controllo Windows Form predefinito per il progetto, Form1.  
  
2.  Quando si aggiungono tabelle alla finestra di Progettazione relazionale, la finestra di progettazione aggiunge un <xref:System.Data.Linq.DataContext> oggetto al progetto. Questo oggetto contiene codice che è possibile utilizzare per accedere alla tabella Customers. Contiene anche il codice che definisce un oggetto Customer locale e una raccolta di clienti per la tabella. Il <xref:System.Data.Linq.DataContext> oggetto per il progetto viene denominato in base al nome del file. dbml. Per questo progetto, il <xref:System.Data.Linq.DataContext> oggetto è denominato `northwindDataContext`.  
  
     È possibile creare un'istanza di <xref:System.Data.Linq.DataContext> dell'oggetto nel codice e query e modificare la raccolta di clienti specificata da O/R Designer. Le modifiche apportate alla raccolta di clienti non vengono riflesse nel database fino a quando non vengono inviate tramite la chiamata di <xref:System.Data.Linq.DataContext.SubmitChanges%2A> metodo il <xref:System.Data.Linq.DataContext> oggetto.  
  
     Fare doppio clic su Windows Form, Form1 per aggiungere il codice per il <xref:System.Windows.Forms.Form.Load> evento per eseguire query nella tabella Customers è che viene esposto come una proprietà del <xref:System.Data.Linq.DataContext>. Aggiungere il codice seguente:  
  
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
  
3.  Dal **della casella degli strumenti**, trascinare i tre <xref:System.Windows.Forms.Button> controlli nel form. Selezionare il primo `Button` controllo. Nel **proprietà** finestra, impostare il `Name` del `Button` il controllo a `AddButton` e `Text` a `Add`. Selezionare il secondo pulsante e impostare il `Name` proprietà `UpdateButton` e `Text` proprietà `Update`. Selezionare il terzo pulsante e impostare il `Name` proprietà `DeleteButton` e `Text` proprietà `Delete`.  
  
4.  Fare doppio clic su di **Aggiungi** pulsante per aggiungere codice al relativo `Click` evento. Aggiungere il codice seguente:  
  
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
  
5.  Fare doppio clic su di **aggiornamento** pulsante per aggiungere codice al relativo `Click` evento. Aggiungere il codice seguente:  
  
    ```vb  
    Private Sub UpdateButton_Click(ByVal sender As System.Object, _  
                                   ByVal e As System.EventArgs  
                                  ) Handles UpdateButton.Click  
      Dim updateCust = (From cust In db.Customers   
                        Where cust.CustomerID = "JILLF").ToList()(0)  
  
      updateCust.ContactName = "Jill Shrader"  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
6.  Fare doppio clic su di **eliminare** pulsante per aggiungere codice al relativo `Click` evento. Aggiungere il codice seguente:  
  
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
  
7.  Premere F5 per eseguire il progetto. Fare clic su **Aggiungi** per aggiungere un nuovo record. Fare clic su **aggiornamento** per modificare il nuovo record. Fare clic su **eliminare** per eliminare il nuovo record.  
  
## <a name="see-also"></a>Vedere anche  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Query](../../../../visual-basic/language-reference/queries/queries.md)  
 [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)  
 [Metodi DataContext (O/R Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [Procedura: assegnare stored procedure per eseguire aggiornamenti, inserimenti ed eliminazioni (O/R Designer)](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)
