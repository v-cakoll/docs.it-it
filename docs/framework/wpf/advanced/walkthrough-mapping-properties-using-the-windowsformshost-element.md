---
title: "Procedura dettagliata: mapping di proprietà tramite l'elemento WindowsFormsHost"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
ms.openlocfilehash: 771c0d972420b929ac757ced684de70d2dc7a58d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549302"
---
# <a name="walkthrough-mapping-properties-using-the-windowsformshost-element"></a>Procedura dettagliata: mapping di proprietà tramite l'elemento WindowsFormsHost
Questa procedura dettagliata viene illustrato come utilizzare il <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> proprietà da mappare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proprietà alle proprietà corrispondenti di hosting [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo.  
  
 Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
-   Creazione del progetto.  
  
-   Definizione del layout dell'applicazione.  
  
-   Definizione di un nuovo mapping delle proprietà.  
  
-   Definizione di un mapping delle proprietà predefinito.  
  
-   Sostituzione di un mapping delle proprietà predefinito.  
  
-   Estensione di un mapping delle proprietà predefinito.  
  
 Per un elenco di codice completo delle attività illustrate in questa procedura dettagliata, vedere [Mapping delle proprietà utilizzando l'esempio di elemento WindowsFormsHost](http://go.microsoft.com/fwlink/?LinkID=160019).  
  
 Al termine, sarà possibile eseguire il mapping di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proprietà alle proprietà corrispondenti di hosting [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo.  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
## <a name="creating-the-project"></a>Creazione del progetto  
  
#### <a name="to-create-and-set-up-the-project"></a>Per creare e impostare il progetto  
  
1.  Creare un progetto di applicazione WPF denominato `PropertyMappingWithWfhSample`.  
  
2.  In Esplora soluzioni aggiungere un riferimento all'assembly WindowsFormsIntegration, denominato WindowsFormsIntegration.  
  
3.  In Esplora soluzioni aggiungere riferimenti agli assembly System. Drawing e Forms.  
  
## <a name="defining-the-application-layout"></a>Definizione del layout dell'applicazione  
 Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-in base che utilizza il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento per ospitare un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo.  
  
#### <a name="to-define-the-application-layout"></a>Per definire il layout dell'applicazione  
  
1.  Aprire Window1. XAML nel [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
2.  Sostituire il codice esistente con quello seguente.  
  
     [!code-xaml[PropertyMappingWithWfhSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]  
  
3.  Aprire Window1.xaml.cs nell'editor di codice.  
  
4.  Nella parte superiore del file importare gli spazi dei nomi seguenti.  
  
     [!code-csharp[PropertyMappingWithWfhSample#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]  
  
## <a name="defining-a-new-property-mapping"></a>Definizione di un nuovo mapping delle proprietà  
 Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento fornisce mapping di proprietà predefiniti diversi. Per aggiungere un nuovo mapping di proprietà, chiamare il <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> metodo il <xref:System.Windows.Forms.Integration.WindowsFormsHost> dell'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.  
  
#### <a name="to-define-a-new-property-mapping"></a>Per definire un nuovo mapping delle proprietà  
  
-   Copiare il codice seguente nella definizione di `Window1` classe.  
  
     [!code-csharp[PropertyMappingWithWfhSample#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]  
  
     Il `AddClipMapping` metodo aggiunge un nuovo mapping per il <xref:System.Windows.UIElement.Clip%2A> proprietà.  
  
     Il `OnClipChange` metodo converte il <xref:System.Windows.UIElement.Clip%2A> proprietà per il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.Region%2A> proprietà.  
  
     Il `Window1_SizeChanged` metodo consente di gestire la finestra <xref:System.Windows.FrameworkElement.SizeChanged> eventi e le dimensioni dell'area di ritaglio per adattarlo alla finestra dell'applicazione.  
  
## <a name="removing-a-default-property-mapping"></a>Rimozione di un mapping delle proprietà predefinito  
 Rimuovere un mapping di proprietà predefinito chiamando il <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> metodo il <xref:System.Windows.Forms.Integration.WindowsFormsHost> dell'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.  
  
#### <a name="to-remove-a-default-property-mapping"></a>Per rimuovere un mapping delle proprietà predefinito  
  
-   Copiare il codice seguente nella definizione di `Window1` classe.  
  
     [!code-csharp[PropertyMappingWithWfhSample#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]  
  
     Il `RemoveCursorMapping` metodo elimina il mapping predefinito per il <xref:System.Windows.FrameworkElement.Cursor%2A> proprietà.  
  
## <a name="replacing-a-default-property-mapping"></a>Sostituzione di un mapping delle proprietà predefinito  
 Sostituire un mapping di proprietà predefinito rimuovendo il mapping predefinito e la chiamata di <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> metodo il <xref:System.Windows.Forms.Integration.WindowsFormsHost> dell'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.  
  
#### <a name="to-replace-a-default-property-mapping"></a>Per sostituire un mapping delle proprietà predefinito  
  
-   Copiare il codice seguente nella definizione di `Window1` classe.  
  
     [!code-csharp[PropertyMappingWithWfhSample#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]  
  
     Il `ReplaceFlowDirectionMapping` metodo sostituisce il mapping predefinito per il <xref:System.Windows.FrameworkElement.FlowDirection%2A> proprietà.  
  
     Il `OnFlowDirectionChange` metodo converte il <xref:System.Windows.FrameworkElement.FlowDirection%2A> proprietà per il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.RightToLeft%2A> proprietà.  
  
     Il `cb_CheckedChanged` metodo gestisca il <xref:System.Windows.Forms.CheckBox.CheckedChanged> evento il <xref:System.Windows.Forms.CheckBox> controllo. Assegna il <xref:System.Windows.FrameworkElement.FlowDirection%2A> proprietà in base al valore del <xref:System.Windows.Forms.CheckBox.CheckState%2A> proprietà  
  
## <a name="extending-a-default-property-mapping"></a>Estensione di un mapping delle proprietà predefinito  
 È possibile usare un mapping delle proprietà predefinito ed estenderlo con un mapping personalizzato.  
  
#### <a name="to-extend-a-default-property-mapping"></a>Per estendere un mapping delle proprietà predefinito  
  
-   Copiare il codice seguente nella definizione di `Window1` classe.  
  
     [!code-csharp[PropertyMappingWithWfhSample#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]  
  
     Il `ExtendBackgroundMapping` metodo aggiunge un convertitore di proprietà personalizzato esistente <xref:System.Windows.Controls.Control.Background%2A> mapping di proprietà.  
  
     Il `OnBackgroundChange` metodo assegna un'immagine specifica del controllo ospitato <xref:System.Windows.Forms.Control.BackgroundImage%2A> proprietà. Il `OnBackgroundChange` metodo viene chiamato dopo aver applicato il mapping di proprietà predefinito.  
  
## <a name="initializing-your-property-mappings"></a>Inizializzazione dei mapping delle proprietà  
 Impostare i mapping di proprietà chiamando i metodi descritti in precedenza <xref:System.Windows.FrameworkElement.Loaded> gestore dell'evento.  
  
#### <a name="to-initialize-your-property-mappings"></a>Per inizializzare i mapping delle proprietà  
  
1.  Copiare il codice seguente nella definizione di `Window1` classe.  
  
     [!code-csharp[PropertyMappingWithWfhSample#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]  
  
     Il `WindowLoaded` metodo gestisca il <xref:System.Windows.FrameworkElement.Loaded> evento ed esegue le inizializzazioni seguenti.  
  
    -   Crea un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.CheckBox> controllo.  
  
    -   Chiama i metodi definiti in precedenza nella procedura dettagliata per impostare i mapping delle proprietà.  
  
    -   Assegna i valori iniziali alle proprietà mappate.  
  
2.  Premere F5 per compilare ed eseguire l'applicazione. Fare clic sulla casella di controllo per visualizzare l'effetto del <xref:System.Windows.FrameworkElement.FlowDirection%2A> mapping. Quando si seleziona la casella di controllo, il layout inverte l'orientamento da sinistra a destra.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Mapping di proprietà di Windows Form e WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)  
 [WPF Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [Procedura dettagliata: hosting di controlli Windows Form in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)
