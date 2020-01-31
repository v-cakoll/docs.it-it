---
title: 'Procedura dettagliata: mapping delle proprietà tramite il controllo ElementHost'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- ElementHost control [WPF], mapping properties
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
ms.openlocfilehash: 7ff4ff607ab70b55cda1e2c4736ff773d4907a22
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794123"
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a>Procedura dettagliata: mapping delle proprietà tramite il controllo ElementHost

In questa procedura dettagliata viene illustrato come utilizzare la proprietà <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> per eseguire il mapping delle proprietà Windows Forms alle proprietà corrispondenti in un elemento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ospitato.

Le attività illustrate nella procedura dettagliata sono le seguenti:

- Creazione del progetto.

- Definizione di un nuovo mapping delle proprietà.

- Definizione di un mapping delle proprietà predefinito.

- Estensione di un mapping delle proprietà predefinito.

Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere [mapping delle proprietà tramite l'esempio di controllo ElementHost](https://go.microsoft.com/fwlink/?LinkID=160018).

Al termine, sarà possibile eseguire il mapping delle proprietà di Windows Forms alle proprietà [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] corrispondenti su un elemento ospitato.

## <a name="prerequisites"></a>Prerequisiti

Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:

- Visual Studio 2017

## <a name="creating-the-project"></a>Creazione del progetto

### <a name="to-create-the-project"></a>Per creare il progetto

1. Creare un progetto di **App Windows Forms** denominato `PropertyMappingWithElementHost`.

2. In **Esplora soluzioni**aggiungere riferimenti agli assembly [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] seguenti.

    - PresentationCore

    - PresentationFramework

    - WindowsBase

    - WindowsFormsIntegration

3. Copiare il codice seguente nella parte superiore del file di codice `Form1`.

     [!code-csharp[PropertyMappingWithElementHost#10](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]

4. Aprire `Form1` in Progettazione Windows Form. Fare doppio clic sul form per aggiungere un gestore eventi per l'evento <xref:System.Windows.Forms.Form.Load>.

5. Tornare alla Progettazione Windows Form e aggiungere un gestore eventi per l'evento <xref:System.Windows.Forms.Control.Resize> del modulo. Per altre informazioni, vedere [procedura: creare gestori eventi tramite la finestra di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).

6. Dichiarare un campo <xref:System.Windows.Forms.Integration.ElementHost> nella classe `Form1`.

     [!code-csharp[PropertyMappingWithElementHost#16](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]

## <a name="defining-new-property-mappings"></a>Definizione di nuovi mapping di proprietà

Il controllo <xref:System.Windows.Forms.Integration.ElementHost> fornisce diversi mapping di proprietà predefiniti. Per aggiungere un nuovo mapping della proprietà, chiamare il metodo <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> sul <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>del controllo <xref:System.Windows.Forms.Integration.ElementHost>.

### <a name="to-define-new-property-mappings"></a>Per definire nuovi mapping di proprietà

1. Copiare il codice seguente nella definizione della classe `Form1`.

     [!code-csharp[PropertyMappingWithElementHost#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]

     Il metodo `AddMarginMapping` aggiunge un nuovo mapping per la proprietà <xref:System.Windows.Forms.Control.Margin%2A>.

     Il metodo `OnMarginChange` converte la proprietà <xref:System.Windows.Forms.Control.Margin%2A> nella proprietà <xref:System.Windows.FrameworkElement.Margin%2A> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

2. Copiare il codice seguente nella definizione della classe `Form1`.

     [!code-csharp[PropertyMappingWithElementHost#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]

     Il metodo `AddRegionMapping` aggiunge un nuovo mapping per la proprietà <xref:System.Windows.Forms.Control.Region%2A>.

     Il metodo `OnRegionChange` converte la proprietà <xref:System.Windows.Forms.Control.Region%2A> nella proprietà <xref:System.Windows.UIElement.Clip%2A> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

     Il metodo `Form1_Resize` gestisce l'evento <xref:System.Windows.Forms.Control.Resize> del form e ridimensiona l'area di ridimensionamento per adattarla all'elemento ospitato.

## <a name="removing-a-default-property-mapping"></a>Rimozione di un mapping delle proprietà predefinito

Rimuovere un mapping di proprietà predefinito chiamando il metodo <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> sul <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>del controllo <xref:System.Windows.Forms.Integration.ElementHost>.

### <a name="to-remove-a-default-property-mapping"></a>Per rimuovere un mapping delle proprietà predefinito

- Copiare il codice seguente nella definizione della classe `Form1`.

     [!code-csharp[PropertyMappingWithElementHost#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]

     Il metodo `RemoveCursorMapping` Elimina il mapping predefinito per la proprietà <xref:System.Windows.Forms.Control.Cursor%2A>.

## <a name="extending-a-default-property-mapping"></a>Estensione di un mapping delle proprietà predefinito

È possibile usare un mapping delle proprietà predefinito ed estenderlo con un mapping personalizzato.

### <a name="to-extend-a-default-property-mapping"></a>Per estendere un mapping delle proprietà predefinito

- Copiare il codice seguente nella definizione della classe `Form1`.

     [!code-csharp[PropertyMappingWithElementHost#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]

     Il metodo `ExtendBackColorMapping` aggiunge un convertitore di proprietà personalizzato al mapping della proprietà <xref:System.Windows.Forms.Control.BackColor%2A> esistente.

     Il metodo `OnBackColorChange` assegna un'immagine specifica alla proprietà <xref:System.Windows.Controls.Control.Background%2A> del controllo ospitato. Il metodo `OnBackColorChange` viene chiamato dopo l'applicazione del mapping di proprietà predefinito.

## <a name="initialize-your-property-mappings"></a>Inizializzare i mapping delle proprietà

1. Copiare il codice seguente nella definizione della classe `Form1`.

     [!code-csharp[PropertyMappingWithElementHost#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]

     Il metodo `Form1_Load` gestisce l'evento <xref:System.Windows.Forms.Form.Load> ed esegue l'inizializzazione seguente.

    - Crea un elemento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button>.

    - Chiama i metodi definiti in precedenza nella procedura dettagliata per impostare i mapping delle proprietà.

    - Assegna i valori iniziali alle proprietà mappate.

2. Premere F5 per compilare ed eseguire l'applicazione.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Mapping di proprietà di Windows Form e WPF](windows-forms-and-wpf-property-mapping.md)
- [Progettare XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Procedura dettaglia: hosting di un controllo WPF composito in Windows Form](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
