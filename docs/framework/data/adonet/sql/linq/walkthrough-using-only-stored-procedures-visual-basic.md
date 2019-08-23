---
title: 'Procedura dettagliata: Usare solo stored procedure (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: 5a736a30-ba66-4adb-b87c-57d19476e862
ms.openlocfilehash: 159b65b4b58b9142a168401ea2a881af2714df5f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946633"
---
# <a name="walkthrough-using-only-stored-procedures-visual-basic"></a>Procedura dettagliata: Usare solo stored procedure (Visual Basic)
In questa procedura dettagliata viene descritto uno scenario [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] end-to-end di base per l'accesso ai dati usando solo stored procedure. Questo approccio viene spesso è usato dagli amministratori di database per limitare l'accesso all'archivio dati.  
  
> [!NOTE]
> È inoltre possibile usare stored procedure nelle applicazioni [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per eseguire l'override del comportamento predefinito, specialmente per i processi `Create`, `Update` e `Delete`. Per ulteriori informazioni, vedere [personalizzazione di operazioni di inserimento, aggiornamento ed eliminazione](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
  
 Ai fini di questa procedura dettagliata, si utilizzeranno due metodi mappati a stored procedure nel database di esempio Northwind: CustOrdersDetail e CustOrderHist. Il mapping viene eseguito quando si esegue lo strumento da riga di comando SqlMetal per generare un file di Visual Basic. Per altre informazioni, vedere la sezione successiva relativa ai prerequisiti.  
  
 Questa procedura dettagliata non si basa sul Object Relational Designer. Gli sviluppatori che usano Visual Studio possono usare anche la finestra di progettazione relazionale oggetti per implementare stored procedure funzionalità. Vedere [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 Questa procedura dettagliata è stata scritta usando Impostazioni di sviluppo di Visual Basic.  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per l'esecuzione di questa procedura sono richiesti i seguenti elementi:  
  
- Una cartella dedicata ("c:\linqtest3") in cui inserire i file usati nella procedura dettagliata. Creare la cartella prima di avviare la procedura.  
  
- Il database di esempio Northwind.  
  
     Se questo database non è disponibile nel computer di sviluppo, è possibile scaricarlo dal sito di download Microsoft. Per istruzioni, vedere [download di database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md). Dopo avere scaricato il database, copiare il file northwnd.mdf nella cartella c:\linqtest3.  
  
- Un file di codice Visual Basic generato dal database Northwind.  
  
     Questa procedura dettagliata è stata scritta usando lo strumento SqlMetal con la riga di comando seguente:  
  
     **sqlmetal /code:"c:\linqtest3\northwind.vb" /language:vb "c:\linqtest3\northwnd.mdf" /sprocs /functions /pluralize**  
  
     Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="overview"></a>Panoramica  
 La procedura dettagliata è costituita da sei attività principali:  
  
- Configurazione della [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] soluzione in Visual Studio.  
  
- Aggiunta dell'assembly System.Data.Linq al progetto.  
  
- Aggiunta del file di codice del database al progetto.  
  
- Creazione di una connessione al database.  
  
- Impostazione dell'interfaccia utente.  
  
- Esecuzione e test dell'applicazione.  
  
## <a name="creating-a-linq-to-sql-solution"></a>Creazione di una soluzione LINQ to SQL  
 In questa prima attività viene creata una soluzione di Visual Studio che contiene i riferimenti necessari per compilare ed eseguire un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] progetto.  
  
### <a name="to-create-a-linq-to-sql-solution"></a>Per creare una soluzione LINQ to SQL  
  
1. Scegliere **Nuovo progetto** dal menu **File**di Visual Studio.  
  
2. Nel riquadro **Tipi progetto** della finestra di dialogo **Nuovo progetto** espandere **Visual Basic**, quindi fare clic su **Windows**  
  
3. Nel riquadro **Modelli** scegliere **Applicazione Windows Form**.  
  
4. Nella casella **nome** digitare **SprocOnlyApp nella**.  
  
5. Fare clic su **OK**.  
  
     Verrà aperto Progettazione Windows Form.  
  
## <a name="adding-the-linq-to-sql-assembly-reference"></a>Aggiunta del riferimento all'assembly LINQ to SQL  
 L'assembly [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non è incluso nel modello Applicazione Windows Form standard. Sarà pertanto necessario aggiungere l'assembly manualmente, come descritto nei passaggi seguenti:  
  
### <a name="to-add-systemdatalinqdll"></a>Per aggiungere System.Data.Linq.dll  
  
1. In **Esplora soluzioni**fare clic su **Mostra tutti i file**.  
  
2. In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **riferimenti**, quindi scegliere **Aggiungi riferimento**.  
  
3. Nella finestra di dialogo **Aggiungi riferimento** fare clic su **.NET**, selezionare l'assembly System. Data. Linq, quindi fare clic su **OK**.  
  
     L'assembly verrà aggiunto al progetto.  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a>Aggiunta del file di codice di Northwind al progetto  
 In questa procedura si presuppone che sia stato usato lo strumento SqlMetal per generare un file di codice dal database di esempio Northwind. Per altre informazioni, vedere la sezione precedente relativa ai prerequisiti.  
  
### <a name="to-add-the-northwind-code-file-to-the-project"></a>Per aggiungere il file di codice di Northwind al progetto  
  
1. Scegliere **Aggiungi elemento esistente**dal menu **progetto** .  
  
2. Nella finestra di dialogo **Aggiungi elemento esistente** passare a c:\linqtest3\northwind.vb e quindi fare clic su **Aggiungi**.  
  
     Il file northwind.vb viene aggiunto al progetto.  
  
## <a name="creating-a-database-connection"></a>Creazione di connessioni a database  
 In questo passaggio si definirà la connessione al database di esempio Northwind. Per questa procedura dettagliata viene usato il percorso "c:\linqtest3\northwnd.mdf".  
  
### <a name="to-create-the-database-connection"></a>Per creare la connessione al database  
  
1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **Form1. vb**, quindi scegliere **Visualizza codice**.  
  
     `Class Form1` verrà visualizzato nell'editor di codice.  
  
2. Digitare il codice riportato di seguito nel blocco di codice `Form1`.  
  
     [!code-vb[DLinqWalk4VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#1)]  
  
## <a name="setting-up-the-user-interface"></a>Impostazione dell'interfaccia utente  
 In questa attività verrà creata un'interfaccia per consentire agli utenti di eseguire stored procedure per l'accesso ai dati nel database. Nell'applicazione creata con questa procedura dettagliata gli utenti potranno accedere ai dati nel database solo usando le stored procedure incorporate nell'applicazione.  
  
### <a name="to-set-up-the-user-interface"></a>Per impostare l'interfaccia utente  
  
1. Tornare al Progettazione Windows Form (**Form1. vb [Design]** ).  
  
2. Scegliere **Casella degli strumenti** dal menu **Visualizza**.  
  
     Verrà aperta la Casella degli strumenti.  
  
    > [!NOTE]
    > Fare clic sulla puntina da disegno **Nascondi automaticamente** per mantenere aperta la casella degli strumenti mentre si eseguono i passaggi rimanenti di questa sezione.  
  
3. Trascinare due pulsanti, due caselle di testo e due etichette nella casella degli strumenti in **Form1**.  
  
     Disporre i controlli come raffigurato nell'illustrazione. Espandere **Form1** in modo che i controlli si adattano facilmente.  
  
4. Fare clic con il pulsante destro del mouse su **Label1**, quindi scegliere **Proprietà**.  
  
5. Modificare la proprietà **Text** da **Label1** in **Enter OrderID:** .  
  
6. Allo stesso modo per **Label2**, modificare la proprietà **Text** da **Label2** in **Enter CustomerID:** .  
  
7. Allo stesso modo, modificare la proprietà **Text** per **Button1** in **Order**details.  
  
8. Modificare la proprietà **Text** per **Button2** in **Order History**.  
  
     Ampliare i controlli pulsante in modo che tutto il testo sia visibile.  
  
### <a name="to-handle-button-clicks"></a>Per gestire i clic sui pulsanti  
  
1. Fare doppio clic su **Order** Details in **Form1** per creare il `Button1` gestore eventi e aprire l'editor di codice.  
  
2. Digitare il codice riportato di seguito nel gestore eventi `Button1`:  
  
     [!code-vb[DLinqWalk4VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#2)]  
  
3. A questo punto, fare doppio clic su **Button2** in `Button2` Form1 per creare il gestore eventi e aprire l'editor di codice.  
  
4. Digitare il codice riportato di seguito nel gestore eventi `Button2`:  
  
     [!code-vb[DLinqWalk4VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#3)]  
  
## <a name="testing-the-application"></a>Verifica dell'applicazione  
 A questo punto è possibile procedere al test dell'applicazione. Notare che il contatto con l'archivio dati è limitato alle azioni supportate dalle due stored procedure che, in questo caso, consistono nel restituire i prodotti inclusi per qualsiasi ID ordine immesso o nel restituire una cronologia dei prodotti ordinati per qualsiasi ID cliente immesso.  
  
### <a name="to-test-the-application"></a>Per eseguire il test dell'applicazione  
  
1. Premere F5 per avviare il debug.  
  
     Viene visualizzato Form1.  
  
2. Nella casella **Enter OrderID** Digitare **10249** , quindi fare clic su **Order**details.  
  
     I prodotti inclusi nell'ordine 10249 vengono elencati in una finestra di messaggio.  
  
     Fare clic su **OK** per chiudere la finestra di messaggio.  
  
3. Nella casella **immettere CustomerID** Digitare `ALFKI`, quindi fare clic su **Cronologia ordini**.  
  
     In una finestra di messaggio viene elencata la cronologia degli ordini per il cliente ALFKI.  
  
     Fare clic su **OK** per chiudere la finestra di messaggio.  
  
4. Nella casella **Enter OrderID** Digitare `123`, quindi fare clic su **Order**details.  
  
     Viene visualizzata una finestra di messaggio con l'indicazione che non è stato trovato alcun risultato.  
  
     Fare clic su **OK** per chiudere la finestra di messaggio.  
  
5. Scegliere **Interrompi debug**dal menu **debug** .  
  
     La sessione di debug viene chiusa.  
  
6. Se è stata completata la sperimentazione, è possibile fare clic su **Chiudi progetto** nel menu **file** e salvare il progetto quando richiesto.  
  
## <a name="next-steps"></a>Fasi successive  
 Questo progetto può essere migliorato apportandovi alcune modifiche. Ad esempio, è possibile elencare le stored procedure disponibili in una casella di riepilogo, in modo che l'utente possa selezionare quella da eseguire. È inoltre possibile trasmettere l'output dei rapporti a un file di testo.  
  
## <a name="see-also"></a>Vedere anche

- [Apprendimento tramite procedure dettagliate](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
- [stored procedure](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
