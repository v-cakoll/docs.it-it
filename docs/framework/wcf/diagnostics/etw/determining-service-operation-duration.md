---
title: Determinazione della durata dell'operazione del servizio
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 24f1bc22e088c0198ec8a8f8183611d2b43941b5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="determining-service-operation-duration"></a>Determinazione della durata dell'operazione del servizio
Se la traccia analitica è abilitata in un'applicazione [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], la durata di esecuzione per un'operazione del servizio può essere determinata con facilità esaminando il registro eventi.  In questo argomento viene descritto come determinare la quantità di tempo richiesta per il completamento di un'operazione del servizio.  
  
### <a name="determining-service-operation-execution-duration"></a>Determinazione della durata di esecuzione dell'operazione del servizio  
  
1.  Aprire il Visualizzatore eventi fare clic su **avviare**, **eseguire**e l'immissione di `eventvwr.exe`.  
  
2.  Se è stata abilitata la traccia analitica, espandere **registri applicazioni e servizi**, **Microsoft**, **Windows**, **Server applicazioni-applicazioni** . Selezionare **vista**, **Mostra analitica e registri di Debug**. Fare doppio clic su **analitico** e selezionare **Attiva registro**. Lasciare aperto il Visualizzatore eventi in modo che sia possibile visualizzare le tracce dopo l'esecuzione dell'operazione del servizio.  
  
3.  Aprire quindi un'applicazione [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] in cui siano inclusi un progetto di servizio e un progetto client che interagisce con tale servizio.  È possibile creare un'applicazione di questo tipo seguendo il [esercitazione introduttiva](../../../../../docs/framework/wcf/getting-started-tutorial.md).  Se si dispone di [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] gli esempi installati, è possibile aprire il [Introduzione](../../../../../docs/framework/wcf/samples/getting-started-sample.md), che contiene il progetto completato, creato nell'esercitazione.  
  
4.  Eseguire l'applicazione server premendo **F5**. Eseguire l'applicazione client facendo clic su di **Client** progetto, quindi selezionando **Debug**, **Avvia nuova istanza**.  
  
5.  Nel Visualizzatore eventi aggiornare il registro analitico e ordinare gli eventi in base all'ID evento.  Ricercare gli eventi con ID evento [214 - OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md).  Questi eventi indicheranno le operazioni completate, nonché la relativa durata.  L'evento seguente indica la durata di un'operazione Add.  
  
    ```Output  
    An OperationInvoker completed the call to the 'Add' method.  The method call duration was '3' ms.  
    ```
