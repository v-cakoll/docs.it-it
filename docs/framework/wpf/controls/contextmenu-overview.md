---
title: Cenni preliminari sull'oggetto ContextMenu
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ContextMenu
- ContextMenu controls [WPF], about ContextMenu controls
ms.assetid: 16909c42-799a-4561-91e0-7d69dcfeea91
ms.openlocfilehash: 4d2d8db0f614b5240705146dbe91432b96b46dd6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185907"
---
# <a name="contextmenu-overview"></a>Cenni preliminari sull'oggetto ContextMenu
La <xref:System.Windows.Controls.ContextMenu> classe rappresenta l'elemento che espone funzionalità <xref:System.Windows.Controls.Menu>utilizzando un oggetto specifico del contesto. In genere, un <xref:System.Windows.Controls.ContextMenu> utente [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] espone l'oggetto in facendo clic con il pulsante destro del mouse sul pulsante del mouse. In questo argomento <xref:System.Windows.Controls.ContextMenu> viene presentato l'elemento e [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] vengono forniti esempi di come utilizzarlo in e nel codice.  

<a name="contextmenu_control"></a>
## <a name="contextmenu-control"></a>Controllo ContextMenu  
 A <xref:System.Windows.Controls.ContextMenu> è collegato a un controllo specifico. L'elemento <xref:System.Windows.Controls.ContextMenu> consente di presentare agli utenti un elenco di elementi che specificano comandi <xref:System.Windows.Controls.Button>o opzioni associati a un determinato controllo, ad esempio un oggetto . Gli utenti possono fare clic con il pulsante destro del mouse sul controllo per visualizzare il menu. In genere, <xref:System.Windows.Controls.MenuItem> facendo clic su un apre un sottomenu o viene emesso un comando da parte di un'applicazione.  
  
<a name="creating_contextmenus"></a>
## <a name="creating-contextmenus"></a>Creazione di elementi ContextMenu  
 Negli esempi seguenti viene <xref:System.Windows.Controls.ContextMenu> illustrato come creare un con sottomenu. I <xref:System.Windows.Controls.ContextMenu> controlli sono associati ai controlli pulsante.  
  
 [!code-xaml[ContextMenu#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>
## <a name="applying-styles-to-a-contextmenu"></a>Applicazione di stili a un elemento ContextMenu  
 Utilizzando un <xref:System.Windows.Style>controllo , è possibile modificare notevolmente l'aspetto e il comportamento di un <xref:System.Windows.Controls.ContextMenu> senza scrivere un controllo personalizzato. Oltre a impostare proprietà visive, è anche possibile applicare stili alle parti di un controllo. Ad esempio, è possibile modificare il comportamento di parti del controllo utilizzando le proprietà oppure <xref:System.Windows.Controls.ContextMenu>aggiungere parti o modificare il layout di un oggetto . Negli esempi seguenti vengono illustrati <xref:System.Windows.Controls.ContextMenu> diversi modi per aggiungere stili ai controlli.  
  
 Nel primo esempio viene definito uno stile denominato `SimpleSysResources`, che illustra come usare le impostazioni di sistema correnti nello stile. L'esempio <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> viene <xref:System.Windows.Controls.Control.Background%2A> assegnato <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> come <xref:System.Windows.Controls.Control.Foreground%2A> colore e <xref:System.Windows.Controls.ContextMenu>come colore dell'oggetto .  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 Nell'esempio riportato di seguito viene utilizzato l'elemento <xref:System.Windows.Trigger> per modificare l'aspetto di un <xref:System.Windows.Controls.Menu> oggetto in risposta agli eventi generati nell'oggetto <xref:System.Windows.Controls.ContextMenu>. Quando un utente sposta il mouse sul <xref:System.Windows.Controls.ContextMenu> menu, l'aspetto degli elementi cambia.  
  
```xaml  
<Style x:Key="Triggers" TargetType="{x:Type MenuItem}">  
  <Style.Triggers>  
    <Trigger Property="MenuItem.IsMouseOver" Value="true">  
      <Setter Property = "FontSize" Value="16"/>  
      <Setter Property = "FontStyle" Value="Italic"/>  
      <Setter Property = "Foreground" Value="Red"/>  
    </Trigger>  
  </Style.Triggers>  
</Style>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.ContextMenu>
- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.Menu>
- <xref:System.Windows.Controls.MenuItem>
- [ContextMenu](contextmenu.md)
- [Stili e modelli di ContextMenu](contextmenu-styles-and-templates.md)
- [Esempio di raccolta di controlli WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
