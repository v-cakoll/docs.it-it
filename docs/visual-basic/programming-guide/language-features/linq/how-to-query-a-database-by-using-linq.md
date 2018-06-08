---
title: 'Procedura: eseguire query in un database utilizzando LINQ (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- query samples [LINQ]
- database querying [LINQ]
- queries [LINQ in Visual Basic], database querying
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: bcf5e9c3-a236-4399-9a7f-3991eca7cf56
ms.openlocfilehash: f17e0dc6956c5465f8269562705eb0f754f1585c
ms.sourcegitcommit: d955cb4c681d68cf301d410925d83f25172ece86
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2018
ms.locfileid: "34827261"
---
# <a name="how-to-query-a-database-by-using-linq-visual-basic"></a>Procedura: eseguire query in un database utilizzando LINQ (Visual Basic)
Language-Integrated Query (LINQ) rende più semplice accedere alle informazioni di database ed eseguire query.  
  
 Nell'esempio seguente viene illustrato come creare una nuova applicazione che esegue query su un database di SQL Server.  
  
 Gli esempi in questo argomento usano il database di esempio Northwind. Se non è il database nel computer di sviluppo, è possibile scaricare da Microsoft Download Center. Per istruzioni, vedere [download dei database di esempio](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-create-a-connection-to-a-database"></a>Per creare una connessione a un database  
  
1.  In Visual Studio, aprire **Esplora Server**/**Esplora Database** facendo **Esplora Server**/**Database Esplora** sul **vista** menu.  
  
2.  Fare doppio clic su **connessioni dati** in **Esplora Server**/**Esplora Database** e quindi fare clic su **Aggiungi connessione**.  
  
3.  Specificare una connessione valida al database di esempio Northwind.  
  
## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Per aggiungere un progetto che contiene un file LINQ to SQL  
  
1.  In Visual Studio scegliere **Nuovo** dal menu **File** e quindi fare clic su **Progetto**. Selezionare Visual Basic **Windows Forms Application** come tipo di progetto.  
  
2.  Nel menu **Progetto** fare clic su **Aggiungi nuovo elemento**. Selezionare il **classi LINQ to SQL** modello di elemento.  
  
3.  Denominare il file `northwind.dbml`. Fare clic su **Aggiungi**. Il Object Relational Designer (O/R Designer) è aperto per il file Northwind. dbml.  
  
## <a name="to-add-tables-to-query-to-the-or-designer"></a>Per aggiungere le tabelle di eseguire query O/R Designer  
  
1.  In **Esplora Server**/**Esplora Database**, espandere la connessione al database Northwind. Espandere il **tabelle** cartella.  
  
     Se è stato chiuso O/R Designer, è possibile riaprirlo facendo doppio clic sul file Northwind. dbml aggiunto in precedenza.  
  
2.  Fare clic sulla tabella di clienti e trascinarlo nel riquadro sinistro della finestra di progettazione. Fare clic sulla tabella Orders e trascinarlo nel riquadro sinistro della finestra di progettazione.  
  
     La finestra di progettazione crea nuovi `Customer` e `Order` oggetti per il progetto. Si noti che la finestra di progettazione automaticamente rileva le relazioni tra le tabelle e crea le proprietà per gli oggetti correlati figlio. Ad esempio, IntelliSense visualizzerà che il `Customer` oggetto ha un `Orders` proprietà per tutti gli ordini relativi a quel cliente.  
  
3.  Salvare le modifiche e chiudere la finestra di progettazione.  
  
4.  Salvare il progetto.  
  
## <a name="to-add-code-to-query-the-database-and-display-the-results"></a>Per aggiungere il codice per eseguire query sul database e visualizzare i risultati  
  
1.  Dal **della casella degli strumenti**, trascinare un <xref:System.Windows.Forms.DataGridView> controllo Windows Form predefinito per il progetto, Form1.  
  
2.  Fare doppio clic su Form1 per aggiungere il codice per il `Load` eventi del modulo.  
  
3.  Quando si aggiungono tabelle alla finestra di Progettazione relazionale, la finestra di progettazione aggiunge un <xref:System.Data.Linq.DataContext> oggetto per il progetto. Questo oggetto contiene il codice che è necessario disporre per accedere a tali tabelle, oltre ai singoli oggetti e raccolte per ogni tabella. Il <xref:System.Data.Linq.DataContext> oggetto per il progetto viene denominato in base al nome del file. dbml. Per questo progetto, il <xref:System.Data.Linq.DataContext> oggetto è denominato `northwindDataContext`.  
  
     È possibile creare un'istanza di <xref:System.Data.Linq.DataContext> nel codice e query vengono specificate le tabelle da O/R Designer.  
  
     Aggiungere il codice seguente per il `Load` evento per eseguire query su tabelle che sono esposte come proprietà del contesto dati.  
  
     [!code-vb[VbLINQToSQLHowTos#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_1.vb)]  
  
4.  Premere F5 per eseguire il progetto e visualizzare i risultati.  
  
5.  Di seguito sono illustrate alcune query aggiuntive che è possibile provare:  
  
     [!code-vb[VbLINQToSQLHowTos#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_2.vb)]  
    [!code-vb[VbLINQToSQLHowTos#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_3.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Query](../../../../visual-basic/language-reference/queries/queries.md)  
 [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)  
 [Metodi DataContext (O/R Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
