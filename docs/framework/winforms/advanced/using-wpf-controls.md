---
title: Utilizzo di controlli WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
ms.openlocfilehash: be925bdceea3dd01c568d85fe025d6e037066454
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47170470"
---
# <a name="using-wpf-controls"></a>Utilizzo di controlli WPF
È possibile usare i controlli Windows Presentation Foundation (WPF) nelle applicazioni basate su Windows Form. Anche se questi sono due tecnologie di visualizzazione diversa, si integrano perfettamente.  
  
 Finestra di progettazione Windows Form fornisce un ambiente di progettazione visiva per l'hosting di controlli Windows Presentation Foundation. Un controllo WPF è ospitato da un controllo Windows Form speciale denominato <xref:System.Windows.Forms.Integration.ElementHost>. Questo controllo consente il controllo WPF a partecipare al layout del form e di ricevere i messaggi della tastiera e mouse. In fase di progettazione, è possibile disporre di <xref:System.Windows.Forms.Integration.ElementHost> controllare esattamente come si farebbe qualsiasi controllo Windows Form.  
  
 È anche possibile usare i controlli Windows Form nelle applicazioni basate su WPF. Per altre informazioni, vedere [progettazione XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Copiare e incollare un controllo ElementHost in fase di progettazione](../../../../docs/framework/winforms/advanced/how-to-copy-and-paste-an-elementhost-control-at-design-time.md)  
 Illustra come copiare un controllo Windows Presentation Foundation in un Windows Form.  
  
 [Procedura dettagliata: Disposizione del contenuto WPF in Windows Form in fase di progettazione](../../../../docs/framework/winforms/advanced/walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)  
 Viene illustrato come usare le funzionalità di layout di Windows Form, ad esempio l'ancoraggio e le guide di allineamento, per disporre i controlli Windows Presentation Foundation.
  
 [Procedura dettagliata: Creazione di nuovo contenuto WPF in Windows Form in fase di progettazione](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)  
 Viene illustrato come creare un controllo Windows Presentation Foundation per l'uso nelle applicazioni basate su Windows Form.
  
 [Procedura dettagliata: Assegnazione del contenuto WPF in Windows Form in fase di progettazione](../../../../docs/framework/winforms/advanced/walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)  
 Viene illustrato come selezionare i tipi di controllo di Windows Presentation Foundation che si desidera visualizzare nel form.  
  
 [Procedura dettagliata: Applicazione di stili al contenuto WPF](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md)  
 Viene illustrato il flusso di lavoro tra la finestra di progettazione Windows Form e [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] per l'applicazione di stili ai controlli Windows Presentation Foundation.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 Descrive una classe che è possibile usare per ospitare i controlli Windows Presentation Foundation nelle applicazioni basate su Windows Form.  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 Descrive una classe che è possibile usare per ospitare i controlli Windows Form nell'applicazione basata su Windows Presentation Foundation.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Migrazione e interoperabilità](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 Viene descritta l'interazione tra le tecnologie di Windows Presentation Foundation e Windows Form.  
  
 [Progettare XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)  
 Descrive come progettare i controlli Windows Presentation Foundation in Visual Studio.
