---
title: Determinazione della durata dell'operazione del servizio
ms.date: 03/30/2017
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
ms.openlocfilehash: 06a4c2da7b702fa4fbc1469576c118b790803339
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291430"
---
# <a name="determining-service-operation-duration"></a>Determinazione della durata dell'operazione del servizio
Se la traccia analitica è abilitata in un'applicazione Windows Communication Foundation (WCF), è possibile determinare facilmente la durata dell'esecuzione di un'operazione del servizio esaminando il registro eventi.  In questo argomento viene descritto come determinare la quantità di tempo richiesta per il completamento di un'operazione del servizio.  
  
### <a name="determining-service-operation-execution-duration"></a>Determinazione della durata di esecuzione dell'operazione del servizio  
  
1. Per aprire Visualizzatore eventi, fare clic su **Start**, **esegui**e immettere `eventvwr.exe`.  
  
2. Se non è stata abilitata la traccia analitica, espandere **registri applicazioni e servizi**, **Microsoft**, **Windows**, **server applicazioni-applicazioni**. Selezionare **Visualizza**, Mostra **log analitici e di debug**. Fare clic con il pulsante destro del mouse su **analitico** e selezionare **Abilita log**. Lasciare aperto il Visualizzatore eventi in modo che sia possibile visualizzare le tracce dopo l'esecuzione dell'operazione del servizio.  
  
3. Aprire quindi un'applicazione WCF che include un progetto di servizio e un progetto client che interagisce con tale servizio.  È possibile creare tale applicazione seguendo l' [esercitazione Introduzione](../../getting-started-tutorial.md).  Se sono stati installati gli esempi WCF, è possibile aprire il [Introduzione](../../samples/getting-started-sample.md), che contiene il progetto completato creato nell'esercitazione.  
  
4. Eseguire l'applicazione server premendo **F5**. Eseguire l'applicazione client facendo clic con il pulsante destro del mouse sul progetto **client** e selezionando **debug**, **Avvia nuova istanza**.  
  
5. Nel Visualizzatore eventi aggiornare il registro analitico e ordinare gli eventi in base all'ID evento.  Cercare gli eventi con ID evento [214-OperationCompleted](214-operationcompleted.md).  Questi eventi indicheranno le operazioni completate, nonché la relativa durata.  L'evento seguente indica la durata di un'operazione Add.  
  
    ```output  
    An OperationInvoker completed the call to the 'Add' method.  The method call duration was '3' ms.  
    ```
