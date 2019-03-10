---
title: Multithreading nei controlli Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: cc7f358a62c8057abb77e1f5a28544bb6c858d98
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703322"
---
# <a name="multithreading-in-windows-forms-controls"></a>Multithreading nei controlli Windows Form
In molte applicazioni, è possibile rendere più reattiva l'interfaccia utente (UI) eseguendo le operazioni che richiedono molto tempo in un altro thread. Una serie di strumenti è disponibile per il multithreading dei controlli Windows Form, tra cui il <xref:System.Threading> dello spazio dei nomi, il <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> metodo e il `BackgroundWorker` componente.  
  
> [!NOTE]
>  Il `BackgroundWorker` componente sostituisce e aggiunge funzionalità per il <xref:System.Threading> dello spazio dei nomi e il <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> metodo; tuttavia, questi vengono mantenuti per compatibilità con le versioni precedenti e per un uso futuro, se si sceglie. Per altre informazioni, vedere [Cenni preliminari sul componente BackgroundWorker](backgroundworker-component-overview.md).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Effettuare chiamate Thread-Safe a controlli di Windows Form](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 Viene illustrato come effettuare chiamate thread-safe a controlli Windows Form.  
  
 [Procedura: Usare un Thread in Background per la ricerca file](how-to-use-a-background-thread-to-search-for-files.md)  
 Viene illustrato come utilizzare il <xref:System.Threading> dello spazio dei nomi e il <xref:System.Windows.Forms.Control.BeginInvoke%2A> metodo per cercare i file in modo asincrono.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.ComponentModel.BackgroundWorker>  
 Documenta un componente che incapsula un thread di lavoro per le operazioni asincrone.  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 Viene illustrato come caricare in modo asincrono un suono.  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 Viene illustrato come caricare un'immagine in modo asincrono.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Procedura: Eseguire un'operazione in background](how-to-run-an-operation-in-the-background.md)  
 Viene illustrato come eseguire un'operazione richiede molto tempo con la <xref:System.ComponentModel.BackgroundWorker> componente.  
  
 [Panoramica sul componente BackgroundWorker](backgroundworker-component-overview.md)  
 Fornisce argomenti che descrivono come usare il <xref:System.ComponentModel.BackgroundWorker> componente per le operazioni asincrone.
