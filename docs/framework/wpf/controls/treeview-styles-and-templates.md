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
ms.openlocfilehash: 45276d23380fe956fc3d59b90d5baae23ee8a7e2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283627"
---
# <a name="treeview-styles-and-templates"></a>Stili e modelli di TreeView
In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.TreeView>. È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco. Per altre informazioni, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="treeview-parts"></a>Parti TreeView  
 Il controllo <xref:System.Windows.Controls.TreeView> non dispone di parti denominate.  
  
 Quando si crea un <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.TreeView>, il modello potrebbe contenere un <xref:System.Windows.Controls.ItemsPresenter> all'interno di una <xref:System.Windows.Controls.ScrollViewer>. Il <xref:System.Windows.Controls.ItemsPresenter> Visualizza ogni elemento del <xref:System.Windows.Controls.TreeView>. il <xref:System.Windows.Controls.ScrollViewer> consente lo scorrimento all'interno del controllo.  Se il <xref:System.Windows.Controls.ItemsPresenter> non è il figlio diretto del <xref:System.Windows.Controls.ScrollViewer>, è necessario assegnare al <xref:System.Windows.Controls.ItemsPresenter> il nome `ItemsPresenter`.  
  
## <a name="treeview-states"></a>Stati di TreeView  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.TreeView>.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Valido|ValidationStates|Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.|  
  
## <a name="treeviewitem-parts"></a>Parti TreeViewItem  
 Nella tabella seguente sono elencate le parti denominate per il controllo <xref:System.Windows.Controls.TreeViewItem>.  
  
|Parte|Type|Descrizione|  
|----------|----------|-----------------|  
|PART_Header|<xref:System.Windows.FrameworkElement>|Elemento visivo che contiene il contenuto dell'intestazione del controllo <xref:System.Windows.Controls.TreeView>.|  
  
## <a name="treeviewitem-states"></a>Stati di TreeViewItem  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.TreeViewItem>.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|----------------------|---------------------------|-----------------|  
|Normale|CommonStates|Stato predefinito.|  
|MouseOver|CommonStates|Il puntatore del mouse viene posizionato sul <xref:System.Windows.Controls.TreeViewItem>.|  
|Disabilitato|CommonStates|Il <xref:System.Windows.Controls.TreeViewItem> è disabilitato.|  
|Con stato attivo|FocusStates|Il <xref:System.Windows.Controls.TreeViewItem> ha lo stato attivo.|  
|Con stato non attivo|FocusStates|Il <xref:System.Windows.Controls.TreeViewItem> non ha lo stato attivo.|  
|Espanso|ExpansionStates|Il controllo <xref:System.Windows.Controls.TreeViewItem> è espanso.|  
|Collapsed|ExpansionStates|Il controllo <xref:System.Windows.Controls.TreeViewItem> è compresso.|  
|HasItems|HasItemsStates|Il <xref:System.Windows.Controls.TreeViewItem> contiene elementi.|  
|Noitems|HasItemsStates|Il <xref:System.Windows.Controls.TreeViewItem> non contiene elementi.|  
|Selected|SelectionStates|Il <xref:System.Windows.Controls.TreeViewItem> è selezionato.|  
|SelectedInactive|SelectionStates|Il <xref:System.Windows.Controls.TreeViewItem> è selezionato ma non attivo.|  
|Deselezionato|SelectionStates|Il <xref:System.Windows.Controls.TreeViewItem> non è selezionato.|  
|Valido|ValidationStates|Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.|  
  
## <a name="treeview-controltemplate-example"></a>Esempio di ControlTemplate TreeView  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.TreeView> e i relativi tipi associati.  
  
 [!code-xaml[ControlTemplateExamples#TreeView](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/treeview.xaml#treeview)]  
  
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
