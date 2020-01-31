---
title: "Procedura dettagliata: mapping di proprietà tramite l'elemento WindowsFormsHost"
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
ms.openlocfilehash: c076937d6431adf1750793d47ece88dc82edf95c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794110"
---
# <a name="walkthrough-mapping-properties-using-the-windowsformshost-element"></a>Procedura dettagliata: mapping di proprietà tramite l'elemento WindowsFormsHost

In questa procedura dettagliata viene illustrato come utilizzare la proprietà <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> per eseguire il mapping delle proprietà [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] alle proprietà corrispondenti in un controllo Windows Forms ospitato.

Le attività illustrate nella procedura dettagliata sono le seguenti:

- Creazione del progetto.

- Definizione del layout dell'applicazione.

- Definizione di un nuovo mapping delle proprietà.

- Definizione di un mapping delle proprietà predefinito.

- Sostituzione di un mapping delle proprietà predefinito.

- Estensione di un mapping delle proprietà predefinito.

Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere [mapping delle proprietà tramite l'esempio WindowsFormsHost](https://go.microsoft.com/fwlink/?LinkID=160019).

Al termine, sarà possibile eseguire il mapping delle proprietà [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] alle proprietà corrispondenti in un controllo Windows Forms ospitato.

## <a name="prerequisites"></a>Prerequisiti

Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:

- Visual Studio 2017

## <a name="create-and-set-up-the-project"></a>Creare e configurare il progetto

1. Creare un progetto di **applicazione WPF** denominato `PropertyMappingWithWfhSample`.

2. In **Esplora soluzioni**aggiungere un riferimento all'assembly WindowsFormsIntegration, denominato WindowsFormsIntegration. dll.

3. In **Esplora soluzioni**aggiungere riferimenti agli assembly System. Drawing e System. Windows. Forms.

## <a name="defining-the-application-layout"></a>Definizione del layout dell'applicazione

L'applicazione basata su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]usa l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> per ospitare un controllo di Windows Forms.

### <a name="to-define-the-application-layout"></a>Per definire il layout dell'applicazione

1. Aprire Window1. XAML in WPF Designer.

2. Sostituire il codice esistente con quello seguente.

     [!code-xaml[PropertyMappingWithWfhSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]

3. Aprire Window1.xaml.cs nell'editor di codice.

4. Nella parte superiore del file importare gli spazi dei nomi seguenti.

     [!code-csharp[PropertyMappingWithWfhSample#20](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]

## <a name="defining-a-new-property-mapping"></a>Definizione di un nuovo mapping delle proprietà

L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> fornisce diversi mapping di proprietà predefiniti. Per aggiungere un nuovo mapping della proprietà, chiamare il metodo <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> sul <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>dell'elemento del <xref:System.Windows.Forms.Integration.WindowsFormsHost>.

### <a name="to-define-a-new-property-mapping"></a>Per definire un nuovo mapping delle proprietà

- Copiare il codice seguente nella definizione della classe `Window1`.

     [!code-csharp[PropertyMappingWithWfhSample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]

     Il metodo `AddClipMapping` aggiunge un nuovo mapping per la proprietà <xref:System.Windows.UIElement.Clip%2A>.

     Il metodo `OnClipChange` converte la proprietà <xref:System.Windows.UIElement.Clip%2A> nella proprietà<xref:System.Windows.Forms.Control.Region%2A> Windows Forms.

     Il metodo `Window1_SizeChanged` gestisce l'evento <xref:System.Windows.FrameworkElement.SizeChanged> della finestra e ridimensiona l'area di ridimensionamento per adattarla alla finestra dell'applicazione.

## <a name="removing-a-default-property-mapping"></a>Rimozione di un mapping delle proprietà predefinito

Rimuovere un mapping di proprietà predefinito chiamando il metodo <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> sul <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>dell'elemento del <xref:System.Windows.Forms.Integration.WindowsFormsHost>.

### <a name="to-remove-a-default-property-mapping"></a>Per rimuovere un mapping delle proprietà predefinito

- Copiare il codice seguente nella definizione della classe `Window1`.

     [!code-csharp[PropertyMappingWithWfhSample#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]

     Il metodo `RemoveCursorMapping` Elimina il mapping predefinito per la proprietà <xref:System.Windows.FrameworkElement.Cursor%2A>.

## <a name="replacing-a-default-property-mapping"></a>Sostituzione di un mapping delle proprietà predefinito

Sostituire un mapping di proprietà predefinito rimuovendo il mapping predefinito e chiamando il metodo <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> sul <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>dell'elemento del <xref:System.Windows.Forms.Integration.WindowsFormsHost>.

### <a name="to-replace-a-default-property-mapping"></a>Per sostituire un mapping delle proprietà predefinito

- Copiare il codice seguente nella definizione della classe `Window1`.

     [!code-csharp[PropertyMappingWithWfhSample#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]

     Il metodo `ReplaceFlowDirectionMapping` sostituisce il mapping predefinito per la proprietà <xref:System.Windows.FrameworkElement.FlowDirection%2A>.

     Il metodo `OnFlowDirectionChange` converte la proprietà <xref:System.Windows.FrameworkElement.FlowDirection%2A> nella proprietà<xref:System.Windows.Forms.Control.RightToLeft%2A> Windows Forms.

     Il metodo `cb_CheckedChanged` gestisce l'evento <xref:System.Windows.Forms.CheckBox.CheckedChanged> sul controllo <xref:System.Windows.Forms.CheckBox>. Assegna la proprietà <xref:System.Windows.FrameworkElement.FlowDirection%2A> in base al valore della proprietà <xref:System.Windows.Forms.CheckBox.CheckState%2A>

## <a name="extending-a-default-property-mapping"></a>Estensione di un mapping delle proprietà predefinito

È possibile usare un mapping delle proprietà predefinito ed estenderlo con un mapping personalizzato.

### <a name="to-extend-a-default-property-mapping"></a>Per estendere un mapping delle proprietà predefinito

- Copiare il codice seguente nella definizione della classe `Window1`.

     [!code-csharp[PropertyMappingWithWfhSample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]

     Il metodo `ExtendBackgroundMapping` aggiunge un convertitore di proprietà personalizzato al mapping della proprietà <xref:System.Windows.Controls.Control.Background%2A> esistente.

     Il metodo `OnBackgroundChange` assegna un'immagine specifica alla proprietà <xref:System.Windows.Forms.Control.BackgroundImage%2A> del controllo ospitato. Il metodo `OnBackgroundChange` viene chiamato dopo l'applicazione del mapping di proprietà predefinito.

## <a name="initializing-your-property-mappings"></a>Inizializzazione dei mapping delle proprietà

Configurare i mapping delle proprietà chiamando i metodi descritti in precedenza nel gestore eventi <xref:System.Windows.FrameworkElement.Loaded>.

### <a name="to-initialize-your-property-mappings"></a>Per inizializzare i mapping delle proprietà

1. Copiare il codice seguente nella definizione della classe `Window1`.

     [!code-csharp[PropertyMappingWithWfhSample#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]

     Il metodo `WindowLoaded` gestisce l'evento <xref:System.Windows.FrameworkElement.Loaded> ed esegue l'inizializzazione seguente.

    - Crea una Windows Forms controllo<xref:System.Windows.Forms.CheckBox>.

    - Chiama i metodi definiti in precedenza nella procedura dettagliata per impostare i mapping delle proprietà.

    - Assegna i valori iniziali alle proprietà mappate.

2. Premere **F5** per compilare ed eseguire l'applicazione. Fare clic sulla casella di controllo per visualizzare l'effetto del mapping del <xref:System.Windows.FrameworkElement.FlowDirection%2A>. Quando si seleziona la casella di controllo, il layout inverte l'orientamento da sinistra a destra.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Mapping di proprietà di Windows Form e WPF](windows-forms-and-wpf-property-mapping.md)
- [Progettare XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Procedura dettagliata: hosting di controlli Windows Form in WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
