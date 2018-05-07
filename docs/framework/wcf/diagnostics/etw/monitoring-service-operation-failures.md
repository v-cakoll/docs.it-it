---
title: Monitoraggio di errori relativi alle operazioni del servizio
ms.date: 03/30/2017
ms.assetid: 59472ba3-8ebf-4479-bd7b-f440d5e636cb
ms.openlocfilehash: 16ed779f77836fb68cf1edf1e01dbb3c0df01d45
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="monitoring-service-operation-failures"></a>Monitoraggio di errori relativi alle operazioni del servizio
Se la traccia analitica è abilitata per un'applicazione, è possibile monitorare gli errori del servizio facilmente nel visualizzatore eventi.  Questo argomento illustra come determinare quando un'operazione del servizio non riesce e come determinare ciò che ha provocato l'errore.  
  
### <a name="determining-service-operation-failure-information"></a>Informazioni sulla determinazione di errori relativi alle operazioni del servizio  
  
1.  Aprire il Visualizzatore eventi fare clic su **avviare**, **eseguire**e l'immissione di `eventvwr.exe`.  
  
2.  Se è stata abilitata la traccia analitica, espandere **registri applicazioni e servizi**, **Microsoft**, **Windows**, **Server applicazioni-applicazioni** . Selezionare **vista**, **Mostra analitica e registri di Debug**. Fare doppio clic su **analitico** e selezionare **Attiva registro**. Lasciare aperto il Visualizzatore eventi in modo che le tracce possano essere visualizzate dopo la mancata riuscita dell'operazione del servizio.  
  
3.  Aprire quindi il codice di esempio creato nel [esercitazione introduttiva](../../../../../docs/framework/wcf/getting-started-tutorial.md) in [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] si noti che è necessario eseguire [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] come amministratore in modo che il servizio può essere creato. Se si dispone di [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] gli esempi installati, è possibile aprire il [Introduzione](../../../../../docs/framework/wcf/samples/getting-started-sample.md), che contiene il progetto completato, creato nell'esercitazione.  
  
4.  Nel file Program.cs del progetto Server aggiungere la riga di codice seguente all'inizio del metodo `Divide` nella classe `CalculatorService`:  
  
    ```  
    if (n2 == 0) throw new DivideByZeroException();  
    ```  
  
5.  Nel file Program.cs nel progetto Client, assegnare a value2 il valore zero:  
  
    ```  
    //Call the Divide service operation  
    value1 = 22.00D;  
    value2 = 0.00D;  
    result = client.Divide(value1, value2);  
    Console.WriteLine("Divide({0}, {1}) = {2}", value1, value2, result);  
    ```  
  
6.  Eseguire l'applicazione server senza debug premendo **Ctrl + F5**.  
  
7.  Aprire il prompt dei comandi di Visual Studio.  Passare alla directory client ed eseguire il client dalla riga di comando.  
  
8.  Nel Visualizzatore eventi, disabilitare e aggiornare il registro analitico e ordinare gli eventi in base all'ID evento.  Cerca un evento con ID evento [ServiceException 219 -](../../../../../docs/framework/wcf/diagnostics/etw/219-serviceexception.md), che descrive l'errore di servizio.  
  
    ```Output  
    There was an unhandled exception of type 'System.DivideByZeroException' during message processing.  Full Exception ToString: System.DivideByZeroException: Attempted to divide by zero.  
    ```  
  
    > [!NOTE]
    >  Gli eventi vengono memorizzati nel buffer in caso di invio al visualizzatore eventi; è possibile che l'evento relativo all'errore non venga subito visualizzato.
