---
title: Stili e modelli di ComboBox
ms.date: 03/30/2017
helpviewer_keywords:
- ComboBox [WPF], styles and templates
- states [WPF], ComboBox
- ControlTemplate [WPF], ComboBox
- styles [WPF], ComboBox
- templates [WPF], ComboBox
- parts [WPF], ComboBox
ms.assetid: b0662fa1-16d7-4320-b26b-c1804e565a44
ms.openlocfilehash: 887698bdaebf7bc5ddac8997167589d9fbd3dd4d
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960371"
---
# <a name="combobox-styles-and-templates"></a>Stili e modelli di ComboBox
In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.ComboBox>. È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco. Per altre informazioni, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="combobox-parts"></a>Parti ComboBox  
 Nella tabella seguente sono elencate le parti denominate per il controllo <xref:System.Windows.Controls.ComboBox>.  
  
|Componente|Tipo di|Descrizione|  
|-|-|-|  
|PART_EditableTextBox|<xref:System.Windows.Controls.TextBox>|Contiene il testo della <xref:System.Windows.Controls.ComboBox>.|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|Elenco a discesa che contiene gli elementi nella casella combinata.|  
  
 Quando si crea un <xref:System.Windows.Controls.ControlTemplate> per una <xref:System.Windows.Controls.ComboBox>, il modello potrebbe contenere un <xref:System.Windows.Controls.ItemsPresenter> all'interno di una <xref:System.Windows.Controls.ScrollViewer>. Il <xref:System.Windows.Controls.ItemsPresenter> Visualizza ogni elemento del <xref:System.Windows.Controls.ComboBox>. il <xref:System.Windows.Controls.ScrollViewer> consente lo scorrimento all'interno del controllo.  Se il <xref:System.Windows.Controls.ItemsPresenter> non è il figlio diretto del <xref:System.Windows.Controls.ScrollViewer>, è necessario assegnare al <xref:System.Windows.Controls.ItemsPresenter> il nome `ItemsPresenter`.  
  
## <a name="combobox-states"></a>Stati ComboBox  
 Nella tabella seguente sono elencati gli Stati per il controllo <xref:System.Windows.Controls.ComboBox>.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Normale|CommonStates|Stato predefinito.|  
|Disabilitato|CommonStates|Il controllo è disabilitato.|  
|MouseOver|CommonStates|Il puntatore del mouse si trova sul controllo <xref:System.Windows.Controls.ComboBox>.|  
|Con stato attivo|FocusStates|Il controllo ha lo stato attivo.|  
|Con stato non attivo|FocusStates|Il controllo non ha lo stato attivo.|  
|FocusedDropDown|FocusStates|L'elenco a discesa per il <xref:System.Windows.Controls.ComboBox> ha lo stato attivo.|  
|Valido|ValidationStates|Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.|  
|Editable|EditStates|La proprietà <xref:System.Windows.Controls.ComboBox.IsEditable%2A> è `true`.|  
|Modificabili|EditStates|La proprietà <xref:System.Windows.Controls.ComboBox.IsEditable%2A> è `false`.|  
  
## <a name="comboboxitem-parts"></a>Parti ComboBoxItem  
 Il controllo <xref:System.Windows.Controls.ComboBoxItem> non dispone di parti denominate.  
  
## <a name="comboboxitem-states"></a>Stati ComboBoxItem  
 Nella tabella seguente sono elencati gli Stati per il controllo <xref:System.Windows.Controls.ComboBoxItem>.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Normale|CommonStates|Stato predefinito.|  
|Disabilitato|CommonStates|Il controllo è disabilitato.|  
|MouseOver|CommonStates|Il puntatore del mouse si trova sul controllo <xref:System.Windows.Controls.ComboBoxItem>.|  
|Con stato attivo|FocusStates|Il controllo ha lo stato attivo.|  
|Con stato non attivo|FocusStates|Il controllo non ha lo stato attivo.|  
|Selected|SelectionStates|L'elemento è attualmente selezionato.|  
|Deselezionato|SelectionStates|L'elemento non è selezionato.|  
|SelectedUnfocused|SelectionStates|L'elemento è selezionato, ma non ha uno stato attivo.|  
|Valido|ValidationStates|Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.|  
  
## <a name="combobox-controltemplate-example"></a>Esempio di ControlTemplate ComboBox  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.ComboBox> e i tipi associati.  
  
 [!code-xaml[ControlTemplateExamples#ComboBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#combobox)]  
  
 L'esempio precedente usa una o più delle seguenti risorse.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Stili e modelli di Control](control-styles-and-templates.md)
- [Personalizzazione dei controlli](control-customization.md)
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md)
