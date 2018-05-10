---
title: Determinazione della durata dell'operazione del servizio
ms.date: 03/30/2017
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
ms.openlocfilehash: 8c86ccc09979071e0678be792f4937d526e23fa7
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
---
# <a name="determining-service-operation-duration"></a>Determinazione della durata dell'operazione del servizio
Se la traccia analitica è abilitata in un'applicazione Windows Communication Foundation (WCF), la durata dell'esecuzione per un'operazione del servizio può essere facilmente determinata esaminando il registro eventi.  In questo argomento viene descritto come determinare la quantità di tempo richiesta per il completamento di un'operazione del servizio.  
  
### <a name="determining-service-operation-execution-duration"></a>Determinazione della durata di esecuzione dell'operazione del servizio  
  
1.  Aprire il Visualizzatore eventi fare clic su **avviare**, **eseguire**e l'immissione di `eventvwr.exe`.  
  
2.  Se è stata abilitata la traccia analitica, espandere **registri applicazioni e servizi**, **Microsoft**, **Windows**, **Server applicazioni-applicazioni** . Selezionare **vista**, **Mostra analitica e registri di Debug**. Fare doppio clic su **analitico** e selezionare **Attiva registro**. Lasciare aperto il Visualizzatore eventi in modo che sia possibile visualizzare le tracce dopo l'esecuzione dell'operazione del servizio.  
  
3.  Successivamente, aprire un'applicazione WCF che include un progetto di servizio e un progetto di client che interagisce con tale servizio.  È possibile creare un'applicazione di questo tipo seguendo il [esercitazione introduttiva](../../../../../docs/framework/wcf/getting-started-tutorial.md).  Se si dispone di installare gli esempi WCF, è possibile aprire il [Getting Started](../../../../../docs/framework/wcf/samples/getting-started-sample.md), che contiene il progetto completato creato nell'esercitazione.  
  
4.  Eseguire l'applicazione server premendo **F5**. Eseguire l'applicazione client facendo clic su di **Client** progetto, quindi selezionando **Debug**, **Avvia nuova istanza**.  
  
5.  Nel Visualizzatore eventi aggiornare il registro analitico e ordinare gli eventi in base all'ID evento.  Ricercare gli eventi con ID evento [214 - OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md).  Questi eventi indicheranno le operazioni completate, nonché la relativa durata.  L'evento seguente indica la durata di un'operazione Add.  
  
    ```Output  
    An OperationInvoker completed the call to the 'Add' method.  The method call duration was '3' ms.  
    ```
