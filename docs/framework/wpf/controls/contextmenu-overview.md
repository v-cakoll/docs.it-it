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
ms.openlocfilehash: 54fd823594fba4500f35ed1d69720a3309e54a36
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43787038"
---
# <a name="contextmenu-overview"></a>Cenni preliminari sull'oggetto ContextMenu
Il <xref:System.Windows.Controls.ContextMenu> classe rappresenta l'elemento che espone la funzionalità utilizzando un contesto specifico <xref:System.Windows.Controls.Menu>. In genere, un utente espone il <xref:System.Windows.Controls.ContextMenu> nella [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] facendo clic con il pulsante del mouse. Questo argomento vengono presentate le <xref:System.Windows.Controls.ContextMenu> elemento e vengono forniti esempi su come usarlo in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] e codice.  
  
  
  
<a name="contextmenu_control"></a>   
## <a name="contextmenu-control"></a>Controllo ContextMenu  
 Oggetto <xref:System.Windows.Controls.ContextMenu> è collegato a un controllo specifico. Il <xref:System.Windows.Controls.ContextMenu> elemento consente di presentare agli utenti un elenco di elementi che specificano i comandi o le opzioni che sono associate a un particolare controllo, ad esempio, un <xref:System.Windows.Controls.Button>. Gli utenti possono fare clic con il pulsante destro del mouse sul controllo per visualizzare il menu. In genere, facendo clic su un <xref:System.Windows.Controls.MenuItem> apre un sottomenu o parte di un'applicazione eseguire un comando.  
  
<a name="creating_contextmenus"></a>   
## <a name="creating-contextmenus"></a>Creazione di elementi ContextMenu  
 Gli esempi seguenti illustrano come creare un <xref:System.Windows.Controls.ContextMenu> con sottomenu. Il <xref:System.Windows.Controls.ContextMenu> controlli vengono associati ai controlli pulsante.  
  
 [!code-xaml[ContextMenu#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>   
## <a name="applying-styles-to-a-contextmenu"></a>Applicazione di stili a un elemento ContextMenu  
 Usando un controllo <xref:System.Windows.Style>, è possibile modificare in modo significativo l'aspetto e il comportamento di un <xref:System.Windows.Controls.ContextMenu> senza dover scrivere un controllo personalizzato. Oltre a impostare proprietà visive, è anche possibile applicare stili alle parti di un controllo. Ad esempio, è possibile modificare il comportamento delle parti del controllo utilizzando le proprietà, oppure è possibile aggiungere parti o modificare il layout di un <xref:System.Windows.Controls.ContextMenu>. Gli esempi seguenti illustrano diversi modi per aggiungere gli stili per <xref:System.Windows.Controls.ContextMenu> controlli.  
  
 Nel primo esempio viene definito uno stile denominato `SimpleSysResources`, che illustra come usare le impostazioni di sistema correnti nello stile. Nell'esempio viene assegnato <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> come il <xref:System.Windows.Controls.Control.Background%2A> colore e <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> come il <xref:System.Windows.Controls.Control.Foreground%2A> colore del <xref:System.Windows.Controls.ContextMenu>.  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=   
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=   
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 L'esempio seguente usa il <xref:System.Windows.Trigger> elemento per modificare l'aspetto di un <xref:System.Windows.Controls.Menu> in risposta agli eventi generati per il <xref:System.Windows.Controls.ContextMenu>. Quando un utente si sposta il puntatore del mouse sul menu, l'aspetto del <xref:System.Windows.Controls.ContextMenu> gli elementi delle modifiche.  
  
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
 <xref:System.Windows.Controls.ContextMenu>  
 <xref:System.Windows.Style>  
 <xref:System.Windows.Controls.Menu>  
 <xref:System.Windows.Controls.MenuItem>  
 [ContextMenu](../../../../docs/framework/wpf/controls/contextmenu.md)  
 [Stili e modelli di ContextMenu](../../../../docs/framework/wpf/controls/contextmenu-styles-and-templates.md)  
 [Esempio di raccolta di controlli WPF](https://go.microsoft.com/fwlink/?LinkID=160053)
