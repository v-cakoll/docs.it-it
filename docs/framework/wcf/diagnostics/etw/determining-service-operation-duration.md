---
title: Determinazione della durata dell'operazione del servizio
ms.date: 03/30/2017
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
ms.openlocfilehash: fd7dec5784f50a0613b574822a31202a859b34c6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59299033"
---
# <a name="determining-service-operation-duration"></a>Determinazione della durata dell'operazione del servizio
Se la traccia analitica è abilitata in un'applicazione Windows Communication Foundation (WCF), la durata dell'esecuzione per un'operazione del servizio può essere determinata facilmente esaminando il registro eventi.  In questo argomento viene descritto come determinare la quantità di tempo richiesta per il completamento di un'operazione del servizio.  
  
### <a name="determining-service-operation-execution-duration"></a>Determinazione della durata di esecuzione dell'operazione del servizio  
  
1. Aprire il Visualizzatore eventi facendo **avviare**, **eseguito**e l'immissione di `eventvwr.exe`.  
  
2. Se non è stata abilitata la traccia analitica, espandere **registri applicazioni e servizi**, **Microsoft**, **Windows**, **Server applicazioni-applicazioni** . Selezionare **View**, **mostrano analitici e i registri Debug**. Fare doppio clic su **analitico** e selezionare **Attiva registro**. Lasciare aperto il Visualizzatore eventi in modo che sia possibile visualizzare le tracce dopo l'esecuzione dell'operazione del servizio.  
  
3. Successivamente, aprire un'applicazione WCF che include un progetto di servizio e un progetto di client che interagisce con il servizio.  È possibile creare un'applicazione di questo tipo seguendo la [esercitazione introduttiva](../../../../../docs/framework/wcf/getting-started-tutorial.md).  Se si dispone di installare gli esempi WCF, è possibile aprire il [introduttiva](../../../../../docs/framework/wcf/samples/getting-started-sample.md), che contiene il progetto completato creato nell'esercitazione.  
  
4. Eseguire l'applicazione server premendo **F5**. Eseguire l'applicazione client facendo clic sui **Client** progetto, quindi selezionando **Debug**, **Avvia nuova istanza**.  
  
5. Nel Visualizzatore eventi aggiornare il registro analitico e ordinare gli eventi in base all'ID evento.  Ricercare gli eventi con ID evento [214 - OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md).  Questi eventi indicheranno le operazioni completate, nonché la relativa durata.  L'evento seguente indica la durata di un'operazione Add.  
  
    ```Output  
    An OperationInvoker completed the call to the 'Add' method.  The method call duration was '3' ms.  
    ```
