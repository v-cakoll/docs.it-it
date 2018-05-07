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
ms.openlocfilehash: 3a73127e409a96d5282272bd7a0e55a13a83a849
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="treeview-styles-and-templates"></a>Stili e modelli di TreeView
In questo argomento vengono descritti gli stili e modelli per il <xref:System.Windows.Controls.TreeView> controllo. È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco. Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="treeview-parts"></a>Parti di TreeView  
 Il <xref:System.Windows.Controls.TreeView> controllo non dispone di parti denominate.  
  
 Quando si crea un <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.TreeView>, il modello potrebbe contenere un <xref:System.Windows.Controls.ItemsPresenter> all'interno di un <xref:System.Windows.Controls.ScrollViewer>. (Il <xref:System.Windows.Controls.ItemsPresenter> Visualizza ogni elemento nel <xref:System.Windows.Controls.TreeView>; <xref:System.Windows.Controls.ScrollViewer> Abilita lo scorrimento all'interno del controllo).  Se il <xref:System.Windows.Controls.ItemsPresenter> non è il figlio diretto del <xref:System.Windows.Controls.ScrollViewer>, è necessario assegnare il <xref:System.Windows.Controls.ItemsPresenter> il nome, `ItemsPresenter`.  
  
## <a name="treeview-states"></a>Stati del controllo TreeView  
 Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Controls.TreeView> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Valido|ValidationStates|Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.|  
  
## <a name="treeviewitem-parts"></a>TreeViewItem parti  
 La tabella seguente elenca le parti denominate la <xref:System.Windows.Controls.TreeViewItem> controllo.  
  
|Parte|Tipo|Descrizione|  
|----------|----------|-----------------|  
|PART_Header|<xref:System.Windows.FrameworkElement>|Un elemento visivo che contiene il contenuto dell'intestazione di <xref:System.Windows.Controls.TreeView> controllo.|  
  
## <a name="treeviewitem-states"></a>Stati di TreeViewItem  
 Nella tabella seguente sono elencati gli stati visivi per <xref:System.Windows.Controls.TreeViewItem> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|----------------------|---------------------------|-----------------|  
|Normale|CommonStates|Lo stato predefinito.|  
|MouseOver|CommonStates|Il puntatore del mouse è posizionato il <xref:System.Windows.Controls.TreeViewItem>.|  
|Disabilitato|CommonStates|Il <xref:System.Windows.Controls.TreeViewItem> è disabilitato.|  
|Con stato attivo|FocusStates|Il <xref:System.Windows.Controls.TreeViewItem> ha lo stato attivo.|  
|Con stato non attivo|FocusStates|Il <xref:System.Windows.Controls.TreeViewItem> non è attivo.|  
|Espanso|ExpansionStates|Il <xref:System.Windows.Controls.TreeViewItem> controllo è espanso.|  
|Collapsed|ExpansionStates|Il <xref:System.Windows.Controls.TreeViewItem> controllo viene compresso.|  
|HasItems|HasItemsStates|Il <xref:System.Windows.Controls.TreeViewItem> dispone di elementi.|  
|NoItems|HasItemsStates|Il <xref:System.Windows.Controls.TreeViewItem> non dispone di voci.|  
|Selezionato|SelectionStates|Il <xref:System.Windows.Controls.TreeViewItem> è selezionata.|  
|SelectedInactive|SelectionStates|Il <xref:System.Windows.Controls.TreeViewItem> è selezionata, ma non attiva.|  
|Deselezionato|SelectionStates|Il <xref:System.Windows.Controls.TreeViewItem> non è selezionata.|  
|Valido|ValidationStates|Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.|  
  
## <a name="treeview-controltemplate-example"></a>Esempio di ControlTemplate del controllo TreeView  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.TreeView> controllo e i relativi tipi associati.  
  
 [!code-xaml[ControlTemplateExamples#TreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/treeview.xaml#treeview)]  
  
 L'esempio precedente usa una o più delle seguenti risorse.  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [Stili e modelli di Control](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [Personalizzazione dei controlli](../../../../docs/framework/wpf/controls/control-customization.md)  
 [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
