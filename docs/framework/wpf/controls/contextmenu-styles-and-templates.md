---
title: Stili e modelli di ContextMenu
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], ContextMenu
- parts [WPF], ContextMenu
- ContextMenu [WPF], styles and templates
- styles [WPF], ContextMenu
- ControlTemplate [WPF], ContextMenu
- states [WPF], ContextMenu
ms.assetid: 342d1f17-c406-4f94-8f55-867c5f3ea511
ms.openlocfilehash: fa192e20ea84e96c9f85ff84e16c63b7f56c8a98
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283548"
---
# <a name="contextmenu-styles-and-templates"></a>Stili e modelli di ContextMenu
In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.ContextMenu>. È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco. Per altre informazioni, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="contextmenu-parts"></a>Parti ContextMenu  
 Il controllo <xref:System.Windows.Controls.ContextMenu> non dispone di parti denominate.  
  
 Quando si crea un <xref:System.Windows.Controls.ControlTemplate> per una <xref:System.Windows.Controls.ContextMenu>, il modello potrebbe contenere un <xref:System.Windows.Controls.ItemsPresenter> all'interno di una <xref:System.Windows.Controls.ScrollViewer>. Il <xref:System.Windows.Controls.ItemsPresenter> Visualizza ogni elemento del <xref:System.Windows.Controls.ContextMenu>. il <xref:System.Windows.Controls.ScrollViewer> consente lo scorrimento all'interno del controllo.  Se il <xref:System.Windows.Controls.ItemsPresenter> non è il figlio diretto del <xref:System.Windows.Controls.ScrollViewer>, è necessario assegnare al <xref:System.Windows.Controls.ItemsPresenter> il nome `ItemsPresenter`.  
  
## <a name="contextmenu-states"></a>Stati ContextMenu  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.ContextMenu>.  
  
|Nome VisualState|Nome VisualStateGroup|description|  
|-|-|-|  
|Valido|ValidationStates|Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.|  
  
## <a name="contextmenu-controltemplate-example"></a>Esempio di ControlTemplate ContextMenu  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.ContextMenu>.  
  
 [!code-xaml[ControlTemplateExamples#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#contextmenu)]  
  
 Il <xref:System.Windows.Controls.ControlTemplate> utilizza le risorse seguenti.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Stili e modelli di Control](control-styles-and-templates.md)
- [Personalizzazione dei controlli](control-customization.md)
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md)
