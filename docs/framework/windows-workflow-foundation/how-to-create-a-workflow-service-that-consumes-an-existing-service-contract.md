---
title: 'Procedura: Creare un servizio del flusso di lavoro che utilizza un contratto di servizio esistente'
ms.date: 03/30/2017
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
ms.openlocfilehash: 06d4d4f6687979f4fd54e919ca6f236a5b5402e8
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2019
ms.locfileid: "57843008"
---
# <a name="how-to-create-a-workflow-service-that-consumes-an-existing-service-contract"></a>Procedura: Creare un servizio del flusso di lavoro che utilizza un contratto di servizio esistente
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] offre una maggiore integrazione tra i servizi Web e i flussi di lavoro sotto forma di sviluppo di flussi di lavoro con priorità al contratto. Lo strumento di sviluppo di flussi di lavoro con priorità al contratto consente di progettare il contratto innanzitutto nel codice. Lo strumento consente di generare automaticamente un modello di attività nella casella degli strumenti per le operazioni nel contratto.  
  
> [!NOTE]
>  In questo argomento viene fornito materiale sussidiario dettagliato per la creazione di un servizio del flusso di lavoro con priorità al contratto ("contract-first"). Per altre informazioni sullo sviluppo di flussi di lavoro contratto di servizio, vedere [sviluppo del servizio del flusso di lavoro prima Contract](contract-first-workflow-service-development.md).  
  
### <a name="creating-the-workflow-project"></a>Creazione del progetto flusso di lavoro  
  
1.  In Visual Studio, selezionare **File**, **nuovo progetto**. Selezionare il **WCF** nodo sotto il **C#** nodo il **modelli** della struttura ad albero e selezionare il **applicazione del servizio del flusso di lavoro WCF** modello.  
  
2.  Denominare il nuovo progetto `ContractFirst` e fare clic su **accettabile**.  
  
### <a name="creating-the-service-contract"></a>Creazione del contratto di servizio  
  
1.  Fare clic sul progetto in **Esplora soluzioni** e selezionare **Add**, **nuovo elemento...** . Selezionare il **codice** nodo a sinistra e il **classe** modello sul lato destro. Denominare la nuova classe `IBookService` e fare clic su **accettabile**.  
  
2.  Nella parte superiore della finestra del codice visualizzata, aggiungere un'istruzione Using a `System.Servicemodel`.  
  
    ```  
    using System.ServiceModel;  
    ```  
  
3.  Modificare la definizione della classe di esempio nella definizione di interfaccia seguente.  
  
    ```  
    [ServiceContract]  
        public interface IBookService  
        {  
            [OperationContract]  
            void Buy(string bookName);  
  
            [OperationContract(IsOneWay=true)]  
            void Checkout();  
        }  
    ```  
  
4.  Compilare il progetto premendo **Ctrl + MAIUSC + B**.  
  
### <a name="importing-the-service-contract"></a>Importazione del contratto di servizio  
  
1.  Fare clic sul progetto in **Esplora soluzioni** e selezionare **Importa contratto del servizio**. Sotto  **\<progetto corrente >**, aprire tutti i sottonodi e selezionare **IBookService**. Fare clic su **OK**.  
  
2.  Verrà visualizzata una finestra di dialogo indicante che l'operazione è stata completata correttamente e che le attività generate verranno inserite nella casella degli strumenti dopo che il progetto sarà stato compilato. Fare clic su **OK**.  
  
3.  Compilare il progetto premendo **Ctrl + MAIUSC + B**, in modo che le attività importate saranno visualizzate nella casella degli strumenti.  
  
4.  Nelle **Esplora soluzioni**, aprire il file Service1.xamlx. Il servizio del flusso di lavoro verrà visualizzata nella finestra di progettazione.  
  
5.  Selezionare il **sequenza** attività. Nella finestra Proprietà, fare clic su di **...** pulsante di **ImplementedContract** proprietà. Nel **Editor raccolta di tipi** finestra visualizzata, fare clic sui **tipo** elenco a discesa e selezionare il **Cerca tipi...** voce. Nel **individuare e selezionare un tipo .NET** finestra di dialogo, sotto  **\<progetto corrente >**, aprire tutti i sottonodi e selezionare **IBookService**. Fare clic su **OK**. Nel **Editor raccolta di tipi** finestra di dialogo, fare clic su **OK**.  
  
6.  Selezionare ed eliminare le **ReceiveRequest** e **SendResponse** attività.  
  
7.  Dalla casella degli strumenti, trascinare un **Buy_ReceiveAndSendReply** e una **Checkout_Receive** attività sul **Sequential Service** attività.
