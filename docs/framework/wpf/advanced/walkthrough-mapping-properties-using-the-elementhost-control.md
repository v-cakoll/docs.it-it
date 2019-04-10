---
title: 'Procedura dettagliata: Mapping di proprietà tramite il controllo ElementHost'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- ElementHost control [WPF], mapping properties
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
ms.openlocfilehash: 360f19e558f97e1807b329ad18e429fa893bbf86
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59300918"
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a>Procedura dettagliata: Mapping di proprietà tramite il controllo ElementHost

Questa procedura dettagliata illustra come usare il <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> proprietà a cui mappare [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] delle proprietà alle proprietà corrispondenti in un ambiente host [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elemento.

Le attività illustrate nella procedura dettagliata sono le seguenti:

-   Creazione del progetto.

-   Definizione di un nuovo mapping delle proprietà.

-   Definizione di un mapping delle proprietà predefinito.

-   Estensione di un mapping delle proprietà predefinito.

Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere [Mapping delle proprietà usando l'esempio di controllo ElementHost](https://go.microsoft.com/fwlink/?LinkID=160018).

Al termine, sarà possibile eseguire il mapping [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] proprietà corrispondente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le proprietà di un elemento ospitato.

## <a name="prerequisites"></a>Prerequisiti

Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:

-   Visual Studio 2017

## <a name="creating-the-project"></a>Creazione del progetto

### <a name="to-create-the-project"></a>Per creare il progetto

1. Creare un **App di Windows. Forms** progetto denominato `PropertyMappingWithElementHost`.

2. Nelle **Esplora soluzioni**, aggiungere i riferimenti ai seguenti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assembly.

    -   PresentationCore

    -   PresentationFramework

    -   WindowsBase

    -   WindowsFormsIntegration

3. Copiare il codice seguente nella parte superiore del `Form1` file di codice.

     [!code-csharp[PropertyMappingWithElementHost#10](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]

4. Aprire `Form1` in Progettazione Windows Form. Fare doppio clic sul form per aggiungere un gestore eventi per il <xref:System.Windows.Forms.Form.Load> evento.

5. Tornare alla finestra di progettazione Windows Form e aggiungere un gestore eventi per il form <xref:System.Windows.Forms.Control.Resize> evento. Per altre informazioni, vedere [Procedura: Creare i gestori eventi utilizzando la finestra di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).

6. Dichiarare un <xref:System.Windows.Forms.Integration.ElementHost> campo il `Form1` classe.

     [!code-csharp[PropertyMappingWithElementHost#16](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]

## <a name="defining-new-property-mappings"></a>La definizione di nuovi mapping delle proprietà

Il <xref:System.Windows.Forms.Integration.ElementHost> controllo fornisce mapping di proprietà predefiniti diversi. È possibile aggiungere un nuovo mapping delle proprietà chiamando i <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> metodo sul <xref:System.Windows.Forms.Integration.ElementHost> del controllo <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.

### <a name="to-define-new-property-mappings"></a>Per definire nuovi mapping delle proprietà

1. Copiare il codice seguente nella definizione per il `Form1` classe.

     [!code-csharp[PropertyMappingWithElementHost#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]

     Il `AddMarginMapping` metodo aggiunge un nuovo mapping per il <xref:System.Windows.Forms.Control.Margin%2A> proprietà.

     Il `OnMarginChange` metodo converte il <xref:System.Windows.Forms.Control.Margin%2A> proprietà per il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> proprietà.

2. Copiare il codice seguente nella definizione per il `Form1` classe.

     [!code-csharp[PropertyMappingWithElementHost#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]

     Il `AddRegionMapping` metodo aggiunge un nuovo mapping per il <xref:System.Windows.Forms.Control.Region%2A> proprietà.

     Il `OnRegionChange` metodo converte il <xref:System.Windows.Forms.Control.Region%2A> proprietà per il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> proprietà.

     Il `Form1_Resize` metodo gestisce il form <xref:System.Windows.Forms.Control.Resize> eventi e le dimensioni dell'area di ritaglio per adattarlo all'elemento ospitato.

## <a name="removing-a-default-property-mapping"></a>Rimozione di un mapping delle proprietà predefinito

Rimuovere un mapping delle proprietà predefinito chiamando il <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> metodo sul <xref:System.Windows.Forms.Integration.ElementHost> del controllo <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.

### <a name="to-remove-a-default-property-mapping"></a>Per rimuovere un mapping delle proprietà predefinito

-   Copiare il codice seguente nella definizione per il `Form1` classe.

     [!code-csharp[PropertyMappingWithElementHost#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]

     Il `RemoveCursorMapping` metodo elimina il mapping predefinito per il <xref:System.Windows.Forms.Control.Cursor%2A> proprietà.

## <a name="extending-a-default-property-mapping"></a>Estensione di un mapping delle proprietà predefinito

È possibile usare un mapping delle proprietà predefinito ed estenderlo con un mapping personalizzato.

### <a name="to-extend-a-default-property-mapping"></a>Per estendere un mapping delle proprietà predefinito

-   Copiare il codice seguente nella definizione per il `Form1` classe.

     [!code-csharp[PropertyMappingWithElementHost#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]

     Il `ExtendBackColorMapping` metodo aggiunge un convertitore di proprietà personalizzata esistente <xref:System.Windows.Forms.Control.BackColor%2A> mapping delle proprietà.

     Il `OnBackColorChange` metodo assegna un'immagine specifica del controllo ospitato <xref:System.Windows.Controls.Control.Background%2A> proprietà. Il `OnBackColorChange` metodo viene chiamato dopo aver applicato il mapping delle proprietà predefinito.

## <a name="initialize-your-property-mappings"></a>Inizializzare i mapping delle proprietà

1. Copiare il codice seguente nella definizione per il `Form1` classe.

     [!code-csharp[PropertyMappingWithElementHost#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]

     Il `Form1_Load` metodo consente di gestire il <xref:System.Windows.Forms.Form.Load> eventi ed esegue l'inizializzazione seguente.

    -   Crea una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> elemento.

    -   Chiama i metodi definiti in precedenza nella procedura dettagliata per impostare i mapping delle proprietà.

    -   Assegna i valori iniziali alle proprietà mappate.

2. Premere F5 per compilare ed eseguire l'applicazione.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Mapping di proprietà di Windows Form e WPF](windows-forms-and-wpf-property-mapping.md)
- [Progettare XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Procedura dettagliata: Hosting di un controllo composito WPF in Windows Form](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)