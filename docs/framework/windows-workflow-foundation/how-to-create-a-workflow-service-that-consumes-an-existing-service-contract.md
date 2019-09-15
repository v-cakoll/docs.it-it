---
title: 'Procedura: Creare un servizio di flusso di lavoro che utilizza un contratto di servizio esistente'
ms.date: 03/30/2017
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
ms.openlocfilehash: 6d7fa8c9faa84efc84243387cd27aa264f6155eb
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70989617"
---
# <a name="how-to-create-a-workflow-service-that-consumes-an-existing-service-contract"></a>Procedura: Creare un servizio di flusso di lavoro che utilizza un contratto di servizio esistente
.NET Framework 4,5 offre una migliore integrazione tra i servizi Web e i flussi di lavoro sotto forma di sviluppo di flussi di lavoro di primo contratto. Lo strumento di sviluppo di flussi di lavoro con priorità al contratto consente di progettare il contratto innanzitutto nel codice. Lo strumento consente di generare automaticamente un modello di attività nella casella degli strumenti per le operazioni nel contratto.  
  
> [!NOTE]
> In questo argomento viene fornito materiale sussidiario dettagliato per la creazione di un servizio del flusso di lavoro con priorità al contratto ("contract-first"). Per ulteriori informazioni sullo sviluppo di servizi del flusso di lavoro con il primo contratto, vedere [sviluppo del servizio del flusso di lavoro](contract-first-workflow-service-development.md).  
  
### <a name="creating-the-workflow-project"></a>Creazione del progetto flusso di lavoro  
  
1. In Visual Studio selezionare **file**, **nuovo progetto**. Selezionare il nodo **WCF** sotto il **C#** nodo nell'albero dei **modelli** e selezionare il modello **applicazione del servizio flusso di lavoro WCF** .  
  
2. Assegnare un nome al `ContractFirst` nuovo progetto e fare clic su **OK**.  
  
### <a name="creating-the-service-contract"></a>Creazione del contratto di servizio  
  
1. Fare clic con il pulsante destro del mouse sul progetto **Esplora soluzioni** e scegliere **Aggiungi**, **nuovo elemento...** . Selezionare il nodo del **codice** a sinistra e il modello di **classe** a destra. Assegnare un nome alla `IBookService` nuova classe e fare clic su **OK**.  
  
2. Nella parte superiore della finestra del codice visualizzata, aggiungere un'istruzione Using a `System.Servicemodel`.  
  
    ```csharp  
    using System.ServiceModel;  
    ```  
  
3. Modificare la definizione della classe di esempio nella definizione di interfaccia seguente.  
  
    ```csharp  
    [ServiceContract]  
        public interface IBookService  
        {  
            [OperationContract]  
            void Buy(string bookName);  
  
            [OperationContract(IsOneWay=true)]  
            void Checkout();  
        }  
    ```  
  
4. Compilare il progetto premendo **CTRL + MAIUSC + B**.  
  
### <a name="importing-the-service-contract"></a>Importazione del contratto di servizio  
  
1. Fare clic con il pulsante destro del mouse sul progetto in **Esplora soluzioni** e selezionare **Importa contratto del servizio**. **In\<progetto corrente >** aprire tutti i sottonodi e selezionare **IBookService**. Fare clic su **OK**.  
  
2. Verrà visualizzata una finestra di dialogo indicante che l'operazione è stata completata correttamente e che le attività generate verranno inserite nella casella degli strumenti dopo che il progetto sarà stato compilato. Fare clic su **OK**.  
  
3. Compilare il progetto premendo **CTRL + MAIUSC + B**, in modo che le attività importate verranno visualizzate nella casella degli strumenti.  
  
4. In **Esplora soluzioni**Aprire Service1. xamlx. Il servizio del flusso di lavoro verrà visualizzata nella finestra di progettazione.  
  
5. Selezionare l'attività **Sequence** . Nella Finestra Proprietà fare clic su **...** nella proprietà **implementedContract** . Nella finestra **Editor della raccolta di tipi** che viene visualizzata fare clic sull'elenco a discesa **tipo** e selezionare **Cerca tipi...** voce. Nella finestra di dialogo **Cerca e seleziona un tipo .NET** ,  **\<in progetto corrente >** , aprire tutti i sottonodi e selezionare **IBookService**. Fare clic su **OK**. Nella finestra di dialogo **Editor raccolta di tipi** fare clic su **OK**.  
  
6. Selezionare ed eliminare le attività **ReceiveRequest** e **SendResponse** .  
  
7. Dalla casella degli strumenti trascinare un **Buy_ReceiveAndSendReply** e un'attività **Checkout_Receive** nell'attività **sequenziale del servizio** .
