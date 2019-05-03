---
title: Componente BackgroundWorker
ms.date: 03/30/2017
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
ms.openlocfilehash: 0baf54d27cf33eef7e4df7019ee98b42eba40205
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011801"
---
# <a name="backgroundworker-component"></a>Componente BackgroundWorker
Il `BackgroundWorker` componente consente a un form o controllo per eseguire un'operazione in modo asincrono.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Panoramica sul componente BackgroundWorker](backgroundworker-component-overview.md)  
 Viene descritto il `BackgroundWorker` componente, che ti offre la possibilità di eseguire operazioni che richiedono molto tempo in modo asincrono ("in background"), in un thread diverso dal thread principale della UI dell'applicazione.  
  
 [Procedura dettagliata: Esecuzione di un'operazione in Background](walkthrough-running-an-operation-in-the-background.md)  
 Viene illustrato come utilizzare il `BackgroundWorker` componente nella finestra di progettazione per eseguire un'operazione impegnativa in un thread separato.  
  
 [Procedura: Eseguire un'operazione in background](how-to-run-an-operation-in-the-background.md)  
 Viene illustrato come utilizzare il `BackgroundWorker` componente per l'esecuzione di un'operazione impegnativa in un thread separato.  
  
 [Procedura dettagliata: Implementazione di un Form che usa un'operazione in Background](walkthrough-implementing-a-form-that-uses-a-background-operation.md)  
 Crea un'applicazione usando la finestra di progettazione che esegue calcoli matematici in modo asincrono.  
  
 [Procedura: Implementare un modulo che usa un'operazione in background](how-to-implement-a-form-that-uses-a-background-operation.md)  
 Crea un'applicazione che esegue calcoli matematici in modo asincrono.  
  
 [Procedura: Scaricare un File in Background](how-to-download-a-file-in-the-background.md)  
 Viene illustrato come utilizzare il `BackgroundWorker` componente per scaricare un file in un thread separato.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.ComponentModel.BackgroundWorker>  
 Descrive la classe e fornisce i collegamenti a tutti i relativi membri.  
  
 <xref:System.ComponentModel.RunWorkerCompletedEventArgs>  
 Descrive il tipo che contiene i dati per il <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> evento.  
  
 <xref:System.ComponentModel.ProgressChangedEventArgs>  
 Descrive il tipo che contiene i dati per il <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> evento.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Panoramica sul modello asincrono basato su eventi](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 Viene descritto come il modello asincrono rende disponibili i vantaggi delle applicazioni multithread, nascondendo molti dei problemi complessi correlati alla progettazione multithread.
