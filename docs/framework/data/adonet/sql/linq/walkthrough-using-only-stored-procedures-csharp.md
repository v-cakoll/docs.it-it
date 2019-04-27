---
title: 'Procedura dettagliata: Usare solo stored procedure (C#)'
ms.date: 03/30/2017
ms.assetid: ecde4bf2-fa4d-4252-b5e4-96a46b9e097d
ms.openlocfilehash: e5497c1c6bfe032ba272c911217adaa3bd7f4f4f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61876525"
---
# <a name="walkthrough-using-only-stored-procedures-c"></a>Procedura dettagliata: Usare solo stored procedure (C#)
In questa procedura dettagliata viene descritto uno scenario [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] end-to-end di base per l'accesso ai dati eseguendo solo stored procedure. Questo approccio viene spesso è usato dagli amministratori di database per limitare l'accesso all'archivio dati.  
  
> [!NOTE]
>  È inoltre possibile usare stored procedure nelle applicazioni [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per eseguire l'override del comportamento predefinito, specialmente per i processi `Create`, `Update` e `Delete`. Per altre informazioni, vedere [personalizzazione di operazioni di inserimento, aggiornamento ed eliminare](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
  
 Ai fini di questa procedura dettagliata, si userà due metodi che sono stato eseguito il mapping alle stored procedure nel database di esempio Northwind: CustOrdersDetail e CustOrderHist. Il mapping viene applicato quando si esegue lo strumento della riga di comando SqlMetal per generare un file C#. Per altre informazioni, vedere la sezione successiva relativa ai prerequisiti.  
  
 Questa procedura dettagliata non si basa su [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]. Gli sviluppatori che usano Visual Studio consente inoltre di [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] per implementare la funzionalità delle stored procedure. Visualizzare [strumenti LINQ to SQL in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 Questa procedura è stata scritta usando Impostazioni di sviluppo di Visual C#.  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per l'esecuzione di questa procedura sono richiesti i seguenti elementi:  
  
-   Per i file usati nella procedura dettagliata viene usata una cartella dedicata ("c:\linqtest7"). Creare la cartella prima di avviare la procedura.  
  
-   Il database di esempio Northwind.  
  
     Se questo database non è disponibile nel computer di sviluppo, è possibile scaricarlo dal sito di download Microsoft. Per istruzioni, vedere [download dei database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md). Dopo avere scaricato il database, copiare il file northwnd.mdf nella cartella c:\linqtest7 .  
  
-   Un file di codice C# generato dal database Northwind.  
  
     Questa procedura dettagliata è stata scritta usando lo strumento SqlMetal con la riga di comando seguente:  
  
     **sqlmetal /code:"c:\linqtest7\northwind.cs" /language:csharp "c:\linqtest7\northwnd.mdf" /sprocs /functions /pluralize**  
  
     Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="overview"></a>Panoramica  
 La procedura dettagliata è costituita da sei attività principali:  
  
-   Configurare il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] soluzione in Visual Studio.  
  
-   Aggiunta dell'assembly System.Data.Linq al progetto.  
  
-   Aggiunta del file di codice del database al progetto.  
  
-   Creazione di una connessione con il database.  
  
-   Impostazione dell'interfaccia utente.  
  
-   Esecuzione e test dell'applicazione.  
  
## <a name="creating-a-linq-to-sql-solution"></a>Creazione di una soluzione LINQ to SQL  
 In questa prima attività, si crea una soluzione di Visual Studio che contiene i riferimenti necessari per compilare ed eseguire un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] progetto.  
  
#### <a name="to-create-a-linq-to-sql-solution"></a>Per creare una soluzione LINQ to SQL  
  
1. In Visual Studio **File** dal menu **New**, quindi fare clic su **progetto**.  
  
2. Nel **tipi di progetto** nel riquadro le **nuovo progetto** nella finestra di dialogo fare clic su **Visual C#** .  
  
3. Nel riquadro **Modelli** scegliere **Applicazione Windows Form**.  
  
4. Nel **Name** , digitare **SprocOnlyApp**.  
  
5. Nel **posizione** verificare in cui si desidera archiviare i file di progetto.  
  
6. Fare clic su **OK**.  
  
     Verrà aperto Progettazione Windows Form.  
  
## <a name="adding-the-linq-to-sql-assembly-reference"></a>Aggiunta del riferimento all'assembly LINQ to SQL  
 L'assembly [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non è incluso nel modello Applicazione Windows Form standard. Sarà pertanto necessario aggiungere l'assembly manualmente, come descritto nei passaggi seguenti:  
  
#### <a name="to-add-systemdatalinqdll"></a>Per aggiungere System.Data.Linq.dll  
  
1. Nelle **Esplora soluzioni**, fare doppio clic su **riferimenti**, quindi fare clic su **Aggiungi riferimento**.  
  
2. Nel **Aggiungi riferimento** finestra di dialogo, fare clic su **.NET**, fare clic sull'assembly e quindi fare clic su **OK**.  
  
     L'assembly verrà aggiunto al progetto.  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a>Aggiunta del file di codice di Northwind al progetto  
 In questa procedura si presuppone che sia stato usato lo strumento SqlMetal per generare un file di codice dal database di esempio Northwind. Per altre informazioni, vedere la sezione precedente relativa ai prerequisiti.  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a>Per aggiungere il file di codice di Northwind al progetto  
  
1. Nel **Project** menu, fare clic su **Aggiungi elemento esistente**.  
  
2. Nel **Aggiungi elemento esistente** finestra di dialogo, passare a c:\linqtest7\northwind.cs e quindi fare clic su **Add**.  
  
     Il file northwind.cs viene aggiunto al progetto.  
  
## <a name="creating-a-database-connection"></a>Creazione di connessioni a database  
 In questo passaggio si definirà la connessione al database di esempio Northwind. Per questa procedura dettagliata viene usato il percorso "c:\linqtest7\northwnd.mdf".  
  
#### <a name="to-create-the-database-connection"></a>Per creare la connessione al database  
  
1. Nelle **Esplora soluzioni**, fare doppio clic su **Form1.cs**, quindi fare clic su **Visualizza codice**.  
  
2. Digitare il codice riportato di seguito nella classe `Form1`.  
  
     [!code-csharp[DLinqWalk4CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#1)]  
  
## <a name="setting-up-the-user-interface"></a>Impostazione dell'interfaccia utente  
 In questa attività verrà impostata un'interfaccia per consentire agli utenti di eseguire stored procedure per l'accesso ai dati nel database. Nelle applicazioni create con questa procedura dettagliata gli utenti potranno accedere ai dati nel database solo usando le stored procedure incorporate nell'applicazione.  
  
#### <a name="to-set-up-the-user-interface"></a>Per impostare l'interfaccia utente  
  
1. Tornare a di Windows Form della finestra di progettazione (**Form1.cs[Design]**).  
  
2. Scegliere **Casella degli strumenti** dal menu **Visualizza**.  
  
     Verrà aperta la Casella degli strumenti.  
  
    > [!NOTE]
    >  Scegliere il **Nascondi automaticamente** puntina da disegno per tenere aperta la casella degli strumenti mentre si eseguono i rimanenti passaggi in questa sezione.  
  
3. Trascinare due pulsanti, due caselle di testo e due etichette dalla casella degli strumenti **Form1**.  
  
     Disporre i controlli come raffigurato nell'illustrazione. Espandere **Form1** in modo che i controlli di adattarsi con facilità.  
  
4. Fare doppio clic su **label1**, quindi fare clic su **proprietà**.  
  
5. Modifica il **testo** proprietà dal **label1** al **Enter OrderID:**.  
  
6. Nello stesso modo per **label2**, modificare il **testo** proprietà dal **label2** al **Enter CustomerID:**.  
  
7. Nello stesso modo, modificare il **testo** proprietà per **button1** al **Order Details**.  
  
8. Modifica il **testo** proprietà per **button2** al **Order History**.  
  
     Ampliare i controlli pulsante in modo che tutto il testo sia visibile.  
  
#### <a name="to-handle-button-clicks"></a>Per gestire i clic sui pulsanti  
  
1. Fare doppio clic su **Order Details** sul **Form1** per aprire il gestore eventi button1 nell'editor del codice.  
  
2. Digitare il codice riportato di seguito nel gestore eventi `button1`:  
  
     [!code-csharp[DLinqWalk4CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#2)]  
  
3. A questo punto fare doppio clic su **button2** sul **Form1** per aprire la `button2` gestore  
  
4. Digitare il codice riportato di seguito nel gestore eventi `button2`:  
  
     [!code-csharp[DLinqWalk4CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#3)]  
  
## <a name="testing-the-application"></a>Verifica dell'applicazione  
 A questo punto è possibile procedere al test dell'applicazione. Notare che il contatto con l'archivio dati è limitato alle azioni supportate dalle due stored procedure che, in questo caso, consistono nel restituire i prodotti inclusi per qualsiasi ID ordine immesso o nel restituire una cronologia dei prodotti ordinati per qualsiasi ID cliente immesso.  
  
#### <a name="to-test-the-application"></a>Per eseguire il test dell'applicazione  
  
1. Premere F5 per avviare il debug.  
  
     Viene visualizzato Form1.  
  
2. Nel **Enter OrderID** , digitare `10249`, quindi fare clic su **Order Details**.  
  
     I prodotti inclusi nell'ordine 10249 vengono elencati in una finestra di messaggio.  
  
     Fare clic su **OK** per chiudere la finestra di messaggio.  
  
3. Nel **Enter CustomerID** , digitare `ALFKI`, quindi fare clic su **Order History**.  
  
     Viene visualizzata una finestra di messaggio con l'elenco della cronologia degli ordini per il cliente ALFKI.  
  
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
