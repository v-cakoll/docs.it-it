---
title: 'Procedura dettagliata: Assegnazione del contenuto WPF in Windows Form in fase di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
ms.openlocfilehash: b4efef869c96ddb4e58445e45ecad12b5658f9f4
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59343350"
---
# <a name="walkthrough-assigning-wpf-content-on-windows-forms-at-design-time"></a>Procedura dettagliata: Assegnazione del contenuto WPF in Windows Form in fase di progettazione
Questa procedura dettagliata illustra come selezionare i tipi di controllo Windows Presentation Foundation (WPF) da visualizzare nel form. È possibile selezionare qualsiasi tipo di controllo WPF incluso nel progetto.

 Questa procedura dettagliata prevede l'esecuzione delle attività seguenti:

-   Creare il progetto.

-   Creare i tipi di controllo WPF.

-   Selezionare i controlli WPF.

> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:  
  
-   Visual Studio 2012.  
  
## <a name="creating-the-project"></a>Creazione del progetto  
 Il primo passaggio consiste nella creazione del progetto Windows Form.  
  
> [!NOTE]
>  Con il contenuto WPF sono supportati solo progetti C# e Visual Basic.  
  
#### <a name="to-create-the-project"></a>Per creare il progetto  
  
-   Creare un nuovo progetto Windows Forms Application in Visual Basic o Visual c# denominato `SelectingWpfContent`.  
  
## <a name="creating-the-wpf-control-types"></a>Creazione di tipi di controllo WPF  
 Dopo avere aggiunto i tipi di controllo WPF al progetto, è possibile includerli in controlli <xref:System.Windows.Forms.Integration.ElementHost> diversi.  
  
#### <a name="to-create-wpf-control-types"></a>Per creare i tipi di controllo WPF  
  
1. Aggiungere un nuovo progetto WPF <xref:System.Windows.Controls.UserControl> alla soluzione. Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`. Per altre informazioni, vedere [Procedura dettagliata: Creare nuovo contenuto WPF in Windows Form in fase di progettazione](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2. In visualizzazione Progettazione verificare che `UserControl1` sia selezionato. Per altre informazioni, vedere [Procedura: Selezionare e spostare gli elementi nell'area di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).  
  
3. Nel **le proprietà** finestra, impostare il valore della <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> le proprietà da `200`.  
  
4. Aggiungere un <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> il controllo al <xref:System.Windows.Controls.UserControl> e impostare il valore della <xref:System.Windows.Controls.TextBox.Text%2A> proprietà **contenuto ospitato**.  
  
5. Aggiungere un secondo controllo WPF <xref:System.Windows.Controls.UserControl> al progetto. Usare il nome predefinito per il tipo di controllo, `UserControl2.xaml`.  
  
6. Nel **le proprietà** finestra, impostare il valore della <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> le proprietà da `200`.  
  
7. Aggiungere un <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> il controllo al <xref:System.Windows.Controls.UserControl> e impostare il valore della <xref:System.Windows.Controls.TextBox.Text%2A> proprietà **Hosted Content 2**.  
  
 **Nota** In generale, è opportuno ospitare contenuto WPF più sofisticato. Il controllo <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> è qui usato a solo a titolo esemplificativo.  
  
1. Compilare il progetto.  
  
## <a name="selecting-wpf-controls"></a>Selezione di controlli WPF  
 È possibile assegnare contenuto WPF diverso a un controllo <xref:System.Windows.Forms.Integration.ElementHost> che include già contenuto.  
  
#### <a name="to-select-wpf-controls"></a>Per selezionare i controlli WPF  
  
1. Aprire `Form1` in Progettazione Windows Form.  
  
2. Nel **casella degli strumenti**, fare doppio clic su `UserControl1` per creare un'istanza di `UserControl1` nel form.  
  
     L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.  
  
3. Nel pannello smart tag per `elementHost1`, aprire il **selezione contenuto ospitato** elenco a discesa.  
  
4. Selezionare **UserControl2** dall'elenco a discesa.  
  
     Il controllo `elementHost1` include ora un'istanza del tipo `UserControl2`.  
  
5. Nel **delle proprietà** finestra, verificare che il <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> è impostata su **UserControl2**.  
  
6. Dal **casella degli strumenti**, nella **interoperabilità WPF** gruppo, trascinare un <xref:System.Windows.Forms.Integration.ElementHost> controllo nel form.  
  
     Il nome predefinito del nuovo controllo è `elementHost2`.  
  
7. Nel pannello smart tag per `elementHost2`, aprire il **selezione contenuto ospitato** elenco a discesa.  
  
8. Selezionare **UserControl1** nell'elenco a discesa.  
  
9. Il controllo `elementHost2` include ora un'istanza del tipo `UserControl1`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migrazione e interoperabilità](../../wpf/advanced/migration-and-interoperability.md)
- [Utilizzo di controlli WPF](using-wpf-controls.md)
- [Progettare XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
