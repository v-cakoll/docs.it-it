---
title: Riduzione dei riavvii del sistema durante le installazioni di .NET Framework 4.5
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework, reducing system restarts
- installing .NET Framework
- installation [.NET Framework]
ms.assetid: 7aa8cb72-dee9-4716-ac54-b17b9ae8218f
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0019931c0ebe2bfef7ce8db72b768f31ad67f938
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="reducing-system-restarts-during-net-framework-45-installations"></a>Riduzione dei riavvii del sistema durante le installazioni di .NET Framework 4.5
Il programma di installazione di [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] usa [Gestione riavvio](http://go.microsoft.com/fwlink/?LinkId=231425) per evitare, quando possibile, i riavvii del sistema durante l'installazione. Se il programma di installazione dell'app installa .NET Framework, può interagire con la Gestione riavvio per sfruttare i vantaggi di questa funzionalità. Per altre informazioni, vedere [Procedura: Ottenere lo stato di avanzamento dal programma d'installazione di .NET Framework 4.5](../../../docs/framework/deployment/how-to-get-progress-from-the-dotnet-installer.md)  
  
## <a name="reasons-for-a-restart"></a>Motivi di un riavvio  
 L'installazione di [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] richiede un riavvio del sistema se l'app .NET Framework 4 è in uso durante l'installazione. Ciò si verifica perché [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] sostituisce i file di .NET Framework 4 e richiede che tali file siano disponibili durante l'installazione. In molti casi, il riavvio può essere evitato identificando e chiudendo le app .NET Framework 4 in uso prima dell'installazione. Tuttavia, alcune app di sistema non possono essere chiuse. In questi casi, non è possibile evitare un riavvio.  
  
## <a name="end-user-experience"></a>Esperienza utente finale  
 Un utente finale che esegue un'installazione completa di [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] ha la possibilità per evitare un riavvio del sistema se il programma di installazione rileva le app .NET Framework 4 in uso. Un messaggio elenca tutte le app .NET Framework 4 in esecuzione e offre la possibilità di chiudere tali app prima dell'installazione. Se l'utente conferma la chiusura, queste applicazioni vengono arrestate dal programma di installazione e viene evitato il riavvio del sistema. Se l'utente non effettua alcuna selezione entro un determinato periodo di tempo, l'installazione continua senza chiudere alcuna app.  
  
 Se la Gestione riavvio rileva una situazione in cui è necessario riavviare il sistema anche se le app in esecuzione vengono chiuse, non viene visualizzato il messaggio.  
  
 ![Chiudere una finestra di dialogo applicazione](../../../docs/framework/deployment/media/closeapplicationdialog.png "CloseApplicationDialog")  
Richiesta di chiusura delle app .NET Framework in uso  
  
## <a name="using-a-chained-installer"></a>Uso di un programma di installazione concatenato  
 Se si vuole ridistribuire .NET Framework con l'app, ma si preferisce usare un programma di installazione e un'interfaccia utente personalizzati, è possibile includere (concatenare) il processo di installazione di .NET Framework nel processo di installazione. Per altre informazioni sulle installazioni concatenate, vedere [Guida alla distribuzione per sviluppatori](../../../docs/framework/deployment/deployment-guide-for-developers.md). Per ridurre i riavvii del sistema in installazioni concatenate, il programma di installazione di .NET Framework elenca le app da chiudere. Il programma di installazione personalizzato deve specificare tali informazioni all'utente tramite un'interfaccia utente, ad esempio una finestra di messaggio, ottenere la risposta dell'utente e quindi passare la risposta al programma di installazione di .NET Framework. Per un esempio di un programma di installazione concatenata, vedere l'articolo [How to: Get Progress from the .NET Framework 4.5 Installer](../../../docs/framework/deployment/how-to-get-progress-from-the-dotnet-installer.md) (Procedura: Ottenere lo stato di avanzamento dal programma d'installazione di .NET Framework 4.5).  
  
 Se si usa un programma di installazione concatenata, ma non si vuole visualizzare una finestra di messaggio personalizzata per la chiusura delle app, è possibile usare le opzioni `/showrmui` e `/passive` della riga di comando quando si concatena il processo di installazione di .NET Framework. Quando si usano queste opzioni insieme, il programma di installazione visualizza la finestra di messaggio per la chiusura delle app, che è possibile chiudere per evitare un riavvio del sistema. Questa finestra di messaggio ha lo stesso comportamento in modo passivo della finestra di messaggio visualizzata nell'interfaccia utente completa. Per il set completo delle opzioni della riga di comando per .NET Framework ridistribuibile, vedere [Guida alla distribuzione per sviluppatori](../../../docs/framework/deployment/deployment-guide-for-developers.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Distribuzione](../../../docs/framework/deployment/index.md)  
 [Guida alla distribuzione per gli sviluppatori](../../../docs/framework/deployment/deployment-guide-for-developers.md)  
 [Procedura: Ottenere lo stato di avanzamento dal programma d'installazione di .NET Framework 4.5](../../../docs/framework/deployment/how-to-get-progress-from-the-dotnet-installer.md)
