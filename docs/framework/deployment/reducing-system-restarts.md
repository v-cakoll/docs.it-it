---
title: Riduzione dei riavvii del sistema durante le installazioni di .NET Framework 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework, reducing system restarts
- installing .NET Framework
- installation [.NET Framework]
ms.assetid: 7aa8cb72-dee9-4716-ac54-b17b9ae8218f
ms.openlocfilehash: 6261a883e7b99b7fd38da2a17ab4820c81552506
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75716422"
---
# <a name="reducing-system-restarts-during-net-framework-45-installations"></a>Riduzione dei riavvii del sistema durante le installazioni di .NET Framework 4.5
Il programma di installazione di .NET Framework 4.5 usa [Gestione riavvio](/windows/win32/rstmgr/about-restart-manager) per evitare ove possibile il riavvio del sistema durante l'installazione. Se il programma di installazione dell'app installa .NET Framework, può interagire con la Gestione riavvio per sfruttare i vantaggi di questa funzionalità. Per altre informazioni, vedere [Procedura: Ottenere lo stato di avanzamento dal programma d'installazione di .NET Framework 4.5](how-to-get-progress-from-the-dotnet-installer.md)  
  
## <a name="reasons-for-a-restart"></a>Motivi di un riavvio  
 L'installazione di .NET Framework 4.5 richiede un riavvio del sistema se l'app .NET Framework 4 è in uso durante l'installazione, poiché .NET Framework 4.5 sostituisce i file di .NET Framework 4 e richiede che tali file siano disponibili durante l'installazione. In molti casi, il riavvio può essere evitato identificando e chiudendo le app .NET Framework 4 in uso prima dell'installazione. Tuttavia, alcune app di sistema non possono essere chiuse. In questi casi, non è possibile evitare un riavvio.  
  
## <a name="end-user-experience"></a>Esperienza utente finale  
 Un utente finale che esegue un'installazione completa di .NET Framework 4.5può evitare un riavvio del sistema se il programma di installazione rileva le app .NET Framework 4 in uso. Un messaggio elenca tutte le app .NET Framework 4 in esecuzione e offre la possibilità di chiudere tali app prima dell'installazione. Se l'utente conferma la chiusura, queste applicazioni vengono arrestate dal programma di installazione e viene evitato il riavvio del sistema. Se l'utente non effettua alcuna selezione entro un determinato periodo di tempo, l'installazione continua senza chiudere alcuna app.  
  
 Se la Gestione riavvio rileva una situazione in cui è necessario riavviare il sistema anche se le app in esecuzione vengono chiuse, non viene visualizzato il messaggio.  
  
 ![Finestra di dialogo Chiudi applicazione con i programmi attualmente in esecuzione.](./media/reducing-system-restarts/close-application-dialog.png)  
  
## <a name="using-a-chained-installer"></a>Uso di un programma di installazione concatenato  
 Se si vuole ridistribuire .NET Framework con l'app, ma si preferisce usare un programma di installazione e un'interfaccia utente personalizzati, è possibile includere (concatenare) il processo di installazione di .NET Framework nel processo di installazione. Per altre informazioni sulle installazioni concatenate, vedere [Guida alla distribuzione per sviluppatori](deployment-guide-for-developers.md). Per ridurre i riavvii del sistema in installazioni concatenate, il programma di installazione di .NET Framework elenca le app da chiudere. Il programma di installazione personalizzato deve specificare tali informazioni all'utente tramite un'interfaccia utente, ad esempio una finestra di messaggio, ottenere la risposta dell'utente e quindi passare la risposta al programma di installazione di .NET Framework. Per un esempio di un programma di installazione concatenata, vedere l'articolo [How to: Get Progress from the .NET Framework 4.5 Installer](how-to-get-progress-from-the-dotnet-installer.md) (Procedura: Ottenere lo stato di avanzamento dal programma d'installazione di .NET Framework 4.5).  
  
 Se si usa un programma di installazione concatenata, ma non si vuole visualizzare una finestra di messaggio personalizzata per la chiusura delle app, è possibile usare le opzioni `/showrmui` e `/passive` della riga di comando quando si concatena il processo di installazione di .NET Framework. Quando si usano queste opzioni insieme, il programma di installazione visualizza la finestra di messaggio per la chiusura delle app, che è possibile chiudere per evitare un riavvio del sistema. Questa finestra di messaggio ha lo stesso comportamento in modo passivo della finestra di messaggio visualizzata nell'interfaccia utente completa. Per il set completo delle opzioni della riga di comando per .NET Framework ridistribuibile, vedere [Guida alla distribuzione per sviluppatori](deployment-guide-for-developers.md).  
  
## <a name="see-also"></a>Vedere anche

- [Distribuzione](index.md)
- [Guida alla distribuzione per gli sviluppatori](deployment-guide-for-developers.md)
- [Procedura: Ottenere lo stato di avanzamento dal programma d'installazione di .NET Framework 4.5](how-to-get-progress-from-the-dotnet-installer.md)
