---
title: 'Procedura: creare un servizio flusso di lavoro che chiama un altro servizio flusso di lavoro'
ms.date: 03/30/2017
ms.assetid: 99b3ee3e-aeb7-4e6f-8321-60fe6140eb67
ms.openlocfilehash: fda5a7286c3d20c7cdc2093e58bfe3fbdcf1d1c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33497191"
---
# <a name="how-to-create-a-workflow-service-that-calls-another-workflow-service"></a><span data-ttu-id="87350-102">Procedura: creare un servizio flusso di lavoro che chiama un altro servizio flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="87350-102">How to: Create a Workflow Service That Calls Another Workflow Service</span></span>
<span data-ttu-id="87350-103">Per un servizio di flusso di lavoro è talvolta necessario ottenere informazioni da un altro servizio analogo.</span><span class="sxs-lookup"><span data-stu-id="87350-103">It is sometimes necessary for a workflow service to obtain information from another workflow service.</span></span>  <span data-ttu-id="87350-104">In questo argomento viene illustrato come eseguire chiamate tra servizi di flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="87350-104">This topic demonstrates how to call one workflow service from another.</span></span> <span data-ttu-id="87350-105">Verranno creati due servizi di flusso di lavoro: uno che dispone di un metodo che inverte la stringa di input e l'altro che converte la stringa di input in caratteri maiuscoli dopo aver invertito la stringa utilizzata dal primo servizio.</span><span class="sxs-lookup"><span data-stu-id="87350-105">In this topic, we’ll create two workflow services; one that has a method that reverses the input string, and another that converts the input string to uppercase after reversing the string that uses the first service.</span></span>  
  
### <a name="to-create-the-reverser-workflow-service"></a><span data-ttu-id="87350-106">Per creare il servizio di flusso di lavoro che esegue l'inversione</span><span class="sxs-lookup"><span data-stu-id="87350-106">To create the Reverser workflow service</span></span>  
  
1.  <span data-ttu-id="87350-107">Eseguire [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] come amministratore.</span><span class="sxs-lookup"><span data-stu-id="87350-107">Run [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] as an administrator.</span></span>  
  
2.  <span data-ttu-id="87350-108">Selezionare **File**, **nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="87350-108">Select **File**, **New Project**.</span></span> <span data-ttu-id="87350-109">Sotto il **flusso di lavoro** nodo il **modelli installati** riquadro, selezionare **applicazione del servizio del flusso di lavoro WCF**.</span><span class="sxs-lookup"><span data-stu-id="87350-109">Under the **Workflow** node in the **Installed Templates** pane, select **WCF Workflow Service Application**.</span></span> <span data-ttu-id="87350-110">Denominare la soluzione `NestedServices` e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="87350-110">Name the solution `NestedServices` and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="87350-111">In **server**, assicurarsi che **Usa Server Web IIS locale** è selezionata.</span><span class="sxs-lookup"><span data-stu-id="87350-111">Under **Servers**, make sure that **Use Local IIS Web Server** is selected.</span></span> <span data-ttu-id="87350-112">Fare clic su **crea Directory virtuale**.</span><span class="sxs-lookup"><span data-stu-id="87350-112">Click **Create Virtual Directory**.</span></span> <span data-ttu-id="87350-113">Fare clic su **OK** nella finestra di dialogo Conferma che la directory virtuale è stata creata.</span><span class="sxs-lookup"><span data-stu-id="87350-113">Click **OK** in the dialog box stating that the virtual directory was successfully created.</span></span>  
  
4.  <span data-ttu-id="87350-114">In Esplora soluzioni rinominare Service1. xamlx in `StringReverserService.xamlx`.</span><span class="sxs-lookup"><span data-stu-id="87350-114">In Solution Explorer, rename Service1.xamlx to `StringReverserService.xamlx`.</span></span>  
  
5.  <span data-ttu-id="87350-115">Nel **le proprietà del progetto** pagina per il nuovo progetto, fare clic su di **Web** scheda. Impostare il **azione di avvio** a **pagina specifica**e selezionare stringreverserservice. Xamlx come pagina di avvio.</span><span class="sxs-lookup"><span data-stu-id="87350-115">On the **Project Properties** page for the new project, click the **Web** tab. Set the **Start Action** to **Specific Page**, and select StringReverserService.xamlx as the page to start.</span></span>  
  
6.  <span data-ttu-id="87350-116">Aprire StringReverserService.xamlx nella finestra di progettazione, eliminare le attività `ReceiveRequest` e `SendReply` esistenti, quindi trascinare un'attività `ReceiveAndSendReply` nell'attività Sequence esistente.</span><span class="sxs-lookup"><span data-stu-id="87350-116">Open StringReverserService.xamlx in the designer and delete the existing `ReceiveRequest` and `SendReply` activities, and then drag a `ReceiveAndSendReply` activity into the existing sequence activity.</span></span>  
  
    1.  <span data-ttu-id="87350-117">Impostare il **OperationName** su ReverseString.</span><span class="sxs-lookup"><span data-stu-id="87350-117">Set the **OperationName** to ReverseString.</span></span>  
  
    2.  <span data-ttu-id="87350-118">Impostare il **ServiceContractName** su IReverseString.</span><span class="sxs-lookup"><span data-stu-id="87350-118">Set the **ServiceContractName** to IReverseString.</span></span>  
  
    3.  <span data-ttu-id="87350-119">Selezionare il **CanCreateInstance** casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="87350-119">Select the **CanCreateInstance** check box.</span></span>  
  
7.  <span data-ttu-id="87350-120">Selezionare il **SequentialService** attività e quindi scegliere il **variabili** scheda nella parte inferiore della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="87350-120">Select the **SequentialService** activity, and then click the **Variables** tab at the bottom of the designer.</span></span> <span data-ttu-id="87350-121">Creare due nuove variabili di tipo String denominate StringToReverse e ReversedStringToReturn.</span><span class="sxs-lookup"><span data-stu-id="87350-121">Create two new variables named StringToReverse and ReversedStringToReturn of type String.</span></span>  
  
8.  <span data-ttu-id="87350-122">Fare clic su di **definire** collegare il **ricezione** attività.</span><span class="sxs-lookup"><span data-stu-id="87350-122">Click the **Define** link in the **Receive** activity.</span></span> <span data-ttu-id="87350-123">Fare clic su di **parametri**, quindi creare un parametro denominato InputString di tipo String da assegnare a StringToReverse.</span><span class="sxs-lookup"><span data-stu-id="87350-123">Click the  **Parameters**, and create a parameter named InputString of type String that assigns to StringToReverse.</span></span>  
  
9. <span data-ttu-id="87350-124">Fare clic su di **Definisci** collegare il **SendReplyToReceive** attività.</span><span class="sxs-lookup"><span data-stu-id="87350-124">Click the **Define** link in the **SendReplyToReceive** activity.</span></span> <span data-ttu-id="87350-125">Fare clic su di **parametri**, quindi creare un parametro denominato ReversedString di tipo String assegnato a ReversedStringToReturn.</span><span class="sxs-lookup"><span data-stu-id="87350-125">Click the **Parameters**, and create a parameter named ReversedString of type String, assigned to ReversedStringToReturn.</span></span>  
  
10. <span data-ttu-id="87350-126">Per implementare la logica per il servizio, creare una nuova classe nel progetto denominata StringLibrary.</span><span class="sxs-lookup"><span data-stu-id="87350-126">To implement the logic for the service, create a new class in the project called StringLibrary.</span></span>  <span data-ttu-id="87350-127">Sostituire la definizione della classe con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="87350-127">Replace the class definition with the following code.</span></span>  
  
    ```  
    public class StringLibrary  
        {  
            public static String ReverseString(string StringToReverse)  
            {  
                char[] charArray = StringToReverse.ToCharArray();  
                Array.Reverse(charArray);  
                return new String(charArray);  
            }  
        }  
    ```  
  
11. <span data-ttu-id="87350-128">Per chiamare il metodo ReverseString sull'input, trascinare un **InvokeMethod** attività dalla casella degli strumenti per lo spazio tra il **ricezione** e **SendReply** le attività.</span><span class="sxs-lookup"><span data-stu-id="87350-128">To call the ReverseString method on the input, drag an **InvokeMethod** activity from the toolbox to the space between the **Receive** and **SendReply** activities.</span></span> <span data-ttu-id="87350-129">Impostare le proprietà dell'attività come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="87350-129">Set the properties of the activity as follows:</span></span>  
  
    1.  <span data-ttu-id="87350-130">**NomeMetodo**: ReverseString</span><span class="sxs-lookup"><span data-stu-id="87350-130">**MethodName**: ReverseString</span></span>  
  
    2.  <span data-ttu-id="87350-131">**Risultato**: ReversedStringToReturn</span><span class="sxs-lookup"><span data-stu-id="87350-131">**Result**: ReversedStringToReturn</span></span>  
  
    3.  <span data-ttu-id="87350-132">**I parametri**: creare un nuovo parametro con un **direzione** di In, una **tipo** della stringa e una **valore** stringtoreverse.</span><span class="sxs-lookup"><span data-stu-id="87350-132">**Parameters**: Create a new parameter with a **Direction** of In, a **Type** of String, and a **Value** of StringToReverse.</span></span>  
  
    4.  <span data-ttu-id="87350-133">**TargetType**: NestedServices.StringLibrary</span><span class="sxs-lookup"><span data-stu-id="87350-133">**TargetType**: NestedServices.StringLibrary</span></span>  
  
12. <span data-ttu-id="87350-134">Premere F5 per testare il servizio.</span><span class="sxs-lookup"><span data-stu-id="87350-134">Test the service by pressing F5.</span></span> <span data-ttu-id="87350-135">Nel client di test WCF visualizzato fare doppio clic sul metodo ReverseString().</span><span class="sxs-lookup"><span data-stu-id="87350-135">In the WCF Test Client that appears, double-click the ReverseString() method.</span></span> <span data-ttu-id="87350-136">Nel riquadro della richiesta, immettere `Sample` per il valore del parametro InputString.</span><span class="sxs-lookup"><span data-stu-id="87350-136">In the Request pane, enter `Sample` for the Value of the InputString parameter.</span></span> <span data-ttu-id="87350-137">Fare clic su **richiamare**.</span><span class="sxs-lookup"><span data-stu-id="87350-137">Click **Invoke**.</span></span> <span data-ttu-id="87350-138">Il servizio deve restituire "elpmaS".</span><span class="sxs-lookup"><span data-stu-id="87350-138">The service should return "elpmaS".</span></span>  
  
### <a name="to-create-the-uppercaser-workflow-service"></a><span data-ttu-id="87350-139">Per creare il servizio di flusso di lavoro che esegue la conversione in caratteri maiuscoli</span><span class="sxs-lookup"><span data-stu-id="87350-139">To create the UpperCaser workflow service</span></span>  
  
1.  <span data-ttu-id="87350-140">Fare clic sul progetto NestedServices e selezionare **Aggiungi**, **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="87350-140">Right-click the NestedServices project and select **Add**, **New Item**.</span></span> <span data-ttu-id="87350-141">Nel **flusso di lavoro** nodo, seleziona **servizio flusso di lavoro WCF**e il nome del nuovo servizio `UpperCaserService`.</span><span class="sxs-lookup"><span data-stu-id="87350-141">In the **Workflow** node, select **WCF Workflow Service**, and name the new service `UpperCaserService`.</span></span> <span data-ttu-id="87350-142">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="87350-142">Click **Add**.</span></span> <span data-ttu-id="87350-143">Un nuovo servizio di flusso di lavoro denominato UpperCaserService.xamlx verrà aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="87350-143">This should add a new workflow service called UpperCaserService.xamlx to the project.</span></span>  
  
2.  <span data-ttu-id="87350-144">Aprire Uppercaserservice nella finestra di progettazione e di eliminare quello esistente **ReceiveRequest** e `SendReply` attività e trascinare un `ReceiveAndSendReply` attività nell'attività sequence esistente.</span><span class="sxs-lookup"><span data-stu-id="87350-144">Open UpperCaserService.xamlx in the designer and delete the existing **ReceiveRequest** and `SendReply` activities, and drag a `ReceiveAndSendReply` activity into the existing sequence activity.</span></span>  
  
    1.  <span data-ttu-id="87350-145">Impostare il **OperationName** su UpperCaseString.</span><span class="sxs-lookup"><span data-stu-id="87350-145">Set the **OperationName** to UpperCaseString.</span></span>  
  
    2.  <span data-ttu-id="87350-146">Impostare il **ServiceContractName** su IUpperCaseString.</span><span class="sxs-lookup"><span data-stu-id="87350-146">Set the **ServiceContractName** to IUpperCaseString.</span></span>  
  
    3.  <span data-ttu-id="87350-147">Selezionare il **CanCreateInstance** casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="87350-147">Select the **CanCreateInstance** check box.</span></span>  
  
3.  <span data-ttu-id="87350-148">Selezionare l'attività SequentialService e quindi fare clic su di **variabili** scheda nella parte inferiore della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="87350-148">Select the SequentialService activity, and then click the **Variables** tab at the bottom of the designer.</span></span> <span data-ttu-id="87350-149">Creare tre nuove variabili di tipo String, denominate StringToUpper, StringToReverse e StringToReturn.</span><span class="sxs-lookup"><span data-stu-id="87350-149">Create three new variables named StringToUpper, StringToReverse, and StringToReturn of type String.</span></span>  
  
4.  <span data-ttu-id="87350-150">Fare clic su di **definire** collegare il **ricezione** attività.</span><span class="sxs-lookup"><span data-stu-id="87350-150">Click the **Define** link in the **Receive** activity.</span></span> <span data-ttu-id="87350-151">Fare clic su di **parametri**, quindi creare un parametro denominato InputString di tipo String da assegnare a StringToUpper.</span><span class="sxs-lookup"><span data-stu-id="87350-151">Click the **Parameters**, and create a parameter named InputString of type String that assigns to StringToUpper.</span></span>  
  
5.  <span data-ttu-id="87350-152">Fare clic su di **Definisci** collegare il **SendReplyToReceive** attività.</span><span class="sxs-lookup"><span data-stu-id="87350-152">Click the **Define** link in the **SendReplyToReceive** activity.</span></span> <span data-ttu-id="87350-153">Fare clic su di **parametri**, quindi creare un parametro denominato ModifiedString di tipo String assegnato a StringToReturn.</span><span class="sxs-lookup"><span data-stu-id="87350-153">Click the **Parameters**, and create a parameter named ModifiedString of type String, assigned to StringToReturn.</span></span>  
  
6.  <span data-ttu-id="87350-154">Per implementare la logica per il servizio, creare un nuovo metodo nella classe StringLibrary tramite il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="87350-154">To implement the logic for the service, create a new method in the StringLibrary class using the following code.</span></span>  
  
    ```  
    public static String UpperCaseString(string StringToUpperCase)  
    {  
         return StringToUpperCase.ToUpper();  
  
    }  
    ```  
  
7.  <span data-ttu-id="87350-155">Per chiamare il metodo UpperCaseString sull'input, trascinare un **InvokeMethod** attività dalla casella degli strumenti per lo spazio tra il **ricezione** e **SendReply** le attività.</span><span class="sxs-lookup"><span data-stu-id="87350-155">To call the UpperCaseString method on the input, drag an **InvokeMethod** activity from the toolbox to the space between the **Receive** and **SendReply** activities.</span></span> <span data-ttu-id="87350-156">Impostare le proprietà dell'attività come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="87350-156">Set the properties of the activity as follows:</span></span>  
  
    1.  <span data-ttu-id="87350-157">**NomeMetodo**: UpperCaseString</span><span class="sxs-lookup"><span data-stu-id="87350-157">**MethodName**: UpperCaseString</span></span>  
  
    2.  <span data-ttu-id="87350-158">**Risultato**: StringToReverse</span><span class="sxs-lookup"><span data-stu-id="87350-158">**Result**: StringToReverse</span></span>  
  
    3.  <span data-ttu-id="87350-159">**I parametri**: creare un nuovo parametro con un **direzione** di In, una **tipo** della stringa e una **valore** stringtoupper.</span><span class="sxs-lookup"><span data-stu-id="87350-159">**Parameters**: Create a new parameter with a **Direction** of In, a **Type** of String, and a **Value** of StringToUpper.</span></span>  
  
    4.  <span data-ttu-id="87350-160">**TargetType**: NestedServices.StringLibrary</span><span class="sxs-lookup"><span data-stu-id="87350-160">**TargetType**: NestedServices.StringLibrary</span></span>  
  
8.  <span data-ttu-id="87350-161">A questo punto verrà chiamato il primo servizio sulla stringa modificata.</span><span class="sxs-lookup"><span data-stu-id="87350-161">We’ll now call the first service on the modified string.</span></span> <span data-ttu-id="87350-162">Fare clic sul progetto e selezionare **Aggiungi riferimento al servizio**.</span><span class="sxs-lookup"><span data-stu-id="87350-162">Right-click the project and select **Add Service Reference**.</span></span> <span data-ttu-id="87350-163">Aggiungere un riferimento al servizio su http://localhost/NestedServices/StringReverserService.xamlx . sln e compilare il progetto per creare un'attività personalizzata per accedere al primo servizio Web.</span><span class="sxs-lookup"><span data-stu-id="87350-163">Add a service reference to the service at http://localhost/NestedServices/StringReverserService.xamlx and build the project to create a custom activity to access the first Web service.</span></span>  
  
9. <span data-ttu-id="87350-164">Trascinare un'istanza della nuova attività flusso di lavoro, tra il **InvokeMethod** attività e **SendReplyToReceive** le attività.</span><span class="sxs-lookup"><span data-stu-id="87350-164">Drag an instance of the new activity onto the workflow, between the **InvokeMethod** activity and the **SendReplyToReceive** activities.</span></span> <span data-ttu-id="87350-165">Assegnare la variabile StringToReverse alla proprietà InputString della nuova attività e la variabile StringToReturn alla proprietà StringToReturn.</span><span class="sxs-lookup"><span data-stu-id="87350-165">Assign the variable StringToReverse to the InputString property of the new activity, and the variable StringToReturn to the StringToReturn property.</span></span>  
  
10. <span data-ttu-id="87350-166">Aprire la pagina delle proprietà per il progetto NestedServices e modificare il **pagina specifica** nel **Web** scheda Uppercaserservice.</span><span class="sxs-lookup"><span data-stu-id="87350-166">Open the Properties page for the NestedServices project, and change the **Specific Page** in the **Web** tab to UpperCaserService.xamlx.</span></span>  
  
11. <span data-ttu-id="87350-167">Premere F5 per testare il servizio.</span><span class="sxs-lookup"><span data-stu-id="87350-167">Test the service by pressing F5.</span></span> <span data-ttu-id="87350-168">Nel client di test WCF visualizzato fare doppio clic sul metodo ReverseString().</span><span class="sxs-lookup"><span data-stu-id="87350-168">In the WCF Test Client that appears, double-click the ReverseString() method.</span></span> <span data-ttu-id="87350-169">Nel riquadro della richiesta, immettere `Sample` per il valore del parametro InputString.</span><span class="sxs-lookup"><span data-stu-id="87350-169">In the Request pane, enter `Sample` for the Value of the InputString parameter.</span></span> <span data-ttu-id="87350-170">Fare clic su **richiamare**.</span><span class="sxs-lookup"><span data-stu-id="87350-170">Click **Invoke**.</span></span> <span data-ttu-id="87350-171">Il servizio deve restituire "ELPMAS".</span><span class="sxs-lookup"><span data-stu-id="87350-171">The service should return "ELPMAS".</span></span>  
  
### <a name="to-create-a-client-to-call-the-services"></a><span data-ttu-id="87350-172">Per creare un client che chiami i servizi</span><span class="sxs-lookup"><span data-stu-id="87350-172">To create a client to call the services</span></span>  
  
1.  <span data-ttu-id="87350-173">Aggiungere un nuovo progetto di applicazione console denominato Client alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="87350-173">Add a new Console application project called Client to the solution.</span></span>  
  
2.  <span data-ttu-id="87350-174">Fare clic sul progetto Client e selezionare **Aggiungi riferimento al servizio**.</span><span class="sxs-lookup"><span data-stu-id="87350-174">Right-click the Client project and select **Add Service Reference**.</span></span> <span data-ttu-id="87350-175">Nella finestra visualizzata, fare clic su **Discover**.</span><span class="sxs-lookup"><span data-stu-id="87350-175">In the window that appears, click **Discover**.</span></span> <span data-ttu-id="87350-176">Selezionare StringReverserService.xamlx e immettere ReverseService come spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="87350-176">Select StringReverserService.xamlx, and enter ReverseService as the namespace.</span></span>  <span data-ttu-id="87350-177">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="87350-177">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="87350-178">Sostituire il metodo Main in Program.cs con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="87350-178">Replace the Main method in Program.cs with the following code.</span></span>  
  
    ```  
    static void Main(string[] args)  
    {  
        Console.Write("Input string to process:");  
        String input = Console.ReadLine();  
        var service = new ReverseService.ReverseStringClient();  
        Console.WriteLine("Output from service: {0}", service.ReverseString(input));  
        Console.ReadKey();  
    }  
    ```
