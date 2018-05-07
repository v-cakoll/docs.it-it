---
title: 'Procedura dettagliata: mapping delle proprietà tramite il controllo ElementHost'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- ElementHost control [WPF], mapping properties
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
ms.openlocfilehash: b5af1f45a0d01761358e83c890544ec1a11836e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a>Procedura dettagliata: mapping delle proprietà tramite il controllo ElementHost
Questa procedura dettagliata viene illustrato come utilizzare il <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> proprietà da mappare [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] proprietà alle proprietà corrispondenti di hosting [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elemento.  
  
 Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
-   Creazione del progetto.  
  
-   Definizione di un nuovo mapping delle proprietà.  
  
-   Definizione di un mapping delle proprietà predefinito.  
  
-   Estensione di un mapping delle proprietà predefinito.  
  
 Per un elenco di codice completo delle attività illustrate in questa procedura dettagliata, vedere [Mapping delle proprietà utilizzando l'esempio di controllo ElementHost](http://go.microsoft.com/fwlink/?LinkID=160018).  
  
 Al termine, sarà possibile eseguire il mapping di [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] proprietà corrispondente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le proprietà di un elemento ospitato.  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
## <a name="creating-the-project"></a>Creazione del progetto  
  
#### <a name="to-create-the-project"></a>Per creare il progetto  
  
1.  Creare un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] progetto di applicazione denominato `PropertyMappingWithElementHost`. Per altre informazioni, vedere [Procedura: Creare un nuovo progetto di applicazione Windows Form](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  In Esplora soluzioni aggiungere riferimenti ai seguenti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assembly.  
  
    -   PresentationCore  
  
    -   PresentationFramework  
  
    -   WindowsBase  
  
    -   WindowsFormsIntegration  
  
3.  Copiare il codice seguente all'inizio del `Form1` file di codice.  
  
     [!code-csharp[PropertyMappingWithElementHost#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]  
  
4.  Aprire `Form1` in Progettazione Windows Form. Fare doppio clic sul form per aggiungere un gestore eventi per il <xref:System.Windows.Forms.Form.Load> evento.  
  
5.  Tornare a Progettazione Windows Form e aggiungere un gestore eventi per il modulo <xref:System.Windows.Forms.Control.Resize> evento. Per ulteriori informazioni, vedere [procedura: creare di gestori di eventi utilizzando la finestra di progettazione](http://msdn.microsoft.com/library/8461e9b8-14e8-406f-936e-3726732b23d2).  
  
6.  Dichiarare un <xref:System.Windows.Forms.Integration.ElementHost> campo la `Form1` classe.  
  
     [!code-csharp[PropertyMappingWithElementHost#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]  
  
## <a name="defining-new-property-mappings"></a>Definizione di nuovi mapping di proprietà  
 Il <xref:System.Windows.Forms.Integration.ElementHost> controllo fornisce mapping di proprietà predefiniti diversi. Per aggiungere un nuovo mapping di proprietà, chiamare il <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> metodo il <xref:System.Windows.Forms.Integration.ElementHost> del controllo <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.  
  
#### <a name="to-define-new-property-mappings"></a>Per definire nuovi mapping di proprietà  
  
1.  Copiare il codice seguente nella definizione di `Form1` classe.  
  
     [!code-csharp[PropertyMappingWithElementHost#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]  
  
     Il `AddMarginMapping` metodo aggiunge un nuovo mapping per il <xref:System.Windows.Forms.Control.Margin%2A> proprietà.  
  
     Il `OnMarginChange` metodo converte il <xref:System.Windows.Forms.Control.Margin%2A> proprietà per il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> proprietà.  
  
2.  Copiare il codice seguente nella definizione di `Form1` classe.  
  
     [!code-csharp[PropertyMappingWithElementHost#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]  
  
     Il `AddRegionMapping` metodo aggiunge un nuovo mapping per il <xref:System.Windows.Forms.Control.Region%2A> proprietà.  
  
     Il `OnRegionChange` metodo converte il <xref:System.Windows.Forms.Control.Region%2A> proprietà per il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> proprietà.  
  
     Il `Form1_Resize` metodo gestisce il modulo <xref:System.Windows.Forms.Control.Resize> eventi e le dimensioni dell'area di ritaglio per adattarlo all'elemento ospitato.  
  
## <a name="removing-a-default-property-mapping"></a>Rimozione di un mapping delle proprietà predefinito  
 Rimuovere un mapping di proprietà predefinito chiamando il <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> metodo il <xref:System.Windows.Forms.Integration.ElementHost> del controllo <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.  
  
#### <a name="to-remove-a-default-property-mapping"></a>Per rimuovere un mapping delle proprietà predefinito  
  
-   Copiare il codice seguente nella definizione di `Form1` classe.  
  
     [!code-csharp[PropertyMappingWithElementHost#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]  
  
     Il `RemoveCursorMapping` metodo elimina il mapping predefinito per il <xref:System.Windows.Forms.Control.Cursor%2A> proprietà.  
  
## <a name="extending-a-default-property-mapping"></a>Estensione di un mapping delle proprietà predefinito  
 È possibile usare un mapping delle proprietà predefinito ed estenderlo con un mapping personalizzato.  
  
#### <a name="to-extend-a-default-property-mapping"></a>Per estendere un mapping delle proprietà predefinito  
  
-   Copiare il codice seguente nella definizione di `Form1` classe.  
  
     [!code-csharp[PropertyMappingWithElementHost#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]  
  
     Il `ExtendBackColorMapping` metodo aggiunge un convertitore di proprietà personalizzato esistente <xref:System.Windows.Forms.Control.BackColor%2A> mapping di proprietà.  
  
     Il `OnBackColorChange` metodo assegna un'immagine specifica del controllo ospitato <xref:System.Windows.Controls.Control.Background%2A> proprietà. Il `OnBackColorChange` metodo viene chiamato dopo aver applicato il mapping di proprietà predefinito.  
  
## <a name="initializing-your-property-mappings"></a>Inizializzazione dei mapping delle proprietà  
  
#### <a name="to-initialize-your-property-mappings"></a>Per inizializzare i mapping delle proprietà  
  
1.  Copiare il codice seguente nella definizione di `Form1` classe.  
  
     [!code-csharp[PropertyMappingWithElementHost#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]  
  
     Il `Form1_Load` metodo gestisca il <xref:System.Windows.Forms.Form.Load> evento ed esegue le inizializzazioni seguenti.  
  
    -   Crea un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> elemento.  
  
    -   Chiama i metodi definiti in precedenza nella procedura dettagliata per impostare i mapping delle proprietà.  
  
    -   Assegna i valori iniziali alle proprietà mappate.  
  
2.  Premere F5 per compilare ed eseguire l'applicazione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Mapping di proprietà di Windows Form e WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)  
 [WPF Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [Procedura dettaglia: hosting di un controllo WPF composito in Windows Form](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
