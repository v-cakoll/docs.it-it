---
title: 'Procedura dettagliata: Usare solo stored procedure (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: 5a736a30-ba66-4adb-b87c-57d19476e862
ms.openlocfilehash: 22db347afb45b981602d5a92516271f75b8e4359
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648684"
---
# <a name="walkthrough-using-only-stored-procedures-visual-basic"></a>Procedura dettagliata: Usare solo stored procedure (Visual Basic)
In questa procedura dettagliata viene descritto uno scenario [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] end-to-end di base per l'accesso ai dati usando solo stored procedure. Questo approccio viene spesso è usato dagli amministratori di database per limitare l'accesso all'archivio dati.  
  
> [!NOTE]
>  È inoltre possibile usare stored procedure nelle applicazioni [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per eseguire l'override del comportamento predefinito, specialmente per i processi `Create`, `Update` e `Delete`. Per altre informazioni, vedere [personalizzazione di operazioni di inserimento, aggiornamento ed eliminare](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
  
 Ai fini di questa procedura dettagliata, si userà due metodi che sono stato eseguito il mapping alle stored procedure nel database di esempio Northwind: CustOrdersDetail e CustOrderHist. Il mapping si verifica quando si esegue lo strumento da riga di comando SqlMetal per generare un file di Visual Basic. Per altre informazioni, vedere la sezione successiva relativa ai prerequisiti.  
  
 Questa procedura dettagliata non si basa su [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]. Gli sviluppatori che usano Visual Studio consente inoltre di [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] per implementare la funzionalità delle stored procedure. Visualizzare [strumenti LINQ to SQL in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 Questa procedura dettagliata è stata scritta usando Impostazioni di sviluppo di Visual Basic.  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per l'esecuzione di questa procedura sono richiesti i seguenti elementi:  
  
- Una cartella dedicata ("c:\linqtest3") in cui inserire i file usati nella procedura dettagliata. Creare la cartella prima di avviare la procedura.  
  
- Il database di esempio Northwind.  
  
     Se questo database non è disponibile nel computer di sviluppo, è possibile scaricarlo dal sito di download Microsoft. Per istruzioni, vedere [download dei database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md). Dopo avere scaricato il database, copiare il file northwnd.mdf nella cartella c:\linqtest3.  
  
- Un file di codice Visual Basic generato dal database Northwind.  
  
     Questa procedura dettagliata è stata scritta usando lo strumento SqlMetal con la riga di comando seguente:  
  
     **sqlmetal /code:"c:\linqtest3\northwind.vb" /language:vb "c:\linqtest3\northwnd.mdf" /sprocs /functions /pluralize**  
  
     Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="overview"></a>Panoramica  
 La procedura dettagliata è costituita da sei attività principali:  
  
- Configurare il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] soluzione in Visual Studio.  
  
- Aggiunta dell'assembly System.Data.Linq al progetto.  
  
- Aggiunta del file di codice del database al progetto.  
  
- Creazione di una connessione al database.  
  
- Impostazione dell'interfaccia utente.  
  
- Esecuzione e test dell'applicazione.  
  
## <a name="creating-a-linq-to-sql-solution"></a>Creazione di una soluzione LINQ to SQL  
 In questa prima attività, si crea una soluzione di Visual Studio che contiene i riferimenti necessari per compilare ed eseguire un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] progetto.  
  
#### <a name="to-create-a-linq-to-sql-solution"></a>Per creare una soluzione LINQ to SQL  
  
1. Scegliere **Nuovo progetto** dal menu **File**di Visual Studio.  
  
2. Nel riquadro **Tipi progetto** della finestra di dialogo **Nuovo progetto** espandere **Visual Basic**, quindi fare clic su **Windows**  
  
3. Nel riquadro **Modelli** scegliere **Applicazione Windows Form**.  
  
4. Nel **Name** , digitare **SprocOnlyApp**.  
  
5. Fare clic su **OK**.  
  
     Verrà aperto Progettazione Windows Form.  
  
## <a name="adding-the-linq-to-sql-assembly-reference"></a>Aggiunta del riferimento all'assembly LINQ to SQL  
 L'assembly [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non è incluso nel modello Applicazione Windows Form standard. Sarà pertanto necessario aggiungere l'assembly manualmente, come descritto nei passaggi seguenti:  
  
#### <a name="to-add-systemdatalinqdll"></a>Per aggiungere System.Data.Linq.dll  
  
1. Nelle **Esplora soluzioni**, fare clic su **Mostra tutti i file**.  
  
2. Nelle **Esplora soluzioni**, fare doppio clic su **riferimenti**, quindi fare clic su **Aggiungi riferimento**.  
  
3. Nel **Aggiungi riferimento** finestra di dialogo, fare clic su **.NET**, fare clic sull'assembly e quindi fare clic su **OK**.  
  
     L'assembly verrà aggiunto al progetto.  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a>Aggiunta del file di codice di Northwind al progetto  
 In questa procedura si presuppone che sia stato usato lo strumento SqlMetal per generare un file di codice dal database di esempio Northwind. Per altre informazioni, vedere la sezione precedente relativa ai prerequisiti.  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a>Per aggiungere il file di codice di Northwind al progetto  
  
1. Nel **Project** menu, fare clic su **Aggiungi elemento esistente**.  
  
2. Nel **Aggiungi elemento esistente** finestra di dialogo, passare a c:\linqtest3\northwind.vb e quindi fare clic su **Add**.  
  
     Il file northwind.vb viene aggiunto al progetto.  
  
## <a name="creating-a-database-connection"></a>Creazione di connessioni a database  
 In questo passaggio si definirà la connessione al database di esempio Northwind. Per questa procedura dettagliata viene usato il percorso "c:\linqtest3\northwnd.mdf".  
  
#### <a name="to-create-the-database-connection"></a>Per creare la connessione al database  
  
1. Nelle **Esplora soluzioni**, fare doppio clic su **Form1.vb**, quindi fare clic su **Visualizza codice**.  
  
     `Class Form1` verrà visualizzato nell'editor di codice.  
  
2. Digitare il codice riportato di seguito nel blocco di codice `Form1`.  
  
     [!code-vb[DLinqWalk4VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#1)]  
  
## <a name="setting-up-the-user-interface"></a>Impostazione dell'interfaccia utente  
 In questa attività verrà creata un'interfaccia per consentire agli utenti di eseguire stored procedure per l'accesso ai dati nel database. Nell'applicazione creata con questa procedura dettagliata gli utenti potranno accedere ai dati nel database solo usando le stored procedure incorporate nell'applicazione.  
  
#### <a name="to-set-up-the-user-interface"></a>Per impostare l'interfaccia utente  
  
1. Tornare a di Windows Form della finestra di progettazione (**Form1.vb]**).  
  
2. Scegliere **Casella degli strumenti** dal menu **Visualizza**.  
  
     Verrà aperta la Casella degli strumenti.  
  
    > [!NOTE]
    >  Scegliere il **Nascondi automaticamente** puntina da disegno per tenere aperta la casella degli strumenti mentre si eseguono i rimanenti passaggi in questa sezione.  
  
3. Trascinare due pulsanti, due caselle di testo e due etichette dalla casella degli strumenti **Form1**.  
  
     Disporre i controlli come raffigurato nell'illustrazione. Espandere **Form1** in modo che i controlli di adattarsi con facilità.  
  
4. Fare doppio clic su **Label1**, quindi fare clic su **proprietà**.  
  
5. Modifica il **testo** proprietà dal **Label1** al **Enter OrderID:**.  
  
6. Nello stesso modo per **Label2**, modificare il **testo** proprietà dal **Label2** al **Enter CustomerID:**.  
  
7. Nello stesso modo, modificare il **testo** proprietà per **Button1** al **Order Details**.  
  
8. Modifica il **testo** proprietà per **Button2** al **Order History**.  
  
     Ampliare i controlli pulsante in modo che tutto il testo sia visibile.  
  
#### <a name="to-handle-button-clicks"></a>Per gestire i clic sui pulsanti  
  
1. Fare doppio clic su **Order Details** sul **Form1** per creare il `Button1` gestore eventi e aprire l'editor di codice.  
  
2. Digitare il codice riportato di seguito nel gestore eventi `Button1`:  
  
     [!code-vb[DLinqWalk4VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#2)]  
  
3. A questo punto fare doppio clic su **Button2** su Form1 per creare il `Button2` gestore eventi e aprire l'editor di codice.  
  
4. Digitare il codice riportato di seguito nel gestore eventi `Button2`:  
  
     [!code-vb[DLinqWalk4VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#3)]  
  
## <a name="testing-the-application"></a>Verifica dell'applicazione  
 A questo punto è possibile procedere al test dell'applicazione. Notare che il contatto con l'archivio dati è limitato alle azioni supportate dalle due stored procedure che, in questo caso, consistono nel restituire i prodotti inclusi per qualsiasi ID ordine immesso o nel restituire una cronologia dei prodotti ordinati per qualsiasi ID cliente immesso.  
  
#### <a name="to-test-the-application"></a>Per eseguire il test dell'applicazione  
  
1. Premere F5 per avviare il debug.  
  
     Viene visualizzato Form1.  
  
2. Nel **Enter OrderID** , digitare **10249** e quindi fare clic su **Order Details**.  
  
     I prodotti inclusi nell'ordine 10249 vengono elencati in una finestra di messaggio.  
  
     Fare clic su **OK** per chiudere la finestra di messaggio.  
  
3. Nel **Enter CustomerID** , digitare `ALFKI`, quindi fare clic su **Order History**.  
  
     In una finestra di messaggio viene elencata la cronologia degli ordini per il cliente ALFKI.  
  
     Fare clic su **OK** per chiudere la finestra di messaggio.  
  
4. Nel **Enter OrderID** , digitare `123`, quindi fare clic su **Order Details**.  
  
     Viene visualizzata una finestra di messaggio con l'indicazione che non è stato trovato alcun risultato.  
  
     Fare clic su **OK** per chiudere la finestra di messaggio.  
  
5. Nel **Debug** menu, fare clic su **arrestare il debug**.  
  
     La sessione di debug viene chiusa.  
  
6. Se si al termine delle prove, è possibile fare clic su **Chiudi progetto** nel **File** menu e salvare il progetto quando viene richiesto.  
  
## <a name="next-steps"></a>Passaggi successivi  
 Questo progetto può essere migliorato apportandovi alcune modifiche. Ad esempio, è possibile elencare le stored procedure disponibili in una casella di riepilogo, in modo che l'utente possa selezionare quella da eseguire. È inoltre possibile trasmettere l'output dei rapporti a un file di testo.  
  
## <a name="see-also"></a>Vedere anche

- [Apprendimento tramite procedure dettagliate](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
- [stored procedure](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
