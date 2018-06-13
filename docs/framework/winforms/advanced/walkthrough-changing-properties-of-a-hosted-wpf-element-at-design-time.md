---
title: 'Procedura dettagliata: modifica delle proprietà di un elemento WPF ospitato in fase di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], changing properties at design time
- Windows Forms, changing properties of WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- interoperability [WPF]
ms.assetid: a1f7a90c-0bbb-4781-8c3c-8cc8bef2488d
ms.openlocfilehash: d17273f52d0cef118b79fef03af72522f6677073
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529821"
---
# <a name="walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time"></a>Procedura dettagliata: modifica delle proprietà di un elemento WPF ospitato in fase di progettazione
Questa procedura dettagliata mostra come cambiare i valori delle proprietà di un controllo Windows Presentation Foundation (WPF) incluso in un Windows Form.  
  
 Questa procedura dettagliata prevede l'esecuzione delle attività seguenti:  
  
-   Creare il progetto.  
  
-   Creare il controllo WPF.  
  
-   Inserire i controlli WPF in Windows Form  
  
-   Usare WPF Designer per Visual Studio per cambiare i valori delle proprietà.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)].  
  
## <a name="creating-the-project"></a>Creazione del progetto  
 Il primo passaggio consiste nella creazione del progetto Windows Form.  
  
> [!NOTE]
>  Con il contenuto WPF sono supportati solo progetti C# e Visual Basic.  
  
#### <a name="to-create-the-project"></a>Per creare il progetto  
  
-   Creare un nuovo progetto applicazione Windows Forms in Visual Basic o Visual c# denominato `WpfHost`.  
  
## <a name="creating-the-wpf-control"></a>Creazione del controllo WPF  
 Dopo avere aggiunto un controllo WPF al progetto, è possibile disporlo sul form.  
  
#### <a name="to-create-wpf-controls"></a>Per creare controlli WPF  
  
1.  Aggiungere un nuovo <xref:System.Windows.Controls.UserControl> WPF al progetto. Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`. Per ulteriori informazioni, vedere [procedura dettagliata: creazione di nuovo contenuto WPF in Windows Form in fase di progettazione](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  Nel **proprietà** finestra, impostare il valore della <xref:System.Windows.Controls.Control.Background%2A> proprietà `Blue`.  
  
3.  Compilare il progetto.  
  
## <a name="changing-property-values-on-the-wpf-control"></a>Modifica dei valori delle proprietà nel controllo WPF  
 Lo smart tag <xref:System.Windows.Forms.Integration.ElementHost> facilita la modifica delle proprietà del contenuto WPF ospitato usando WPF Designer.  
  
#### <a name="to-host-a-wpf-control"></a>Per includere un controllo WPF  
  
1.  Aprire `Form1` in Progettazione Windows Form.  
  
2.  Nel **della casella degli strumenti**nella **controlli utente WPF** scheda, fare doppio clic su `UserControl1` per creare un'istanza di `UserControl1` nel form.  
  
     L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.  
  
3.  Nel **ElementHost Tasks** pannello smart tag, seleziona **modifica contenuto ospitato**.  
  
     UserControl1.xaml viene aperto in WPF Designer.  
  
4.  Nel **proprietà** finestra, impostare il valore della <xref:System.Windows.Controls.Control.Background%2A> proprietà `Red`.  
  
5.  Ricompilare il progetto.  
  
6.  Aprire `Form1` in Progettazione Windows Form.  
  
     L'istanza di `UserControl1` presenta uno sfondo rosso.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Procedura: Agganciare e ancorare controlli figlio in un controllo TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [Procedura: Allineare un controllo ai bordi dei form in fase di progettazione](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 [Procedura dettagliata: Disposizione dei controlli in Windows Form usando guide di allineamento](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [Migrazione e interoperabilità](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [Uso di controlli WPF](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [WPF Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)
