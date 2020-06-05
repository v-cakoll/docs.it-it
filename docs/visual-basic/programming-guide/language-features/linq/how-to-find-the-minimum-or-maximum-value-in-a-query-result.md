---
title: 'Procedura: Trovare il valore minimo o massimo in un risultato di query usando LINQ'
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
ms.openlocfilehash: a148d8b726da78261eda152fcaafdd64ea01bb24
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404978"
---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a>Procedura: trovare il valore minimo o massimo in un risultato di query utilizzando LINQ (Visual Basic)
LINQ (Language-Integrated Query) consente di accedere facilmente alle informazioni sul database ed eseguire query.  
  
 Nell'esempio seguente viene illustrato come creare una nuova applicazione che esegue query su un database di SQL Server. L'esempio determina i valori minimo e massimo per i risultati usando le `Aggregate` `Group By` clausole e. Per ulteriori informazioni, vedere clausola [Aggregate](../../../language-reference/queries/aggregate-clause.md) e [clausola Group by](../../../language-reference/queries/group-by-clause.md).  
  
 Negli esempi di questo argomento viene utilizzato il database di esempio Northwind. Se questo database non è presente nel computer di sviluppo, è possibile scaricarlo dall'Area download Microsoft. Per istruzioni, vedere [download di database di esempio](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="create-a-connection-to-a-database"></a>Creare una connessione a un database  
  
1. In Visual Studio aprire **Esplora server** / **Esplora database** facendo clic su **Esplora server** / **Esplora database** dal menu **Visualizza** .  
  
2. Fare clic con il pulsante destro del mouse su **connessioni dati** in **Esplora server** / **Esplora database** , quindi scegliere **Aggiungi connessione**.  
  
3. Specificare una connessione valida al database di esempio Northwind.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Per aggiungere un progetto che contiene un file di LINQ to SQL  
  
1. In Visual Studio scegliere **nuovo** dal menu **file** , quindi fare clic su **progetto**. Selezionare Visual Basic **Windows Forms applicazione** come tipo di progetto.  
  
2. Dal menu **Progetto** fare clic su **Aggiungi nuovo elemento**. Selezionare il modello di elemento **classi LINQ to SQL** .  
  
3. Assegnare al file il nome `northwind.dbml`. Scegliere **Aggiungi**. Il Object Relational Designer (O/R Designer) viene aperto per il file Northwind. dbml.  
  
## <a name="add-tables-to-query-to-the-or-designer"></a>Aggiungere tabelle a query in Progettazione relazionale di O/R  
  
1. In **Esplora server** / **Esplora database**espandere la connessione al database Northwind. Espandere la cartella **Tabelle** .  
  
     Se la finestra di progettazione di O/R è stata chiusa, è possibile riaprirla facendo doppio clic sul file Northwind. dbml aggiunto in precedenza.  
  
2. Fare clic sulla tabella Customers e trascinarla nel riquadro sinistro della finestra di progettazione. Fare clic sulla tabella Orders e trascinarlo nel riquadro sinistro della finestra di progettazione.  
  
     La finestra di progettazione crea nuovi `Customer` `Order` oggetti e per il progetto. Si noti che la finestra di progettazione rileva automaticamente le relazioni tra le tabelle e crea le proprietà figlio per gli oggetti correlati. Ad esempio, IntelliSense indicherà che l' `Customer` oggetto dispone di una `Orders` proprietà per tutti gli ordini correlati a tale cliente.  
  
3. Salvare le modifiche e chiudere la finestra di progettazione.  
  
4. Salvare il progetto.  
  
## <a name="add-code-to-query-the-database-and-display-the-results"></a>Aggiungere codice per eseguire query sul database e visualizzare i risultati  
  
1. Dalla **casella degli strumenti**trascinare un <xref:System.Windows.Forms.DataGridView> controllo nel Windows Form predefinito per il progetto Form1.  
  
2. Fare doppio clic su Form1 per aggiungere codice all' `Load` evento del modulo.  
  
3. Quando sono state aggiunte tabelle a Progettazione relazionale oggetti, nella finestra di progettazione è stato aggiunto un <xref:System.Data.Linq.DataContext> oggetto per il progetto. Questo oggetto contiene il codice necessario per accedere a tali tabelle, oltre a singoli oggetti e raccolte per ogni tabella. L' <xref:System.Data.Linq.DataContext> oggetto per il progetto viene denominato in base al nome del file con estensione dbml. Per questo progetto, l' <xref:System.Data.Linq.DataContext> oggetto è denominato `northwindDataContext` .  
  
     È possibile creare un'istanza di <xref:System.Data.Linq.DataContext> nel codice ed eseguire una query sulle tabelle specificate da O/R Designer.  
  
     Aggiungere il codice seguente all' `Load` evento. Questo codice esegue una query sulle tabelle esposte come proprietà del contesto dati e determina i valori minimo e massimo per i risultati. Nell'esempio viene utilizzata la `Aggregate` clausola per eseguire una query per ottenere un singolo risultato e la `Group By` clausola per visualizzare una media per i risultati raggruppati.  
  
     [!code-vb[VbLINQToSQLHowTos#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form7.vb#14)]  
  
4. Premere **F5** per eseguire il progetto e visualizzare i risultati.  
  
## <a name="see-also"></a>Vedere anche

- [LINQ](index.md)
- [Query](../../../language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Metodi DataContext (O/R Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
