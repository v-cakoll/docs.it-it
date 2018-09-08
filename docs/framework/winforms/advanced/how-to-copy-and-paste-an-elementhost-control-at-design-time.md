---
title: 'Procedura: copiare e incollare un controllo ElementHost in fase di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
ms.openlocfilehash: 43ebe50497df97511925bd2e413ab5b5988b7f57
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44210919"
---
# <a name="how-to-copy-and-paste-an-elementhost-control-at-design-time"></a>Procedura: copiare e incollare un controllo ElementHost in fase di progettazione
Questa procedura illustra come copiare un controllo Windows Presentation Foundation (WPF) in un Windows Form.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-copy-and-paste-an-elementhost-control-at-design-time"></a>Per copiare e incollare un controllo ElementHost in fase di progettazione  
  
1.  Aggiungere un nuovo controllo WPF <xref:System.Windows.Controls.UserControl> al progetto Windows Form. Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`. Per altre informazioni, vedere [procedura dettagliata: creazione di nuovo contenuto WPF in Windows Form in fase di progettazione](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  Nel **delle proprietà** finestra, impostare il valore della <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> le proprietà di `UserControl1` per `200`.  
  
3.  Impostare il valore della proprietà <xref:System.Windows.Controls.Control.Background%2A> su `Blue`.  
  
4.  Compilare il progetto.  
  
5.  Aprire `Form1` in Progettazione Windows Form.  
  
6.  Dal **casella degli strumenti**, trascinare un'istanza di `UserControl1` nel form.  
  
     L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.  
  
7.  Con `elementHost1` selezionato, premere CTRL+C per copiarlo negli Appunti.  
  
8.  Premere CTRL + V per incollare il controllo copiato nel form.  
  
     Una nuova <xref:System.Windows.Forms.Integration.ElementHost> controllo denominato `elementHost2` viene creato nel form.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Procedura dettagliata: Copiare e incollare un controllo ElementHost in Windows Form separati](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 [Migrazione e interoperabilità](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [Uso di controlli WPF](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [Progettare XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
