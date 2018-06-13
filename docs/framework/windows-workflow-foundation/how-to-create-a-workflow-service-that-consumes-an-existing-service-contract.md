---
title: 'Procedura: creare un servizio di flusso di lavoro che utilizza un contratto di servizio esistente'
ms.date: 03/30/2017
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
ms.openlocfilehash: 146b3bba3a880c780644eecd277827823793b5e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515305"
---
# <a name="how-to-create-a-workflow-service-that-consumes-an-existing-service-contract"></a><span data-ttu-id="041af-102">Procedura: creare un servizio di flusso di lavoro che utilizza un contratto di servizio esistente</span><span class="sxs-lookup"><span data-stu-id="041af-102">How to: Create a workflow service that consumes an existing service contract</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<span data-ttu-id="041af-103"> offre una maggiore integrazione tra i servizi Web e i flussi di lavoro sotto forma di sviluppo di flussi di lavoro con priorità al contratto.</span><span class="sxs-lookup"><span data-stu-id="041af-103"> features better integration between web services and workflows in the form of contract-first workflow development.</span></span> <span data-ttu-id="041af-104">Lo strumento di sviluppo di flussi di lavoro con priorità al contratto consente di progettare il contratto innanzitutto nel codice.</span><span class="sxs-lookup"><span data-stu-id="041af-104">The contract-first workflow development tool allows you to design the contract in code first.</span></span> <span data-ttu-id="041af-105">Lo strumento consente di generare automaticamente un modello di attività nella casella degli strumenti per le operazioni nel contratto.</span><span class="sxs-lookup"><span data-stu-id="041af-105">The tool then automatically generates an activity template in the toolbox for the operations in the contract.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="041af-106">In questo argomento viene fornito materiale sussidiario dettagliato per la creazione di un servizio del flusso di lavoro con priorità al contratto ("contract-first").</span><span class="sxs-lookup"><span data-stu-id="041af-106">This topic provides step-by-step guidance on creating a contract-first workflow service.</span></span> <span data-ttu-id="041af-107">Per ulteriori informazioni sullo sviluppo di flussi di lavoro contratto di servizio, vedere [lo sviluppo del servizio del flusso di lavoro First contratto](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md).</span><span class="sxs-lookup"><span data-stu-id="041af-107">For more information about contract-first workflow service development, see [Contract First Workflow Service Development](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md).</span></span>  
  
### <a name="creating-the-workflow-project"></a><span data-ttu-id="041af-108">Creazione del progetto flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="041af-108">Creating the workflow project</span></span>  
  
1.  <span data-ttu-id="041af-109">In Visual Studio, selezionare **File**, **nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="041af-109">In Visual Studio, select **File**, **New Project**.</span></span> <span data-ttu-id="041af-110">Selezionare il **WCF** nodo sotto il **c#** nodo il **modelli** ad albero e selezionare il **applicazione del servizio del flusso di lavoro WCF** modello.</span><span class="sxs-lookup"><span data-stu-id="041af-110">Select the **WCF** node under the **C#** node in the **Templates** tree, and select the **WCF Workflow Service Application** template.</span></span>  
  
2.  <span data-ttu-id="041af-111">Denominare il nuovo progetto `ContractFirst` e fare clic su **Ok**.</span><span class="sxs-lookup"><span data-stu-id="041af-111">Name the new project `ContractFirst` and click **Ok**.</span></span>  
  
### <a name="creating-the-service-contract"></a><span data-ttu-id="041af-112">Creazione del contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="041af-112">Creating the service contract</span></span>  
  
1.  <span data-ttu-id="041af-113">Fare clic sul progetto in **Esplora** e selezionare **Aggiungi**, **nuovo elemento...** .</span><span class="sxs-lookup"><span data-stu-id="041af-113">Right-click the project in **Solution Explorer** and select **Add**, **New Item…**.</span></span> <span data-ttu-id="041af-114">Selezionare il **codice** nodo a sinistra e **classe** modello sulla destra.</span><span class="sxs-lookup"><span data-stu-id="041af-114">Select the **Code** node on the left, and the **Class** template on the right.</span></span> <span data-ttu-id="041af-115">Denominare la nuova classe `IBookService` e fare clic su **Ok**.</span><span class="sxs-lookup"><span data-stu-id="041af-115">Name the new class `IBookService` and click **Ok**.</span></span>  
  
2.  <span data-ttu-id="041af-116">Nella parte superiore della finestra del codice visualizzata, aggiungere un'istruzione Using a `System.Servicemodel`.</span><span class="sxs-lookup"><span data-stu-id="041af-116">In the top of the code window that appears, add a Using statement to `System.Servicemodel`.</span></span>  
  
    ```  
    using System.ServiceModel;  
    ```  
  
3.  <span data-ttu-id="041af-117">Modificare la definizione della classe di esempio nella definizione di interfaccia seguente.</span><span class="sxs-lookup"><span data-stu-id="041af-117">Change the sample class definition to the following interface definition.</span></span>  
  
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
  
4.  <span data-ttu-id="041af-118">Compilare il progetto premendo **Ctrl + MAIUSC + B**.</span><span class="sxs-lookup"><span data-stu-id="041af-118">Build the project by pressing **Ctrl+Shift+B**.</span></span>  
  
### <a name="importing-the-service-contract"></a><span data-ttu-id="041af-119">Importazione del contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="041af-119">Importing the service contract</span></span>  
  
1.  <span data-ttu-id="041af-120">Fare clic sul progetto in **Esplora** e selezionare **Importa contratto del servizio**.</span><span class="sxs-lookup"><span data-stu-id="041af-120">Right-click the project in **Solution Explorer** and select **Import Service Contract**.</span></span> <span data-ttu-id="041af-121">In  **\<progetto corrente >**, aprire tutti i sottonodi e selezionare **IBookService**.</span><span class="sxs-lookup"><span data-stu-id="041af-121">Under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="041af-122">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="041af-122">Click **OK**.</span></span>  
  
2.  <span data-ttu-id="041af-123">Verrà visualizzata una finestra di dialogo indicante che l'operazione è stata completata correttamente e che le attività generate verranno inserite nella casella degli strumenti dopo che il progetto sarà stato compilato.</span><span class="sxs-lookup"><span data-stu-id="041af-123">A dialog will open, alerting you that the operation completed successfully, and that the generated activities will appear in the toolbox after you build the project.</span></span> <span data-ttu-id="041af-124">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="041af-124">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="041af-125">Compilare il progetto premendo **Ctrl + MAIUSC + B**, in modo che le attività importate saranno visualizzate nella casella degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="041af-125">Build the project by pressing **Ctrl+Shift+B**, so that the imported activities will appear in the toolbox.</span></span>  
  
4.  <span data-ttu-id="041af-126">In **Esplora**, aprire Service1. xamlx.</span><span class="sxs-lookup"><span data-stu-id="041af-126">In **Solution Explorer**, open Service1.xamlx.</span></span> <span data-ttu-id="041af-127">Il servizio del flusso di lavoro verrà visualizzata nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="041af-127">The workflow service will appear in the designer.</span></span>  
  
5.  <span data-ttu-id="041af-128">Selezionare il **sequenza** attività.</span><span class="sxs-lookup"><span data-stu-id="041af-128">Select the **Sequence** activity.</span></span> <span data-ttu-id="041af-129">Nella finestra Proprietà, fare clic sul **...**</span><span class="sxs-lookup"><span data-stu-id="041af-129">In the Properties window, click the **…**</span></span> <span data-ttu-id="041af-130">pulsante di **ImplementedContract** proprietà.</span><span class="sxs-lookup"><span data-stu-id="041af-130">button in the **ImplementedContract** property.</span></span> <span data-ttu-id="041af-131">Nel **Editor raccolta di tipi** finestra visualizzata, fare clic sui **tipo** elenco a discesa e selezionare il **Cerca tipi...**</span><span class="sxs-lookup"><span data-stu-id="041af-131">In the **Type Collection Editor** window that appears, click the **Type** dropdown, and select the **Browse for Types…**</span></span> <span data-ttu-id="041af-132">voce.</span><span class="sxs-lookup"><span data-stu-id="041af-132">entry.</span></span> <span data-ttu-id="041af-133">Nel **Cerca e seleziona .net tipo** finestra di dialogo, in  **\<progetto corrente >**, aprire tutti i sottonodi e selezionare **IBookService**.</span><span class="sxs-lookup"><span data-stu-id="041af-133">In the **Browse and Select a .Net Type** dialog, under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="041af-134">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="041af-134">Click **OK**.</span></span> <span data-ttu-id="041af-135">Nel **Editor raccolta di tipi** finestra di dialogo, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="041af-135">In the **Type Collection Editor** dialog, click **OK**.</span></span>  
  
6.  <span data-ttu-id="041af-136">Selezionare ed eliminare il **ReceiveRequest** e **SendResponse** attività.</span><span class="sxs-lookup"><span data-stu-id="041af-136">Select and delete the **ReceiveRequest** and **SendResponse** activities.</span></span>  
  
7.  <span data-ttu-id="041af-137">Dalla casella degli strumenti, trascinare un **Buy_ReceiveAndSendReply** e **Checkout_Receive** attività sul **servizio sequenziale** attività.</span><span class="sxs-lookup"><span data-stu-id="041af-137">From the toolbox, drag a **Buy_ReceiveAndSendReply** and a **Checkout_Receive** activity onto the **Sequential Service** activity.</span></span>
