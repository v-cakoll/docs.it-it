---
title: Multithreading nei controlli
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: 79832e12a10f02c909d2a28270594bcb4ea68656
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742137"
---
# <a name="multithreading-in-windows-forms-controls"></a>Multithreading nei controlli Windows Form
In molte applicazioni è possibile rendere più reattive l'interfaccia utente eseguendo operazioni che richiedono molto tempo in un altro thread. Sono disponibili diversi strumenti per il multithreading dei controlli di Windows Forms, tra cui lo spazio dei nomi <xref:System.Threading>, il metodo <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> e il componente `BackgroundWorker`.  
  
> [!NOTE]
> Il componente `BackgroundWorker` sostituisce e aggiunge funzionalità allo spazio dei nomi <xref:System.Threading> e al metodo <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType>; Tuttavia, questi vengono conservati sia per la compatibilità con le versioni precedenti che per un uso futuro, se si sceglie. Per ulteriori informazioni, vedere [Cenni preliminari sul componente BackgroundWorker](backgroundworker-component-overview.md).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Effettuare chiamate thread-safe a controlli di Windows Form](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 Viene illustrato come eseguire chiamate thread-safe a controlli Windows Forms.  
  
 [Procedura: Usare un thread in background per la ricerca di file](how-to-use-a-background-thread-to-search-for-files.md)  
 Viene illustrato come utilizzare lo spazio dei nomi <xref:System.Threading> e il metodo <xref:System.Windows.Forms.Control.BeginInvoke%2A> per cercare i file in modo asincrono.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.ComponentModel.BackgroundWorker>  
 Documenta un componente che incapsula un thread di lavoro per le operazioni asincrone.  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 Documenta come caricare un suono in modo asincrono.  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 Documenta come caricare un'immagine in modo asincrono.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Procedura: Eseguire un'operazione in background](how-to-run-an-operation-in-the-background.md)  
 Viene illustrato come eseguire un'operazione che richiede molto tempo con il componente <xref:System.ComponentModel.BackgroundWorker>.  
  
 [Panoramica sul componente BackgroundWorker](backgroundworker-component-overview.md)  
 Fornisce argomenti che descrivono come usare il componente <xref:System.ComponentModel.BackgroundWorker> per le operazioni asincrone.
