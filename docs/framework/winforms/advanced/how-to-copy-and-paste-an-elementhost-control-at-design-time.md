---
title: 'Procedura: copiare e incollare un controllo ElementHost in fase di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ffe7d050de84eba8c7962a62a8604a72f78bc2bc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-copy-and-paste-an-elementhost-control-at-design-time"></a>Procedura: copiare e incollare un controllo ElementHost in fase di progettazione
Questa procedura viene illustrato come copiare un controllo Windows Presentation Foundation (WPF) in un Windows Form.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-copy-and-paste-an-elementhost-control-at-design-time"></a>Copiare e incollare un controllo ElementHost in fase di progettazione  
  
1.  Aggiungere un nuovo controllo WPF <xref:System.Windows.Controls.UserControl> al progetto Windows Form. Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`. Per ulteriori informazioni, vedere [procedura dettagliata: creazione di nuovo contenuto WPF in Windows Form in fase di progettazione](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  Nel **proprietà** finestra, impostare il valore della <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> le proprietà di `UserControl1` a `200`.  
  
3.  Impostare il valore della proprietà <xref:System.Windows.Controls.Control.Background%2A> su `Blue`.  
  
4.  Compilare il progetto.  
  
5.  Aprire `Form1` in Progettazione Windows Form.  
  
6.  Dal **della casella degli strumenti**, trascinare un'istanza di `UserControl1` nel form.  
  
     L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.  
  
7.  Con `elementHost1` selezionato, premere CTRL+C per copiarlo negli Appunti.  
  
8.  Premere CTRL + V per incollare il controllo copiato nel form.  
  
     Un nuovo <xref:System.Windows.Forms.Integration.ElementHost> controllo denominato `elementHost2` viene creata nel form.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Procedura dettagliata: Copiare e incollare un controllo ElementHost in Windows Form separati](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 [Migrazione e interoperabilità](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [Uso di controlli WPF](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [WPF Designer](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)
