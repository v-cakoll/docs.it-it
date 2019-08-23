---
title: 'Procedura: Creare un servizio di flusso di lavoro che utilizza un contratto di servizio esistente'
ms.date: 03/30/2017
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
ms.openlocfilehash: f25e71aec03f9808b3263f0353328f92888ccc69
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962309"
---
# <a name="how-to-create-a-workflow-service-that-consumes-an-existing-service-contract"></a><span data-ttu-id="43f8f-102">Procedura: Creare un servizio di flusso di lavoro che utilizza un contratto di servizio esistente</span><span class="sxs-lookup"><span data-stu-id="43f8f-102">How to: Create a workflow service that consumes an existing service contract</span></span>
<span data-ttu-id="43f8f-103">.NET Framework 4,5 offre una migliore integrazione tra i servizi Web e i flussi di lavoro sotto forma di sviluppo di flussi di lavoro di primo contratto.</span><span class="sxs-lookup"><span data-stu-id="43f8f-103">.NET Framework 4.5 features better integration between web services and workflows in the form of contract-first workflow development.</span></span> <span data-ttu-id="43f8f-104">Lo strumento di sviluppo di flussi di lavoro con priorità al contratto consente di progettare il contratto innanzitutto nel codice.</span><span class="sxs-lookup"><span data-stu-id="43f8f-104">The contract-first workflow development tool allows you to design the contract in code first.</span></span> <span data-ttu-id="43f8f-105">Lo strumento consente di generare automaticamente un modello di attività nella casella degli strumenti per le operazioni nel contratto.</span><span class="sxs-lookup"><span data-stu-id="43f8f-105">The tool then automatically generates an activity template in the toolbox for the operations in the contract.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="43f8f-106">In questo argomento viene fornito materiale sussidiario dettagliato per la creazione di un servizio del flusso di lavoro con priorità al contratto ("contract-first").</span><span class="sxs-lookup"><span data-stu-id="43f8f-106">This topic provides step-by-step guidance on creating a contract-first workflow service.</span></span> <span data-ttu-id="43f8f-107">Per ulteriori informazioni sullo sviluppo di servizi del flusso di lavoro con il primo contratto, vedere [sviluppo del servizio del flusso di lavoro](contract-first-workflow-service-development.md).</span><span class="sxs-lookup"><span data-stu-id="43f8f-107">For more information about contract-first workflow service development, see [Contract First Workflow Service Development](contract-first-workflow-service-development.md).</span></span>  
  
### <a name="creating-the-workflow-project"></a><span data-ttu-id="43f8f-108">Creazione del progetto flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="43f8f-108">Creating the workflow project</span></span>  
  
1. <span data-ttu-id="43f8f-109">In Visual Studio selezionare **file**, **nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="43f8f-109">In Visual Studio, select **File**, **New Project**.</span></span> <span data-ttu-id="43f8f-110">Selezionare il nodo **WCF** sotto il **C#** nodo nell'albero dei **modelli** e selezionare il modello **applicazione del servizio flusso di lavoro WCF** .</span><span class="sxs-lookup"><span data-stu-id="43f8f-110">Select the **WCF** node under the **C#** node in the **Templates** tree, and select the **WCF Workflow Service Application** template.</span></span>  
  
2. <span data-ttu-id="43f8f-111">Assegnare un nome al `ContractFirst` nuovo progetto e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="43f8f-111">Name the new project `ContractFirst` and click **Ok**.</span></span>  
  
### <a name="creating-the-service-contract"></a><span data-ttu-id="43f8f-112">Creazione del contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="43f8f-112">Creating the service contract</span></span>  
  
1. <span data-ttu-id="43f8f-113">Fare clic con il pulsante destro del mouse sul progetto **Esplora soluzioni** e scegliere **Aggiungi**, **nuovo elemento...** .</span><span class="sxs-lookup"><span data-stu-id="43f8f-113">Right-click the project in **Solution Explorer** and select **Add**, **New Item…**.</span></span> <span data-ttu-id="43f8f-114">Selezionare il nodo del **codice** a sinistra e il modello di **classe** a destra.</span><span class="sxs-lookup"><span data-stu-id="43f8f-114">Select the **Code** node on the left, and the **Class** template on the right.</span></span> <span data-ttu-id="43f8f-115">Assegnare un nome alla `IBookService` nuova classe e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="43f8f-115">Name the new class `IBookService` and click **Ok**.</span></span>  
  
2. <span data-ttu-id="43f8f-116">Nella parte superiore della finestra del codice visualizzata, aggiungere un'istruzione Using a `System.Servicemodel`.</span><span class="sxs-lookup"><span data-stu-id="43f8f-116">In the top of the code window that appears, add a Using statement to `System.Servicemodel`.</span></span>  
  
    ```  
    using System.ServiceModel;  
    ```  
  
3. <span data-ttu-id="43f8f-117">Modificare la definizione della classe di esempio nella definizione di interfaccia seguente.</span><span class="sxs-lookup"><span data-stu-id="43f8f-117">Change the sample class definition to the following interface definition.</span></span>  
  
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
  
4. <span data-ttu-id="43f8f-118">Compilare il progetto premendo **CTRL + MAIUSC + B**.</span><span class="sxs-lookup"><span data-stu-id="43f8f-118">Build the project by pressing **Ctrl+Shift+B**.</span></span>  
  
### <a name="importing-the-service-contract"></a><span data-ttu-id="43f8f-119">Importazione del contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="43f8f-119">Importing the service contract</span></span>  
  
1. <span data-ttu-id="43f8f-120">Fare clic con il pulsante destro del mouse sul progetto in **Esplora soluzioni** e selezionare **Importa contratto del servizio**.</span><span class="sxs-lookup"><span data-stu-id="43f8f-120">Right-click the project in **Solution Explorer** and select **Import Service Contract**.</span></span> <span data-ttu-id="43f8f-121">**In\<progetto corrente >** aprire tutti i sottonodi e selezionare **IBookService**.</span><span class="sxs-lookup"><span data-stu-id="43f8f-121">Under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="43f8f-122">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="43f8f-122">Click **OK**.</span></span>  
  
2. <span data-ttu-id="43f8f-123">Verrà visualizzata una finestra di dialogo indicante che l'operazione è stata completata correttamente e che le attività generate verranno inserite nella casella degli strumenti dopo che il progetto sarà stato compilato.</span><span class="sxs-lookup"><span data-stu-id="43f8f-123">A dialog will open, alerting you that the operation completed successfully, and that the generated activities will appear in the toolbox after you build the project.</span></span> <span data-ttu-id="43f8f-124">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="43f8f-124">Click **OK**.</span></span>  
  
3. <span data-ttu-id="43f8f-125">Compilare il progetto premendo **CTRL + MAIUSC + B**, in modo che le attività importate verranno visualizzate nella casella degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="43f8f-125">Build the project by pressing **Ctrl+Shift+B**, so that the imported activities will appear in the toolbox.</span></span>  
  
4. <span data-ttu-id="43f8f-126">In **Esplora soluzioni**Aprire Service1. xamlx.</span><span class="sxs-lookup"><span data-stu-id="43f8f-126">In **Solution Explorer**, open Service1.xamlx.</span></span> <span data-ttu-id="43f8f-127">Il servizio del flusso di lavoro verrà visualizzata nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="43f8f-127">The workflow service will appear in the designer.</span></span>  
  
5. <span data-ttu-id="43f8f-128">Selezionare l'attività **Sequence** .</span><span class="sxs-lookup"><span data-stu-id="43f8f-128">Select the **Sequence** activity.</span></span> <span data-ttu-id="43f8f-129">Nella Finestra Proprietà fare clic su **...**</span><span class="sxs-lookup"><span data-stu-id="43f8f-129">In the Properties window, click the **…**</span></span> <span data-ttu-id="43f8f-130">nella proprietà **implementedContract** .</span><span class="sxs-lookup"><span data-stu-id="43f8f-130">button in the **ImplementedContract** property.</span></span> <span data-ttu-id="43f8f-131">Nella finestra **Editor della raccolta di tipi** che viene visualizzata fare clic sull'elenco a discesa **tipo** e selezionare **Cerca tipi...**</span><span class="sxs-lookup"><span data-stu-id="43f8f-131">In the **Type Collection Editor** window that appears, click the **Type** dropdown, and select the **Browse for Types…**</span></span> <span data-ttu-id="43f8f-132">voce.</span><span class="sxs-lookup"><span data-stu-id="43f8f-132">entry.</span></span> <span data-ttu-id="43f8f-133">Nella finestra di dialogo **Cerca e seleziona un tipo .NET** ,  **\<in progetto corrente >** , aprire tutti i sottonodi e selezionare **IBookService**.</span><span class="sxs-lookup"><span data-stu-id="43f8f-133">In the **Browse and Select a .NET Type** dialog, under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="43f8f-134">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="43f8f-134">Click **OK**.</span></span> <span data-ttu-id="43f8f-135">Nella finestra di dialogo **Editor raccolta di tipi** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="43f8f-135">In the **Type Collection Editor** dialog, click **OK**.</span></span>  
  
6. <span data-ttu-id="43f8f-136">Selezionare ed eliminare le attività **ReceiveRequest** e **SendResponse** .</span><span class="sxs-lookup"><span data-stu-id="43f8f-136">Select and delete the **ReceiveRequest** and **SendResponse** activities.</span></span>  
  
7. <span data-ttu-id="43f8f-137">Dalla casella degli strumenti trascinare un **Buy_ReceiveAndSendReply** e un'attività **Checkout_Receive** nell'attività **sequenziale del servizio** .</span><span class="sxs-lookup"><span data-stu-id="43f8f-137">From the toolbox, drag a **Buy_ReceiveAndSendReply** and a **Checkout_Receive** activity onto the **Sequential Service** activity.</span></span>
