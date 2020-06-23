---
title: Ordine degli eventi
description: Scopri i dettagli relativi all'ordine degli eventi nel Windows Forms durante varie fasi importanti della durata delle applicazioni e dei controlli.
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], order of
- focus event order
- application shutdown event order
- sequence [Windows Forms], of events
- validation events [Windows Forms], order of
- application startup event order
ms.assetid: e81db09b-4453-437f-b78a-62d7cd5c9829
ms.openlocfilehash: b16d544d11500b2c684e87a915fc4b8eec071faa
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904338"
---
# <a name="order-of-events-in-windows-forms"></a>Ordine degli eventi in Windows Form
L'ordine in cui gli eventi vengono generati nelle applicazioni Windows Form è di particolare interesse per gli sviluppatori interessati alla gestione di ciascuno di questi eventi a turno. Quando una situazione richiede una precisa gestione degli eventi, ad esempio quando si riprogettano parti del form, è necessaria la conoscenza dell'ordine esatto in cui vengono generati gli eventi in fase di esecuzione. Questo argomento contiene alcune informazioni dettagliate sull'ordine degli eventi durante le varie fasi importanti nella durata delle applicazioni e dei controlli. Per dettagli specifici sull'ordine degli eventi di input del mouse, vedere [eventi del mouse in Windows Forms](mouse-events-in-windows-forms.md). Per una panoramica degli eventi in Windows Forms, vedere [Cenni preliminari sugli eventi](events-overview-windows-forms.md). Per informazioni dettagliate sulla composizione dei gestori eventi, vedere [Cenni preliminari sui gestori eventi](event-handlers-overview-windows-forms.md).  
  
## <a name="application-startup-and-shutdown-events"></a>Eventi di arresto e avvio dell'applicazione  
 Le classi<xref:System.Windows.Forms.Form> e <xref:System.Windows.Forms.Control> espongono un set di eventi correlati all'avvio e all'arresto dell'applicazione. Quando si avvia un'applicazione Windows Forms, gli eventi di avvio del form principale vengono generati nell'ordine seguente:  
  
- <xref:System.Windows.Forms.Control.HandleCreated?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Control.BindingContextChanged?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Control.VisibleChanged?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Activated?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Shown?displayProperty=nameWithType>  
  
 Quando un'applicazione viene chiusa, gli eventi di chiusura del form principale vengono generati nell'ordine seguente:  
  
- <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Closed?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.FormClosed?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Deactivate?displayProperty=nameWithType>  
  
 L'evento <xref:System.Windows.Forms.Application.ApplicationExit> della classe <xref:System.Windows.Forms.Application> viene generato dopo gli eventi di chiusura del form principale.  
  
> [!NOTE]
> Visual Basic 2005 include eventi di applicazioni aggiuntivi, come <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup?displayProperty=nameWithType> e <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown?displayProperty=nameWithType>.  
  
## <a name="focus-and-validation-events"></a>Eventi di convalida e relativi allo stato attivo  
 Quando si modifica lo stato attivo usando la tastiera (TAB, MAIUSC + TAB e così via), chiamando i metodi <xref:System.Windows.Forms.Control.Select%2A> o <xref:System.Windows.Forms.Control.SelectNextControl%2A> oppure impostando la proprietà <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> sul form corrente, gli eventi di attivazione della classe <xref:System.Windows.Forms.Control> si verificano nell'ordine seguente:  
  
- <xref:System.Windows.Forms.Control.Enter>  
  
- <xref:System.Windows.Forms.Control.GotFocus>  
  
- <xref:System.Windows.Forms.Control.Leave>  
  
- <xref:System.Windows.Forms.Control.Validating>  
  
- <xref:System.Windows.Forms.Control.Validated>  
  
- <xref:System.Windows.Forms.Control.LostFocus>  
  
 Quando si modifica lo stato attivo usando il mouse o chiamando il metodo <xref:System.Windows.Forms.Control.Focus%2A>, gli eventi di attivazione della classe <xref:System.Windows.Forms.Control> si verificano nell'ordine seguente:  
  
- <xref:System.Windows.Forms.Control.Enter>  
  
- <xref:System.Windows.Forms.Control.GotFocus>  
  
- <xref:System.Windows.Forms.Control.LostFocus>  
  
- <xref:System.Windows.Forms.Control.Leave>  
  
- <xref:System.Windows.Forms.Control.Validating>  
  
- <xref:System.Windows.Forms.Control.Validated>  
  
## <a name="see-also"></a>Vedere anche

- [Creazione di gestori eventi in Windows Form](creating-event-handlers-in-windows-forms.md)
