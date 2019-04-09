---
title: 'Procedura dettagliata: Modifica dei dati (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: 1f6a54f6-ec33-452a-a37d-48122207bf14
ms.openlocfilehash: 34049f113ce9da0ed1c4cc63fd53093a0775bbad
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208306"
---
# <a name="walkthrough-manipulating-data-visual-basic"></a>Procedura dettagliata: Modifica dei dati (Visual Basic)
In questa procedura dettagliata viene descritto uno scenario [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] end-to-end di base per l'aggiunta, la modifica e l'eliminazione dei dati in un database. Si utilizzerà una copia del database di esempio Northwind per aggiungere un cliente, modificare il nome di un cliente ed eliminare un ordine.  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 Questa procedura dettagliata è stata scritta usando Impostazioni di sviluppo di Visual Basic.  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per l'esecuzione di questa procedura sono richiesti i seguenti elementi:  
  
-   Una cartella dedicata ("c:\linqtest2") in cui inserire i file usati nella procedura dettagliata. Creare la cartella prima di avviare la procedura.  
  
-   Il database di esempio Northwind.  
  
     Se questo database non è disponibile nel computer di sviluppo, è possibile scaricarlo dal sito di download Microsoft. Per istruzioni, vedere [download dei database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md). Dopo avere scaricato il database, copiare il file northwnd.mdf nella cartella c:\linqtest2.  
  
-   Un file di codice Visual Basic generato dal database Northwind.  
  
     È possibile generare questo file usando [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] o lo strumento SQLMetal. Questa procedura dettagliata è stata scritta usando lo strumento SQLMetal con la riga di comando seguente:  
  
     **sqlmetal /code:"c:\linqtest2\northwind.vb" /language:vb "C:\linqtest2\northwnd.mdf" /pluralize**  
  
     Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="overview"></a>Panoramica  
 La procedura dettagliata è costituita da sei attività principali:  
  
-   Creazione di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] soluzione in Visual Studio.  
  
-   Aggiunta del file di codice del database al progetto.  
  
-   Creazione di un nuovo oggetto Customer  
  
-   Modifica del nome di contatto di un cliente.  
  
-   Eliminazione di un ordine.  
  
-   Invio delle modifiche al database Northwind.  
  
## <a name="creating-a-linq-to-sql-solution"></a>Creazione di una soluzione LINQ to SQL  
 In questa prima attività, si crea una soluzione di Visual Studio che contiene i riferimenti necessari per compilare ed eseguire un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] progetto.  
  
#### <a name="to-create-a-linq-to-sql-solution"></a>Per creare una soluzione LINQ to SQL  
  
1.  Scegliere **Nuovo progetto** dal menu **File**di Visual Studio.  
  
2.  Nel **tipi di progetto** nel riquadro le **nuovo progetto** nella finestra di dialogo fare clic su **Visual Basic**.  
  
3.  Nel riquadro **Modelli** fare clic su **Applicazione console**.  
  
4.  Nel **Name** , digitare **LinqDataManipulationApp**.  
  
5.  Fare clic su **OK**.  
  
## <a name="adding-linq-references-and-directives"></a>Aggiunta di riferimenti e direttive LINQ  
 In questa procedura dettagliata vengono usati assembly che potrebbero non essere installati per impostazione predefinita nel progetto. Se `System.Data.Linq` non è elencato come riferimento nel progetto (fare clic su **Mostra tutti i file** nelle **Esplora soluzioni** ed espandere la **riferimenti** nodo), aggiungerlo come spiegato nella la procedura seguente.  
  
#### <a name="to-add-systemdatalinq"></a>Per aggiungere System.Data.Linq  
  
1.  Nelle **Esplora soluzioni**, fare doppio clic su **riferimenti**, quindi fare clic su **Aggiungi riferimento**.  
  
2.  Nel **Aggiungi riferimento** finestra di dialogo, fare clic su **.NET**, fare clic sull'assembly e quindi fare clic su **OK**.  
  
     L'assembly verrà aggiunto al progetto.  
  
3.  Nell'editor del codice, aggiungere la seguente direttiva sopra **Module1**:  
  
     [!code-vb[DLinqWalk3VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#1)]  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a>Aggiunta del file di codice di Northwind al progetto  
 In questa procedura si presuppone che sia stato usato lo strumento SQLMetal per generare un file di codice dal database di esempio Northwind. Per altre informazioni, vedere la sezione precedente relativa ai prerequisiti.  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a>Per aggiungere il file di codice di Northwind al progetto  
  
1.  Nel **Project** menu, fare clic su **Aggiungi elemento esistente**.  
  
2.  Nel **Aggiungi elemento esistente** finestra di dialogo, passare a c:\linqtest2\northwind.vb e quindi fare clic su **Add**.  
  
     Il file northwind.vb viene aggiunto al progetto.  
  
## <a name="setting-up-the-database-connection"></a>Impostazione della connessione al database  
 Eseguire innanzitutto il test della connessione al database. Notare in particolare che nel nome del database, Northwnd, non è presente il carattere i. Se vengono generati errori nei passaggi successivi, esaminare il file northwind.vb per determinare come è digitata la classe parziale Northwind.  
  
#### <a name="to-set-up-and-test-the-database-connection"></a>Per impostare e testare la connessione al database  
  
1.  Digitare o incollare il codice che segue in `Sub Main`:  
  
     [!code-vb[DLinqWalk3VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#2)]  
  
2.  A questo punto premere F5 per eseguire il test dell'applicazione.  
  
     Oggetto **Console** verrà visualizzata la finestra.  
  
     Chiudere l'applicazione premendo INVIO nella **Console** finestra, oppure facendo clic **arresta debug** in Visual Studio **Debug** menu.  
  
## <a name="creating-a-new-entity"></a>Creazione di una nuova entità  
 La creazione di una nuova entità è un processo semplice. È possibile creare oggetti, ad esempio `Customer`, usando la parola chiave `New`.  
  
 In questa e nelle sezioni seguenti vengono apportate modifiche solo alla cache locale. Non viene inviata alcuna modifica al database finché, verso la fine di questa procedura dettagliata, non si chiamerà <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  
  
#### <a name="to-add-a-new-customer-entity-object"></a>Per aggiungere un nuovo oggetto dell'entità Customer  
  
1.  Creare un nuovo oggetto `Customer` aggiungendo il codice riportato di seguito prima di `Console.ReadLine` in `Sub Main`:  
  
     [!code-vb[DLinqWalk3VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#3)]  
  
2.  Premere F5 per eseguire il debug della soluzione.  
  
     Di seguito sono riportati i risultati visualizzati nella finestra della console:  
  
     `Customers matching CA before insert:`  
  
     `Customer ID: CACTU`  
  
     `Customer ID: RICAR`  
  
     Notare che la nuova riga non è visualizzata nei risultati. I nuovi dati non sono ancora stati inviati al database.  
  
3.  Premere INVIO nella **Console** finestra per arrestare il debug.  
  
## <a name="updating-an-entity"></a>Aggiornamento di un'entità  
 Nei passaggi seguenti si recupererà un oggetto `Customer` e si modificherà una delle relative proprietà.  
  
#### <a name="to-change-the-name-of-a-customer"></a>Per modificare il nome di un oggetto Customer  
  
-   Aggiungere il codice seguente sopra `Console.ReadLine()`:  
  
     [!code-vb[DLinqWalk3VB#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#4)]  
  
## <a name="deleting-an-entity"></a>Eliminazione di un'entità  
 Usando lo stesso oggetto Customer, è possibile eliminare il primo ordine.  
  
 Nel codice seguente viene illustrato come interrompere le relazioni tra le righe e come eliminare una riga dal database.  
  
#### <a name="to-delete-a-row"></a>Per eliminare una riga  
  
-   Aggiungere il codice seguente sopra `Console.ReadLine()`:  
  
     [!code-vb[DLinqWalk3VB#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#5)]  
  
## <a name="submitting-changes-to-the-database"></a>Invio di modifiche al database  
 Il passaggio finale necessario per la creazione, l'aggiornamento e l'eliminazione di oggetti consiste nell'inviare effettivamente le modifiche al database. Senza questo passaggio le modifiche vengono applicate solo localmente e non saranno visualizzate nei risultati della query.  
  
#### <a name="to-submit-changes-to-the-database"></a>Per inviare le modifiche al database  
  
1.  Inserire il codice seguente sopra `Console.ReadLine`:  
  
     [!code-vb[DLinqWalk3VB#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#6)]  
  
2.  Inserire il codice seguente dopo `SubmitChanges` per mostrare gli effetti precedenti e successivi all'invio delle modifiche:  
  
     [!code-vb[DLinqWalk3VB#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#7)]  
  
3.  Premere F5 per eseguire il debug della soluzione.  
  
     Viene visualizzata la finestra di console come segue:  
  
    ```  
    Customers matching CA before update:  
    Customer ID: CACTU  
    Customer ID: RICAR  
  
    The Order Detail to be deleted is: OrderID = 10643  
  
    Customers matching CA after update:  
    Customer ID: A3VCA  
    Customer ID: CACTU  
    Customer ID: RICAR  
    ```  
  
4.  Premere INVIO nella **Console** finestra per arrestare il debug.  
  
> [!NOTE]
>  Dopo avere aggiunto il nuovo oggetto Customer mediante l'invio delle modifiche, non sarà possibile eseguire nuovamente questa soluzione così com'è, poiché non è possibile aggiungere di nuovo lo stesso oggetto Customer. Per eseguire nuovamente la soluzione, modificare il valore dell'ID dell'oggetto Customer da aggiungere.  
  
## <a name="see-also"></a>Vedere anche

- [Apprendimento tramite procedure dettagliate](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
