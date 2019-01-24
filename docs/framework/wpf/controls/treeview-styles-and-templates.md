---
title: Stili e modelli di TreeView
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TreeView
- templates [WPF], TreeView
- parts [WPF], TreeView
- states [WPF], TreeView
- styles [WPF], TreeView
- TreeView [WPF], styles and templates
ms.assetid: a49adb77-0202-4caa-b94a-8bb110d7fa9a
ms.openlocfilehash: 938adf5b20f289cc219821a549a9dd47df297ae1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624041"
---
# <a name="treeview-styles-and-templates"></a>Stili e modelli di TreeView
In questo argomento descrive gli stili e modelli per la <xref:System.Windows.Controls.TreeView> controllo. È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco. Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="treeview-parts"></a>Parti del controllo TreeView  
 Il <xref:System.Windows.Controls.TreeView> controllo non dispone di parti denominate.  
  
 Quando si crea una <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.TreeView>, il modello potrebbe contenere una <xref:System.Windows.Controls.ItemsPresenter> all'interno di un <xref:System.Windows.Controls.ScrollViewer>. (Il <xref:System.Windows.Controls.ItemsPresenter> Visualizza ogni elemento nel <xref:System.Windows.Controls.TreeView>; i <xref:System.Windows.Controls.ScrollViewer> consente lo scorrimento all'interno del controllo).  Se il <xref:System.Windows.Controls.ItemsPresenter> non è il figlio diretto del <xref:System.Windows.Controls.ScrollViewer>, è necessario dare il <xref:System.Windows.Controls.ItemsPresenter> il nome, `ItemsPresenter`.  
  
## <a name="treeview-states"></a>Stati del controllo TreeView  
 La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.TreeView> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Valido|ValidationStates|Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.|  
  
## <a name="treeviewitem-parts"></a>Parti di TreeViewItem  
 La tabella seguente elenca le parti denominate di <xref:System.Windows.Controls.TreeViewItem> controllo.  
  
|Parte|Tipo|Descrizione|  
|----------|----------|-----------------|  
|PART_Header|<xref:System.Windows.FrameworkElement>|Un elemento visivo che contiene il contenuto dell'intestazione di <xref:System.Windows.Controls.TreeView> controllo.|  
  
## <a name="treeviewitem-states"></a>Stati di TreeViewItem  
 La tabella seguente elenca gli stati visivi <xref:System.Windows.Controls.TreeViewItem> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|----------------------|---------------------------|-----------------|  
|Normale|CommonStates|Lo stato predefinito.|  
|MouseOver|CommonStates|Il puntatore del mouse è posizionato il <xref:System.Windows.Controls.TreeViewItem>.|  
|Disabilitato|CommonStates|Il <xref:System.Windows.Controls.TreeViewItem> è disabilitato.|  
|Con stato attivo|FocusStates|Il <xref:System.Windows.Controls.TreeViewItem> ha lo stato attivo.|  
|Con stato non attivo|FocusStates|Il <xref:System.Windows.Controls.TreeViewItem> non è attivo.|  
|Espanso|ExpansionStates|Il <xref:System.Windows.Controls.TreeViewItem> controllo è espanso.|  
|Collapsed|ExpansionStates|Il <xref:System.Windows.Controls.TreeViewItem> controllo è compresso.|  
|HasItems|HasItemsStates|Il <xref:System.Windows.Controls.TreeViewItem> contiene elementi.|  
|NoItems|HasItemsStates|Il <xref:System.Windows.Controls.TreeViewItem> è privo di elementi.|  
|Selezionato|SelectionStates|Il <xref:System.Windows.Controls.TreeViewItem> sia selezionata.|  
|SelectedInactive|SelectionStates|Il <xref:System.Windows.Controls.TreeViewItem> è selezionato, ma non attiva.|  
|Deselezionato|SelectionStates|Il <xref:System.Windows.Controls.TreeViewItem> non è selezionata.|  
|Valido|ValidationStates|Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.|  
  
## <a name="treeview-controltemplate-example"></a>Esempio di ControlTemplate TreeView  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.TreeView> controllo e i relativi tipi associati.  
  
 [!code-xaml[ControlTemplateExamples#TreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/treeview.xaml#treeview)]  
  
 L'esempio precedente usa una o più delle seguenti risorse.  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Stili e modelli di Control](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)
- [Personalizzazione dei controlli](../../../../docs/framework/wpf/controls/control-customization.md)
- [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
