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
ms.openlocfilehash: b973d47711632f4c0fe56f042545598272c79d2d
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124364"
---
# <a name="contextmenu-overview"></a>Cenni preliminari sull'oggetto ContextMenu
La classe <xref:System.Windows.Controls.ContextMenu> rappresenta l'elemento che espone la funzionalità utilizzando una <xref:System.Windows.Controls.Menu>specifica del contesto. In genere, un utente espone il <xref:System.Windows.Controls.ContextMenu> nel [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] facendo clic con il pulsante destro del mouse sul pulsante del mouse. Questo argomento introduce l'elemento <xref:System.Windows.Controls.ContextMenu> e fornisce esempi su come usarlo in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] e codice.  

<a name="contextmenu_control"></a>   
## <a name="contextmenu-control"></a>Controllo ContextMenu  
 Un <xref:System.Windows.Controls.ContextMenu> è associato a un controllo specifico. L'elemento <xref:System.Windows.Controls.ContextMenu> consente di presentare agli utenti un elenco di elementi che specificano i comandi o le opzioni associate a un particolare controllo, ad esempio una <xref:System.Windows.Controls.Button>. Gli utenti possono fare clic con il pulsante destro del mouse sul controllo per visualizzare il menu. In genere, quando si fa clic su un <xref:System.Windows.Controls.MenuItem> viene aperto un sottomenu o viene eseguita un'applicazione per eseguire un comando.  
  
<a name="creating_contextmenus"></a>   
## <a name="creating-contextmenus"></a>Creazione di elementi ContextMenu  
 Negli esempi seguenti viene illustrato come creare un <xref:System.Windows.Controls.ContextMenu> con sottomenu. I controlli <xref:System.Windows.Controls.ContextMenu> sono collegati ai controlli Button.  
  
 [!code-xaml[ContextMenu#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>   
## <a name="applying-styles-to-a-contextmenu"></a>Applicazione di stili a un elemento ContextMenu  
 Utilizzando un controllo <xref:System.Windows.Style>, è possibile modificare in modo significativo l'aspetto e il comportamento di un <xref:System.Windows.Controls.ContextMenu> senza scrivere un controllo personalizzato. Oltre a impostare proprietà visive, è anche possibile applicare stili alle parti di un controllo. Ad esempio, è possibile modificare il comportamento delle parti del controllo utilizzando le proprietà oppure è possibile aggiungere o modificare il layout di un <xref:System.Windows.Controls.ContextMenu>. Gli esempi seguenti illustrano diversi modi per aggiungere stili ai controlli <xref:System.Windows.Controls.ContextMenu>.  
  
 Nel primo esempio viene definito uno stile denominato `SimpleSysResources`, che illustra come usare le impostazioni di sistema correnti nello stile. Nell'esempio viene assegnata <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> come colore <xref:System.Windows.Controls.Control.Background%2A> e <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> come colore <xref:System.Windows.Controls.Control.Foreground%2A> del <xref:System.Windows.Controls.ContextMenu>.  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=   
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=   
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 Nell'esempio seguente viene usato l'elemento <xref:System.Windows.Trigger> per modificare l'aspetto di un <xref:System.Windows.Controls.Menu> in risposta a eventi generati nel <xref:System.Windows.Controls.ContextMenu>. Quando un utente sposta il puntatore del mouse sul menu, viene modificato l'aspetto degli elementi <xref:System.Windows.Controls.ContextMenu>.  
  
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
