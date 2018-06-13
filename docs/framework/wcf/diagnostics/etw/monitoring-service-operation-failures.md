---
title: Monitoraggio di errori relativi alle operazioni del servizio
ms.date: 03/30/2017
ms.assetid: 59472ba3-8ebf-4479-bd7b-f440d5e636cb
ms.openlocfilehash: 3d708b537789c8d0decf75df780300c1e185c4c8
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
ms.locfileid: "33803767"
---
# <a name="monitoring-service-operation-failures"></a><span data-ttu-id="7dd0e-102">Monitoraggio di errori relativi alle operazioni del servizio</span><span class="sxs-lookup"><span data-stu-id="7dd0e-102">Monitoring Service Operation Failures</span></span>
<span data-ttu-id="7dd0e-103">Se la traccia analitica è abilitata per un'applicazione, è possibile monitorare gli errori del servizio facilmente nel visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="7dd0e-103">If analytic tracing is enabled for an application, service failures can easily be monitored in the event viewer.</span></span>  <span data-ttu-id="7dd0e-104">Questo argomento illustra come determinare quando un'operazione del servizio non riesce e come determinare ciò che ha provocato l'errore.</span><span class="sxs-lookup"><span data-stu-id="7dd0e-104">This topic demonstrates how to determine when a service operation fails, and how to determine what caused the failure.</span></span>  
  
### <a name="determining-service-operation-failure-information"></a><span data-ttu-id="7dd0e-105">Informazioni sulla determinazione di errori relativi alle operazioni del servizio</span><span class="sxs-lookup"><span data-stu-id="7dd0e-105">Determining service operation failure information</span></span>  
  
1.  <span data-ttu-id="7dd0e-106">Aprire il Visualizzatore eventi fare clic su **avviare**, **eseguire**e l'immissione di `eventvwr.exe`.</span><span class="sxs-lookup"><span data-stu-id="7dd0e-106">Open Event Viewer by clicking **Start**, **Run**, and entering `eventvwr.exe`.</span></span>  
  
2.  <span data-ttu-id="7dd0e-107">Se è stata abilitata la traccia analitica, espandere **registri applicazioni e servizi**, **Microsoft**, **Windows**, **Server applicazioni-applicazioni** .</span><span class="sxs-lookup"><span data-stu-id="7dd0e-107">If you haven’t enabled analytic tracing, expand **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="7dd0e-108">Selezionare **vista**, **Mostra analitica e registri di Debug**.</span><span class="sxs-lookup"><span data-stu-id="7dd0e-108">Select **View**, **Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="7dd0e-109">Fare doppio clic su **analitico** e selezionare **Attiva registro**.</span><span class="sxs-lookup"><span data-stu-id="7dd0e-109">Right-click **Analytic** and select **Enable Log**.</span></span> <span data-ttu-id="7dd0e-110">Lasciare aperto il Visualizzatore eventi in modo che le tracce possano essere visualizzate dopo la mancata riuscita dell'operazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="7dd0e-110">Leave Event Viewer open so that traces can be viewed after the service operation fails.</span></span>  
  
3.  <span data-ttu-id="7dd0e-111">Aprire quindi il codice di esempio creato nel [esercitazione introduttiva](../../../../../docs/framework/wcf/getting-started-tutorial.md) in [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] si noti che è necessario eseguire [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] come amministratore in modo che il servizio può essere creato.</span><span class="sxs-lookup"><span data-stu-id="7dd0e-111">Next, open the sample created in the [Getting Started Tutorial](../../../../../docs/framework/wcf/getting-started-tutorial.md) in [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] Note that you must run [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] as an administrator so that the service can be created.</span></span> <span data-ttu-id="7dd0e-112">Se si dispone di installare gli esempi WCF, è possibile aprire il [Getting Started](../../../../../docs/framework/wcf/samples/getting-started-sample.md), che contiene il progetto completato creato nell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="7dd0e-112">If you have the WCF samples installed, you can open the [Getting Started](../../../../../docs/framework/wcf/samples/getting-started-sample.md), which contains the completed project created in the tutorial.</span></span>  
  
4.  <span data-ttu-id="7dd0e-113">Nel file Program.cs del progetto Server aggiungere la riga di codice seguente all'inizio del metodo `Divide` nella classe `CalculatorService`:</span><span class="sxs-lookup"><span data-stu-id="7dd0e-113">In the Program.cs file in the Server project, add the following line of code to the start of the `Divide` method in the `CalculatorService` class:</span></span>  
  
    ```  
    if (n2 == 0) throw new DivideByZeroException();  
    ```  
  
5.  <span data-ttu-id="7dd0e-114">Nel file Program.cs nel progetto Client, assegnare a value2 il valore zero:</span><span class="sxs-lookup"><span data-stu-id="7dd0e-114">In the Program.cs file in the Client project, change the value assigned to value2 to zero:</span></span>  
  
    ```  
    //Call the Divide service operation  
    value1 = 22.00D;  
    value2 = 0.00D;  
    result = client.Divide(value1, value2);  
    Console.WriteLine("Divide({0}, {1}) = {2}", value1, value2, result);  
    ```  
  
6.  <span data-ttu-id="7dd0e-115">Eseguire l'applicazione server senza debug premendo **Ctrl + F5**.</span><span class="sxs-lookup"><span data-stu-id="7dd0e-115">Execute the server application without debugging by pressing **Ctrl+F5**.</span></span>  
  
7.  <span data-ttu-id="7dd0e-116">Aprire il prompt dei comandi di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7dd0e-116">Open a Visual Studio command prompt.</span></span>  <span data-ttu-id="7dd0e-117">Passare alla directory client ed eseguire il client dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="7dd0e-117">Navigate to the client directory and execute the client from the command line.</span></span>  
  
8.  <span data-ttu-id="7dd0e-118">Nel Visualizzatore eventi, disabilitare e aggiornare il registro analitico e ordinare gli eventi in base all'ID evento.</span><span class="sxs-lookup"><span data-stu-id="7dd0e-118">In Event Viewer, disable and refresh the Analytic log and sort the events by Event ID.</span></span>  <span data-ttu-id="7dd0e-119">Cerca un evento con ID evento [ServiceException 219 -](../../../../../docs/framework/wcf/diagnostics/etw/219-serviceexception.md), che descrive l'errore di servizio.</span><span class="sxs-lookup"><span data-stu-id="7dd0e-119">Look for an event with Event ID [219 - ServiceException](../../../../../docs/framework/wcf/diagnostics/etw/219-serviceexception.md), which describes the service failure.</span></span>  
  
    ```Output  
    There was an unhandled exception of type 'System.DivideByZeroException' during message processing.  Full Exception ToString: System.DivideByZeroException: Attempted to divide by zero.  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="7dd0e-120">Gli eventi vengono memorizzati nel buffer in caso di invio al visualizzatore eventi; è possibile che l'evento relativo all'errore non venga subito visualizzato.</span><span class="sxs-lookup"><span data-stu-id="7dd0e-120">Events are buffered when being sent to the event viewer; the failure event may not appear right away.</span></span>
