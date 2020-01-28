---
title: Funzionalità di trascinamento della selezione
ms.date: 03/30/2017
helpviewer_keywords:
- drag and drop [Windows Forms], Windows Forms
- Windows Forms, drag and drop
ms.assetid: 65cd2c03-8782-474e-b958-cbe43eeb902c
ms.openlocfilehash: 603dc158719c0b11def4386eb24a33f235cf3a42
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732754"
---
# <a name="drag-and-drop-functionality-in-windows-forms"></a>Funzionalità di trascinamento della selezione in Windows Form
Windows Forms include un set di metodi, eventi e classi che implementano il comportamento di trascinamento e rilascio. Questo argomento fornisce una panoramica del supporto per il trascinamento della selezione in Windows Forms.  Vedere anche [operazioni di trascinamento della selezione e supporto degli Appunti](./advanced/drag-and-drop-operations-and-clipboard-support.md).  
  
## <a name="performing-drag-and-drop-operations"></a>Esecuzione di operazioni di trascinamento della selezione  
 Per eseguire un'operazione di trascinamento e rilascio, usare il metodo <xref:System.Windows.Forms.Control.DoDragDrop%2A> della classe <xref:System.Windows.Forms.Control>. Per altre informazioni su come viene eseguita un'operazione di trascinamento e rilascio, vedere <xref:System.Windows.Forms.Control.DoDragDrop%2A>. Per ottenere il rettangolo sul quale deve essere trascinato il puntatore del mouse prima che inizi un'operazione di trascinamento della selezione, usare la proprietà <xref:System.Windows.Forms.SystemInformation.DragSize%2A> della classe <xref:System.Windows.Forms.SystemInformation>.  
  
## <a name="events-related-to-drag-and-drop-operations"></a>Eventi relativi a operazioni di trascinamento e rilascio  
 Esistono due categorie di eventi in un'operazione di trascinamento della selezione: eventi che si verificano sulla destinazione corrente ed eventi che si verificano sull'origine dell'operazione di trascinamento della selezione.  
  
### <a name="events-on-the-current-target"></a>Eventi sulla destinazione corrente  
 La tabella seguente illustra gli eventi che si verificano sulla destinazione corrente di un'operazione di trascinamento della selezione.  
  
|Evento del mouse|Descrizione|  
|-----------------|-----------------|  
|<xref:System.Windows.Forms.Control.DragEnter>|Questo evento si verifica quando un oggetto viene trascinato all'interno dei limiti del controllo. Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.DragEventArgs>.|  
|<xref:System.Windows.Forms.Control.DragOver>|Questo evento si verifica quando un oggetto viene trascinato mentre il puntatore del mouse è all'interno dei limiti del controllo. Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.DragEventArgs>.|  
|<xref:System.Windows.Forms.Control.DragDrop>|Questo evento si verifica quando viene completata un'operazione di trascinamento della selezione. Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.DragEventArgs>.|  
|<xref:System.Windows.Forms.Control.DragLeave>|Questo evento si verifica quando un oggetto viene trascinato all'esterno dei limiti del controllo. Il gestore di questo evento riceve un argomento di tipo <xref:System.EventArgs>.|  
  
 La classe <xref:System.Windows.Forms.DragEventArgs> fornisce la posizione del puntatore del mouse, lo stato corrente dei pulsanti del mouse e dei tasti di modifica della tastiera, i dati trascinati e i valori dell'enumerazione <xref:System.Windows.Forms.DragDropEffects> che specificano le operazioni consentite dall'origine dell'evento di trascinamento e l'effetto del rilascio sulla destinazione per l'operazione.  
  
### <a name="events-on-the-source"></a>Eventi sull'origine  
 La tabella seguente illustra gli eventi che si verificano sull'origine di un'operazione di trascinamento e rilascio.  
  
|Evento del mouse|Descrizione|  
|-----------------|-----------------|  
|<xref:System.Windows.Forms.Control.GiveFeedback>|Questo evento si verifica durante un'operazione di trascinamento. Permette di fornire all'utente un'indicazione visiva dell'operazione di trascinamento della selezione in corso, ad esempio cambiando l'aspetto del puntatore del mouse. Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.GiveFeedbackEventArgs>.|  
|<xref:System.Windows.Forms.Control.QueryContinueDrag>|Questo evento si verifica durante un'operazione di trascinamento della selezione e consente all'origine del trascinamento di determinare se l'operazione deve essere annullata. Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.QueryContinueDragEventArgs>.|  
  
 La classe <xref:System.Windows.Forms.QueryContinueDragEventArgs> fornisce lo stato corrente dei pulsanti del mouse e dei tasti di modifica della tastiera, un valore che specifica se è stato premuto il tasto ESC e un valore dell'enumerazione <xref:System.Windows.Forms.DragAction> che è possibile impostare per specificare se l'operazione di trascinamento della selezione deve continuare.  
  
## <a name="see-also"></a>Vedere anche

- [Input del mouse in un'applicazione Windows Forms](mouse-input-in-a-windows-forms-application.md)
