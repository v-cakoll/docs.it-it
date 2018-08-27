---
title: 'Procedura: trovare il valore minimo o massimo in un risultato di query utilizzando LINQ (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- max operator [LINQ in Visual Basic]
- aggregate operator [LINQ in Visual Basic]
- aggregate queries
- minimum values [LINQ in Visual Basic]
- min operator [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], minimum and maximum values
- Max property
- maximum values [LINQ in Visual Basic]
- Aggregate clause [Visual Basic]
- queries [LINQ in Visual Basic], aggregate queries
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 238b763b-7dcd-4b14-8050-b65500a4f71c
ms.openlocfilehash: 252601b12e21e122c316952f8e10ce04cbe3f78e
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/25/2018
ms.locfileid: "42924482"
---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a>Procedura: trovare il valore minimo o massimo in un risultato di query utilizzando LINQ (Visual Basic)
Language-Integrated Query (LINQ) semplifica accedere alle informazioni sul database ed eseguire query.  
  
 Nell'esempio seguente viene illustrato come creare una nuova applicazione che esegue query su un database di SQL Server. Nell'esempio vengono determinati i valori minimi e massimo per i risultati usando il `Aggregate` e `Group By` clausole. Per altre informazioni, vedere [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) e [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
 Gli esempi in questo argomento usano il database di esempio Northwind. Se non è questo database nel computer di sviluppo, è possibile scaricarlo da Microsoft Download Center. Per istruzioni, vedere [download dei database di esempio](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>Per creare una connessione a un database  
  
1.  In Visual Studio, aprire **Esplora Server**/**Database Explorer** facendo **Esplora Server**/**Database Esplora** nella **visualizzazione** menu.  
  
2.  Fare doppio clic su **connessioni dati** nelle **Esplora Server**/**Esplora Database** e quindi fare clic su **Aggiungi connessione**.  
  
3.  Specificare una connessione valida al database di esempio Northwind.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Per aggiungere un progetto che contiene un file LINQ to SQL  
  
1.  In Visual Studio scegliere **Nuovo** dal menu **File** e quindi fare clic su **Progetto**. Selezionare Visual Basic **Windows Forms Application** come tipo di progetto.  
  
2.  Nel menu **Progetto** fare clic su **Aggiungi nuovo elemento**. Selezionare il **classi LINQ to SQL** modello di elemento.  
  
3.  Denominare il file `northwind.dbml`. Fare clic su **Aggiungi**. Viene aperto il Object Relational Designer (O/R Designer) per il file Northwind. dbml.  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a>Per aggiungere tabelle a query a O/R Designer  
  
1.  Nelle **Esplora Server**/**Esplora Database**, espandere la connessione al database Northwind. Espandere la **tabelle** cartella.  
  
     Se è stato chiuso O/R Designer, è possibile riaprirlo facendo doppio clic sul file Northwind. dbml aggiunti in precedenza.  
  
2.  Fare clic nella tabella Customers e trascinarla nel riquadro sinistro della finestra di progettazione. Fare clic nella tabella Orders e trascinarla nel riquadro sinistro della finestra di progettazione.  
  
     La finestra di progettazione crea nuovi `Customer` e `Order` oggetti per il progetto. Si noti che la finestra di progettazione automaticamente rileva le relazioni tra le tabelle e crea figlio le proprietà per gli oggetti correlati. Ad esempio, IntelliSense mostrerà che il `Customer` oggetto ha un `Orders` proprietà per tutti gli ordini correlati a tale cliente.  
  
3.  Salvare le modifiche e chiudere la finestra di progettazione.  
  
4.  Salvare il progetto.  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a>Per aggiungere il codice per eseguire query sul database e visualizzare i risultati  
  
1.  Dal **casella degli strumenti**, trascinare un <xref:System.Windows.Forms.DataGridView> controllo nel Form di Windows predefinito per il progetto, Form1.  
  
2.  Fare doppio clic su Form1 per aggiungere il codice per il `Load` eventi del form.  
  
3.  Quando si aggiungono tabelle alla finestra di Progettazione relazionale oggetti, la finestra di progettazione aggiunge un <xref:System.Data.Linq.DataContext> oggetto per il progetto. Questo oggetto contiene il codice che è necessario disporre per accedere a tali tabelle, oltre ai singoli oggetti e raccolte per ogni tabella. Il <xref:System.Data.Linq.DataContext> oggetto per il progetto viene denominato in base al nome del file. dbml. Per questo progetto, il <xref:System.Data.Linq.DataContext> oggetto è denominato `northwindDataContext`.  
  
     È possibile creare un'istanza di <xref:System.Data.Linq.DataContext> nel codice e query nelle tabelle specificate dalla finestra di Progettazione relazionale oggetti.  
  
     Aggiungere il codice seguente per il `Load` evento. Questo codice esegue una query di tabelle che vengono esposti come proprietà del contesto dati e determina i valori minimi e massimo per i risultati. L'esempio Usa egli `Aggregate` clausola per eseguire query per un singolo risultato e il `Group By` clausola per visualizzare una media dei risultati raggruppati.  
  
     [!code-vb[VbLINQToSQLHowTos#14](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-find-the-minimum-or-maximum-value-in-a-query-result_1.vb)]  
  
4.  Premere F5 per eseguire il progetto e visualizzare i risultati.  
  
## <a name="see-also"></a>Vedere anche  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Query](../../../../visual-basic/language-reference/queries/index.md)  
 [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)  
 [Metodi DataContext (O/R Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
