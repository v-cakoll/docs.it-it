---
title: Multithreading nei controlli Windows Form
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
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c4651ca9707dcf0fac2edea0f004275cfcf18cf2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="multithreading-in-windows-forms-controls"></a>Multithreading nei controlli Windows Form
In molte applicazioni, è possibile rendere più reattiva l'interfaccia utente (UI) mediante l'esecuzione di operazioni lunghe ed elaborate in un altro thread. Una serie di strumenti è disponibile per multithreading dei controlli Windows Form, inclusi il <xref:System.Threading> dello spazio dei nomi, il <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> (metodo) e `BackgroundWorker` componente.  
  
> [!NOTE]
>  Il `BackgroundWorker` componente sostituisce e aggiunge la funzionalità per il <xref:System.Threading> dello spazio dei nomi e <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> metodo; tuttavia, questi vengono mantenuti per compatibilità con le versioni precedenti e per utilizzo futuro, se si sceglie. Per ulteriori informazioni, vedere [Cenni preliminari sul componente BackgroundWorker](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md).  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Procedura: Effettuare chiamate thread-safe a controlli di Windows Form](../../../../docs/framework/winforms/controls/how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 Viene illustrato come effettuare chiamate thread-safe a controlli Windows Form.  
  
 [Procedura: Usare un thread in background per la ricerca di file](../../../../docs/framework/winforms/controls/how-to-use-a-background-thread-to-search-for-files.md)  
 Viene illustrato come utilizzare il <xref:System.Threading> dello spazio dei nomi e <xref:System.Windows.Forms.Control.BeginInvoke%2A> metodo per cercare i file in modo asincrono.  
  
## <a name="reference"></a>Riferimento  
 <xref:System.ComponentModel.BackgroundWorker>  
 Documenti di un componente che incapsula un thread di lavoro per le operazioni asincrone.  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 Viene illustrato come caricare in modo asincrono un suono.  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 Viene illustrato come caricare un'immagine in modo asincrono.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Procedura: Eseguire un'operazione in background](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 Viene illustrato come eseguire un'operazione richiede molto tempo con la <xref:System.ComponentModel.BackgroundWorker> componente.  
  
 [Panoramica sul componente BackgroundWorker](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 Fornisce argomenti che descrivono come utilizzare il <xref:System.ComponentModel.BackgroundWorker> componente per le operazioni asincrone.
