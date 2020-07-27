---
title: Stili e modelli di Menu
description: Informazioni sugli stili e i modelli per la Windows Presentation Foundation il controllo menu. Modificare il ControlTemplate per dare al controllo un aspetto univoco.
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], Menu
- ControlTemplate [WPF], Menu
- Menu [WPF], styles and templates
- states [WPF], Menu
- templates [WPF], Menu
- parts [WPF], Menu
ms.assetid: b89da183-9b87-42c6-ac53-731a42c7b09e
ms.openlocfilehash: 5187e4a479609686e39e043808931141ca52078c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164552"
---
# <a name="menu-styles-and-templates"></a>Stili e modelli di Menu
In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Controls.Menu> controllo. È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco. Per altre informazioni, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="menu-parts"></a>Parti del menu  
 Il <xref:System.Windows.Controls.Menu> controllo non dispone di parti denominate.  
  
 Quando si crea un oggetto <xref:System.Windows.Controls.ControlTemplate> per un oggetto <xref:System.Windows.Controls.Menu> , il modello potrebbe contenere un oggetto <xref:System.Windows.Controls.ItemsPresenter> all'interno di un oggetto <xref:System.Windows.Controls.ScrollViewer> . ( <xref:System.Windows.Controls.ItemsPresenter> Visualizza ogni elemento in <xref:System.Windows.Controls.Menu> ; <xref:System.Windows.Controls.ScrollViewer> consente lo scorrimento all'interno del controllo).  Se <xref:System.Windows.Controls.ItemsPresenter> non è l'elemento figlio diretto di <xref:System.Windows.Controls.ScrollViewer> , è necessario assegnare al <xref:System.Windows.Controls.ItemsPresenter> nome `ItemsPresenter` .  
  
## <a name="menu-states"></a>Stati dei menu  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.Menu> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Valido|ValidationStates|Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .|  
|InvalidUnfocused|ValidationStates|Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .|  
  
## <a name="menuitem-parts"></a>Parti MenuItem  
 Nella tabella seguente sono elencate le parti denominate per il <xref:System.Windows.Controls.Menu> controllo.  
  
|Parte|Type|Descrizione|  
|-|-|-|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|Area del sottomenu.|  
  
 Quando si crea un oggetto <xref:System.Windows.Controls.ControlTemplate> per un oggetto <xref:System.Windows.Controls.MenuItem> , il modello potrebbe contenere un oggetto <xref:System.Windows.Controls.ItemsPresenter> all'interno di un oggetto <xref:System.Windows.Controls.ScrollViewer> . ( <xref:System.Windows.Controls.ItemsPresenter> Visualizza ogni elemento in <xref:System.Windows.Controls.MenuItem> ; <xref:System.Windows.Controls.ScrollViewer> consente lo scorrimento all'interno del controllo).  Se <xref:System.Windows.Controls.ItemsPresenter> non è l'elemento figlio diretto di <xref:System.Windows.Controls.ScrollViewer> , è necessario assegnare al <xref:System.Windows.Controls.ItemsPresenter> nome `ItemsPresenter` .  
  
## <a name="menuitem-states"></a>Stati MenuItem  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.MenuItem> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Valido|ValidationStates|Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .|  
|InvalidUnfocused|ValidationStates|Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .|  
  
## <a name="menu-and-menuitem-controltemplate-example"></a>Esempio di ControlTemplate di menu e MenuItem  
 Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Menu> controllo.  
  
 [!code-xaml[ControlTemplateExamples#Menu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menu)]  
  
 Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.MenuItem> controllo.  
  
 [!code-xaml[ControlTemplateExamples#MenuItem](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuitem)]  
  
 Nell'esempio seguente viene definito l'oggetto `MenuScrollViewer` , usato nell'esempio precedente.  
  
 [!code-xaml[ControlTemplateExamples#MenuScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuscrollviewer)]  
  
 Negli <xref:System.Windows.Controls.ControlTemplate> esempi vengono utilizzate una o più delle seguenti risorse.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Stili e modelli di Control](control-styles-and-templates.md)
- [Personalizzazione dei controlli](control-customization.md)
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md)
