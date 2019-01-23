---
title: 'Procedura: Applicare uno stile ai controlli di un oggetto ToolBar'
ms.date: 03/30/2017
helpviewer_keywords:
- styling controls on toolbar [WPF]
- toolbars [WPF]
- customizing controls on toolbar [WPF]
ms.assetid: ba6ae056-d6a9-4c24-90f8-467ab0bc0b1a
ms.openlocfilehash: 097bb23a41ba68bf9c121a53920f19694508348b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544861"
---
# <a name="how-to-style-controls-on-a-toolbar"></a>Procedura: Applicare uno stile ai controlli di un oggetto ToolBar
Il <xref:System.Windows.Controls.ToolBar> definisce <xref:System.Windows.ResourceKey> gli oggetti per specificare lo stile di controlli all'interno di <xref:System.Windows.Controls.ToolBar>.  Per definire lo stile di un controllo in una <xref:System.Windows.Controls.ToolBar>, impostare il `x:key` attributo di stile da un <xref:System.Windows.ResourceKey> definito in <xref:System.Windows.Controls.ToolBar>.  
  
 Il <xref:System.Windows.Controls.ToolBar> definisce i seguenti <xref:System.Windows.ResourceKey> oggetti:  
  
-   <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.CheckBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.MenuStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.RadioButtonStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.SeparatorStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.TextBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.ToggleButtonStyleKey%2A>  
  
## <a name="example"></a>Esempio  
 L'esempio seguente definisce gli stili per i controlli all'interno di un <xref:System.Windows.Controls.ToolBar>.  
  
 [!code-xaml[ToolBar_snip#ToolBarAllStyles](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbarallstyles)]  
[!code-xaml[ToolBar_snip#ToolBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbar)]  
  
## <a name="see-also"></a>Vedere anche
- [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md)
