---
title: Multithreading nei controlli Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: cf6790172b7445ad154eead5d17f8efddd78ffee
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952671"
---
# <a name="multithreading-in-windows-forms-controls"></a>Multithreading nei controlli Windows Form
In molte applicazioni è possibile rendere più reattive l'interfaccia utente eseguendo operazioni che richiedono molto tempo in un altro thread. Sono disponibili diversi strumenti per il multithreading dei controlli di Windows Forms, tra cui <xref:System.Threading> lo spazio dei <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> nomi, il metodo `BackgroundWorker` e il componente.  
  
> [!NOTE]
> Il `BackgroundWorker` componente sostituisce e aggiunge funzionalità allo spazio <xref:System.Threading> dei nomi e <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> al metodo. questi elementi vengono tuttavia conservati sia per la compatibilità con le versioni precedenti che per un uso futuro, se si sceglie. Per ulteriori informazioni, vedere [Cenni preliminari sul componente BackgroundWorker](backgroundworker-component-overview.md).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Eseguire chiamate thread-safe a controlli Windows Forms](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 Viene illustrato come eseguire chiamate thread-safe a controlli Windows Forms.  
  
 [Procedura: Usare un thread in background per la ricerca di file](how-to-use-a-background-thread-to-search-for-files.md)  
 Viene illustrato come utilizzare lo <xref:System.Threading> spazio dei nomi <xref:System.Windows.Forms.Control.BeginInvoke%2A> e il metodo per cercare i file in modo asincrono.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.ComponentModel.BackgroundWorker>  
 Documenta un componente che incapsula un thread di lavoro per le operazioni asincrone.  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 Documenta come caricare un suono in modo asincrono.  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 Documenta come caricare un'immagine in modo asincrono.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Procedura: Eseguire un'operazione in background](how-to-run-an-operation-in-the-background.md)  
 Viene illustrato come eseguire un'operazione che richiede molto tempo con il <xref:System.ComponentModel.BackgroundWorker> componente.  
  
 [Panoramica sul componente BackgroundWorker](backgroundworker-component-overview.md)  
 Fornisce argomenti che descrivono come utilizzare il <xref:System.ComponentModel.BackgroundWorker> componente per le operazioni asincrone.
