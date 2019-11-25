---
title: Stili e modelli di Menu
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], Menu
- ControlTemplate [WPF], Menu
- Menu [WPF], styles and templates
- states [WPF], Menu
- templates [WPF], Menu
- parts [WPF], Menu
ms.assetid: b89da183-9b87-42c6-ac53-731a42c7b09e
ms.openlocfilehash: 3ce0be1fdeeee1465c2facb414cc7a081b268eb5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283482"
---
# <a name="menu-styles-and-templates"></a>Stili e modelli di Menu
In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.Menu>. È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco. Per altre informazioni, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="menu-parts"></a>Parti del menu  
 Il controllo <xref:System.Windows.Controls.Menu> non dispone di parti denominate.  
  
 Quando si crea un <xref:System.Windows.Controls.ControlTemplate> per una <xref:System.Windows.Controls.Menu>, il modello potrebbe contenere un <xref:System.Windows.Controls.ItemsPresenter> all'interno di una <xref:System.Windows.Controls.ScrollViewer>. Il <xref:System.Windows.Controls.ItemsPresenter> Visualizza ogni elemento del <xref:System.Windows.Controls.Menu>. il <xref:System.Windows.Controls.ScrollViewer> consente lo scorrimento all'interno del controllo.  Se il <xref:System.Windows.Controls.ItemsPresenter> non è il figlio diretto del <xref:System.Windows.Controls.ScrollViewer>, è necessario assegnare al <xref:System.Windows.Controls.ItemsPresenter> il nome `ItemsPresenter`.  
  
## <a name="menu-states"></a>Stati dei menu  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.Menu>.  
  
|Nome VisualState|Nome VisualStateGroup|description|  
|-|-|-|  
|Valido|ValidationStates|Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.|  
  
## <a name="menuitem-parts"></a>Parti MenuItem  
 Nella tabella seguente sono elencate le parti denominate per il controllo <xref:System.Windows.Controls.Menu>.  
  
|Parte|Digitare|description|  
|-|-|-|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|Area del sottomenu.|  
  
 Quando si crea un <xref:System.Windows.Controls.ControlTemplate> per una <xref:System.Windows.Controls.MenuItem>, il modello potrebbe contenere un <xref:System.Windows.Controls.ItemsPresenter> all'interno di una <xref:System.Windows.Controls.ScrollViewer>. Il <xref:System.Windows.Controls.ItemsPresenter> Visualizza ogni elemento del <xref:System.Windows.Controls.MenuItem>. il <xref:System.Windows.Controls.ScrollViewer> consente lo scorrimento all'interno del controllo.  Se il <xref:System.Windows.Controls.ItemsPresenter> non è il figlio diretto del <xref:System.Windows.Controls.ScrollViewer>, è necessario assegnare al <xref:System.Windows.Controls.ItemsPresenter> il nome `ItemsPresenter`.  
  
## <a name="menuitem-states"></a>Stati MenuItem  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.MenuItem>.  
  
|Nome VisualState|Nome VisualStateGroup|description|  
|-|-|-|  
|Valido|ValidationStates|Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.|  
  
## <a name="menu-and-menuitem-controltemplate-example"></a>Esempio di ControlTemplate di menu e MenuItem  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.Menu>.  
  
 [!code-xaml[ControlTemplateExamples#Menu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menu)]  
  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.MenuItem>.  
  
 [!code-xaml[ControlTemplateExamples#MenuItem](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuitem)]  
  
 Nell'esempio seguente viene definito il `MenuScrollViewer`, che viene usato nell'esempio precedente.  
  
 [!code-xaml[ControlTemplateExamples#MenuScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuscrollviewer)]  
  
 Gli esempi di <xref:System.Windows.Controls.ControlTemplate> usano una o più delle risorse seguenti.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Stili e modelli di Control](control-styles-and-templates.md)
- [Personalizzazione dei controlli](control-customization.md)
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md)
