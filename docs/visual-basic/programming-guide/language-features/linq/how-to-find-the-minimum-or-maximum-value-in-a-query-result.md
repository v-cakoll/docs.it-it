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
ms.openlocfilehash: ef5f218cdcc7275f616486110825ad0b9df11cc3
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112362"
---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a>Procedura: trovare il valore minimo o massimo in un risultato di query utilizzando LINQ (Visual Basic)
Language-Integrated Query (LINQ) semplifica l'accesso alle informazioni del database e l'esecuzione di query.  
  
 Nell'esempio seguente viene illustrato come creare una nuova applicazione che esegue query su un database di SQL Server.The following example shows how to create a new application that performs queries against a SQL Server database. L'esempio determina i valori minimo e `Aggregate` massimo `Group By` per i risultati utilizzando le clausole e . Per ulteriori informazioni, vedere [Clausola di aggregazione](../../../../visual-basic/language-reference/queries/aggregate-clause.md) e [Clausola Group By](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
 Negli esempi di questo argomento viene utilizzato il database di esempio Northwind. Se questo database non è presente nel computer di sviluppo, è possibile scaricarlo dall'Area download Microsoft. Per istruzioni, consultate [Download di database di esempio.](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="create-a-connection-to-a-database"></a>Creare una connessione a un databaseCreate a connection to a database  
  
1. In Visual Studio aprire**Esplora database** di Esplora **server**/scegliendo**Esplora database** di Esplora/ **server**dal menu **Visualizza.**  
  
2. Fare clic con il pulsante destro del mouse su **Connessioni dati** in Esplora database **di Esplora**/**Database Explorer** server, quindi **scegliere Aggiungi connessione**.  
  
3. Specificare una connessione valida al database di esempio Northwind.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Per aggiungere un progetto che contiene un file LINQ to SQLTo add a project that contains a LINQ to SQL file  
  
1. In Visual Studio scegliere **Nuovo** dal menu **File,** quindi fare clic su **Progetto**. Selezionare **Applicazione Windows Form** di Visual Basic come tipo di progetto.  
  
2. Dal menu **Progetto** fare clic su **Aggiungi nuovo elemento**. Selezionare il modello di elemento **Classi LINQ to SQL.**  
  
3. Denominare il file `northwind.dbml`. Fare clic su **Aggiungi**. Progettazione relazionale oggetti (O/R Designer) viene aperto per il file northwind.dbml.  
  
## <a name="add-tables-to-query-to-the-or-designer"></a>Aggiungere tabelle per eseguire query a Progettazione relazionale oggetti  
  
1. In**Esplora database di Esplora**/ **server**espandere la connessione al database Northwind. Espandere la cartella **Tabelle** .  
  
     Se È stato chiuso Progettazione relazionale oggetti, è possibile riaprirlo facendo doppio clic sul file northwind.dbml aggiunto in precedenza.  
  
2. Fare clic sulla tabella Customers e trascinarla nel riquadro sinistro della finestra di progettazione. Fare clic sulla tabella Orders e trascinarla nel riquadro sinistro della finestra di progettazione.  
  
     La finestra `Customer` di `Order` progettazione crea nuovi oggetti per il progetto. Si noti che la finestra di progettazione rileva automaticamente le relazioni tra le tabelle e crea proprietà figlio per gli oggetti correlati. Ad esempio, IntelliSense mostrerà che l'oggetto `Customer` dispone di una `Orders` proprietà per tutti gli ordini correlati a tale cliente.  
  
3. Salvare le modifiche e chiudere la finestra di progettazione.  
  
4. Salvare il progetto.  
  
## <a name="add-code-to-query-the-database-and-display-the-results"></a>Aggiungere codice per eseguire query sul database e visualizzare i risultati  
  
1. Dalla **Casella degli** <xref:System.Windows.Forms.DataGridView> strumenti trascinare un controllo nel Windows Form predefinito per il progetto, Form1.  
  
2. Fare doppio clic su Form1 `Load` per aggiungere codice all'evento del form.  
  
3. Quando sono state aggiunte tabelle a Progettazione <xref:System.Data.Linq.DataContext> relazionale oggetti, la finestra di progettazione ha aggiunto un oggetto per il progetto. Questo oggetto contiene il codice necessario per accedere a tali tabelle, oltre a singoli oggetti e raccolte per ogni tabella. L'oggetto <xref:System.Data.Linq.DataContext> per il progetto viene denominato in base al nome del file con estensione dbml. Per questo progetto, l'oggetto <xref:System.Data.Linq.DataContext> è denominato `northwindDataContext`.  
  
     È possibile creare un'istanza <xref:System.Data.Linq.DataContext> di nel codice ed eseguire una query sulle tabelle specificate da Progettazione relazionale oggetti.  
  
     Aggiungere il codice `Load` seguente all'evento. Questo codice esegue una query sulle tabelle esposte come proprietà del contesto dati e determina i valori minimo e massimo per i risultati. Nell'esempio `Aggregate` viene utilizzata la clausola per `Group By` eseguire una query per un singolo risultato e la clausola per visualizzare una media per i risultati raggruppati.  
  
     [!code-vb[VbLINQToSQLHowTos#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form7.vb#14)]  
  
4. Premere **F5** per eseguire il progetto e visualizzare i risultati.  
  
## <a name="see-also"></a>Vedere anche

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Query](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [DataContext Methods (O/R Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
