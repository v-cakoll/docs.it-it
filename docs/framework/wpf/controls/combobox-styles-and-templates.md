---
title: Stili e modelli di ComboBox
description: Informazioni sugli stili e i modelli per il controllo ComboBox Windows Presentation Foundation. Modificare il ControlTemplate per dare al controllo un aspetto univoco.
ms.date: 03/30/2017
helpviewer_keywords:
- ComboBox [WPF], styles and templates
- states [WPF], ComboBox
- ControlTemplate [WPF], ComboBox
- styles [WPF], ComboBox
- templates [WPF], ComboBox
- parts [WPF], ComboBox
ms.assetid: b0662fa1-16d7-4320-b26b-c1804e565a44
ms.openlocfilehash: 5e929bafeaf849b4b5682a17ca51cb0aab963613
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165915"
---
# <a name="combobox-styles-and-templates"></a>Stili e modelli di ComboBox
In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Controls.ComboBox> controllo. È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco. Per altre informazioni, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="combobox-parts"></a>Parti ComboBox  
 Nella tabella seguente sono elencate le parti denominate per il <xref:System.Windows.Controls.ComboBox> controllo.  
  
|Parte|Type|Descrizione|  
|-|-|-|  
|PART_EditableTextBox|<xref:System.Windows.Controls.TextBox>|Contiene il testo di <xref:System.Windows.Controls.ComboBox> .|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|Elenco a discesa che contiene gli elementi nella casella combinata.|  
  
 Quando si crea un oggetto <xref:System.Windows.Controls.ControlTemplate> per un oggetto <xref:System.Windows.Controls.ComboBox> , il modello potrebbe contenere un oggetto <xref:System.Windows.Controls.ItemsPresenter> all'interno di un oggetto <xref:System.Windows.Controls.ScrollViewer> . ( <xref:System.Windows.Controls.ItemsPresenter> Visualizza ogni elemento in <xref:System.Windows.Controls.ComboBox> ; <xref:System.Windows.Controls.ScrollViewer> consente lo scorrimento all'interno del controllo).  Se <xref:System.Windows.Controls.ItemsPresenter> non è l'elemento figlio diretto di <xref:System.Windows.Controls.ScrollViewer> , è necessario assegnare al <xref:System.Windows.Controls.ItemsPresenter> nome `ItemsPresenter` .  
  
## <a name="combobox-states"></a>Stati ComboBox  
 Nella tabella seguente sono elencati gli Stati per il <xref:System.Windows.Controls.ComboBox> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Normale|CommonStates|Lo stato predefinito.|  
|Disabled|CommonStates|Il controllo è disabilitato.|  
|MouseOver|CommonStates|Il puntatore del mouse è posizionato sul <xref:System.Windows.Controls.ComboBox> controllo.|  
|Con stato attivo|FocusStates|Il controllo ha lo stato attivo.|  
|Con stato non attivo|FocusStates|Il controllo non ha lo stato attivo.|  
|FocusedDropDown|FocusStates|L'elenco a discesa per <xref:System.Windows.Controls.ComboBox> ha lo stato attivo.|  
|Valido|ValidationStates|Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .|  
|InvalidFocused|ValidationStates|La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo non ha lo stato attivo.|  
|Editable|EditStates|La proprietà <xref:System.Windows.Controls.ComboBox.IsEditable%2A> è `true`.|  
|Modificabili|EditStates|La proprietà <xref:System.Windows.Controls.ComboBox.IsEditable%2A> è `false`.|  
  
## <a name="comboboxitem-parts"></a>Parti ComboBoxItem  
 Il <xref:System.Windows.Controls.ComboBoxItem> controllo non dispone di parti denominate.  
  
## <a name="comboboxitem-states"></a>Stati ComboBoxItem  
 Nella tabella seguente sono elencati gli Stati per il <xref:System.Windows.Controls.ComboBoxItem> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Normale|CommonStates|Lo stato predefinito.|  
|Disabled|CommonStates|Il controllo è disabilitato.|  
|MouseOver|CommonStates|Il puntatore del mouse è posizionato sul <xref:System.Windows.Controls.ComboBoxItem> controllo.|  
|Con stato attivo|FocusStates|Il controllo ha lo stato attivo.|  
|Con stato non attivo|FocusStates|Il controllo non ha lo stato attivo.|  
|Selezionato|SelectionStates|L'elemento è attualmente selezionato.|  
|Deselezionato|SelectionStates|L'elemento non è selezionato.|  
|SelectedUnfocused|SelectionStates|L'elemento è selezionato, ma non ha uno stato attivo.|  
|Valido|ValidationStates|Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .|  
|InvalidFocused|ValidationStates|La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo non ha lo stato attivo.|  
  
## <a name="combobox-controltemplate-example"></a>Esempio di ControlTemplate ComboBox  
 Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.ComboBox> controllo e i tipi associati.  
  
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
