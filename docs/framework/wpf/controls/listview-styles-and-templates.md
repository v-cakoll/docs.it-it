---
title: Stili e modelli di ListView
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parts [WPF], ListView
- states [WPF], ListView
- ControlTemplate [WPF], ListView
- styles [WPF], ListView
- ListView [WPF], styles and templates
- templates [WPF], ListView
ms.assetid: d2387356-2171-4785-822a-7247e024b4ee
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ccd597aa6d517bb3a7dda347c26c0eaf731a278f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="listview-styles-and-templates"></a>Stili e modelli di ListView
In questo argomento vengono descritti gli stili e modelli per il <xref:System.Windows.Controls.ListView> controllo. È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco. Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="listview-parts"></a>Parti del controllo ListView  
 Il <xref:System.Windows.Controls.ListView> controllo non dispone di parti denominate.  
  
 Quando si crea un <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.ListView>, il modello potrebbe contenere un <xref:System.Windows.Controls.ItemsPresenter> all'interno di un <xref:System.Windows.Controls.ScrollViewer>. (Il <xref:System.Windows.Controls.ItemsPresenter> Visualizza ogni elemento nel <xref:System.Windows.Controls.ListView>; <xref:System.Windows.Controls.ScrollViewer> Abilita lo scorrimento all'interno del controllo).  Se il <xref:System.Windows.Controls.ItemsPresenter> non è il figlio diretto del <xref:System.Windows.Controls.ScrollViewer>, è necessario assegnare il <xref:System.Windows.Controls.ItemsPresenter> il nome, `ItemsPresenter`.  
  
## <a name="listview-states"></a>Stati di ListView  
 Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Controls.ListView> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Valido|ValidationStates|Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.|  
  
## <a name="listviewitem-parts"></a>ListViewItem parti  
 Il <xref:System.Windows.Controls.ListViewItem> controllo non dispone di parti denominate.  
  
## <a name="listviewitem-states"></a>Stati ListViewItem  
 Nella tabella seguente sono elencati gli stati per il <xref:System.Windows.Controls.ListViewItem> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Normale|CommonStates|Lo stato predefinito.|  
|Disabilitato|CommonStates|Il controllo è disabilitato.|  
|MouseOver|CommonStates|Il puntatore del mouse è posizionato il <xref:System.Windows.Controls.ComboBox> controllo.|  
|Con stato attivo|FocusStates|Il controllo ha lo stato attivo.|  
|Con stato non attivo|FocusStates|Il controllo non ha lo stato attivo.|  
|Selezionato|SelectionStates|L'elemento selezionato.|  
|Deselezionato|SelectionStates|L'elemento non è selezionato.|  
|SelectedUnfocused|SelectionStates|L'elemento è selezionato, ma non ha uno stato attivo.|  
|Valido|ValidationStates|Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.|  
  
## <a name="listview-controltemplate-examples"></a>Esempi di ControlTemplate del controllo ListView  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.ListView> controllo e i relativi tipi associati.  
  
 [!code-xaml[ControlTemplateExamples#ListView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/listview.xaml#listview)]  
  
 Il <xref:System.Windows.Controls.ControlTemplate> negli esempi viene utilizzato uno o più delle seguenti risorse.  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [Stili e modelli di Control](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [Personalizzazione dei controlli](../../../../docs/framework/wpf/controls/control-customization.md)  
 [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
