---
title: 'Procedura: restituire un risultato di query LINQ come tipo specifico'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], specific type returned
- projection [LINQ in Visual Basic]
- anonymous types [Visual Basic]
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 621bb10a-e5d7-44fb-a025-317964b19d92
ms.openlocfilehash: c8ed792bf3ffefd903d60522f621958e44546d32
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404952"
---
# <a name="how-to-return-a-linq-query-result-as-a-specific-type-visual-basic"></a>Procedura: restituire un risultato di query LINQ come tipo specifico (Visual Basic)
LINQ (Language-Integrated Query) consente di accedere facilmente alle informazioni sul database ed eseguire query. Per impostazione predefinita, le query LINQ restituiscono un elenco di oggetti come tipo anonimo. È inoltre possibile specificare che una query restituisca un elenco di un tipo specifico utilizzando la `Select` clausola.  
  
 Nell'esempio seguente viene illustrato come creare una nuova applicazione che esegue query su un database di SQL Server e proietta i risultati come tipo denominato specifico. Per ulteriori informazioni, vedere [tipi anonimi](../objects-and-classes/anonymous-types.md) e [clausola SELECT](../../../language-reference/queries/select-clause.md).  
  
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
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a>Per aggiungere tabelle a query in Progettazione relazionale di O/R  
  
1. In **Esplora server** / **Esplora database**espandere la connessione al database Northwind. Espandere la cartella **Tabelle** .  
  
     Se la finestra di progettazione di O/R è stata chiusa, è possibile riaprirla facendo doppio clic sul file Northwind. dbml aggiunto in precedenza.  
  
2. Fare clic sulla tabella Customers e trascinarla nel riquadro sinistro della finestra di progettazione.  
  
     La finestra di progettazione crea un nuovo `Customer` oggetto per il progetto. È possibile proiettare un risultato di query come `Customer` tipo o come tipo creato dall'utente. In questo esempio viene creato un nuovo tipo in una procedura successiva e viene proiettato il risultato di una query come quel tipo.  
  
3. Salvare le modifiche e chiudere la finestra di progettazione.  
  
4. Salvare il progetto.  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a>Per aggiungere codice per eseguire query sul database e visualizzare i risultati  
  
1. Dalla **casella degli strumenti**trascinare un <xref:System.Windows.Forms.DataGridView> controllo nel Windows Form predefinito per il progetto Form1.  
  
2. Fare doppio clic su Form1 per modificare la classe Form1.  
  
3. Dopo l' `End Class` istruzione della classe Form1, aggiungere il codice seguente per creare un `CustomerInfo` tipo che contenga i risultati della query per questo esempio.  
  
     [!code-vb[VbLINQToSQLHowTos#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#16)]  
  
4. Quando sono state aggiunte tabelle a Progettazione relazionale oggetti, nella finestra di progettazione è stato aggiunto un <xref:System.Data.Linq.DataContext> oggetto al progetto. Questo oggetto contiene il codice necessario per accedere a tali tabelle e per accedere a oggetti e raccolte singoli per ogni tabella. L' <xref:System.Data.Linq.DataContext> oggetto per il progetto viene denominato in base al nome del file con estensione dbml. Per questo progetto, l' <xref:System.Data.Linq.DataContext> oggetto è denominato `northwindDataContext` .  
  
     È possibile creare un'istanza di <xref:System.Data.Linq.DataContext> nel codice ed eseguire una query sulle tabelle specificate da O/R Designer.  
  
     Nel `Load` caso della classe Form1, aggiungere il codice seguente per eseguire una query sulle tabelle esposte come proprietà del contesto dati. La `Select` clausola della query creerà un nuovo `CustomerInfo` tipo anziché un tipo anonimo per ogni elemento del risultato della query.  
  
     [!code-vb[VbLINQToSQLHowTos#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#15)]  
  
5. Premere F5 per eseguire il progetto e visualizzare i risultati.  
  
## <a name="see-also"></a>Vedere anche

- [LINQ](index.md)
- [Query](../../../language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Metodi DataContext (O/R Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
