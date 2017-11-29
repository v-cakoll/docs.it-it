---
title: Componente BackgroundWorker
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: bef7b0ab-ce57-475a-a2d6-fb8a702a9417
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cbcbc786c19ad1af74114915b0fd0689d466fcbe
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="backgroundworker-component"></a>Componente BackgroundWorker
Il `BackgroundWorker` componente consente a un form o controllo per eseguire un'operazione in modo asincrono.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Panoramica sul componente BackgroundWorker](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 Viene descritto il `BackgroundWorker` componente, che offre la possibilità di eseguire operazioni lunghe ed elaborate in modo asincrono (in background"), su un thread diverso dal thread dell'interfaccia utente principale dell'applicazione.  
  
 [Procedura dettagliata: Esecuzione di un'operazione in background](../../../../docs/framework/winforms/controls/walkthrough-running-an-operation-in-the-background.md)  
 Viene illustrato come utilizzare il `BackgroundWorker` componente nella finestra di progettazione per eseguire un'operazione richiede molto tempo su un thread separato.  
  
 [Procedura: Eseguire un'operazione in background](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 Viene illustrato come utilizzare il `BackgroundWorker` componente per l'esecuzione di un'operazione richiede molto tempo su un thread separato.  
  
 [Procedura dettagliata: Implementazione di un form che usa un'operazione in background](../../../../docs/framework/winforms/controls/walkthrough-implementing-a-form-that-uses-a-background-operation.md)  
 Crea un'applicazione utilizzando la finestra di progettazione che esegue calcoli matematici in modo asincrono.  
  
 [Procedura: Implementare un form che esegue un'operazione in background](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 Crea un'applicazione che esegue calcoli matematici in modo asincrono.  
  
 [Procedura: Scaricare file in background](../../../../docs/framework/winforms/controls/how-to-download-a-file-in-the-background.md)  
 Viene illustrato come utilizzare il `BackgroundWorker` componente per scaricare un file in un thread separato.  
  
## <a name="reference"></a>Riferimento  
 <xref:System.ComponentModel.BackgroundWorker>  
 Descrive la classe e fornisce i collegamenti a tutti i relativi membri.  
  
 <xref:System.ComponentModel.RunWorkerCompletedEventArgs>  
 Descrive il tipo che contiene i dati per il <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> evento.  
  
 <xref:System.ComponentModel.ProgressChangedEventArgs>  
 Descrive il tipo che contiene i dati per il <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> evento.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Panoramica sul modello asincrono basato su eventi](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 Descrive come il modello asincrono rende disponibili i vantaggi delle applicazioni multithreading nascondendo al contempo gran degli aspetti complessi inerenti la progettazione multithreading.
