---
title: 'Procedura: Utilizzare un menu di scelta rapida personalizzato con un oggetto TextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [WPF], custom
- menus [WPF], custom
- custom context menus [WPF]
- TextBox control [WPF], custom content menus
ms.assetid: 842d3cd5-6fa0-4be4-8d90-6c7466213b1c
ms.openlocfilehash: 5b1b0ea569831361c4680102e8229fe3755bffda
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54742341"
---
# <a name="how-to-use-a-custom-context-menu-with-a-textbox"></a>Procedura: Utilizzare un menu di scelta rapida personalizzato con un oggetto TextBox
Questo esempio illustra come definire e implementare un menu di scelta rapida personalizzato semplice un <xref:System.Windows.Controls.TextBox>.  
  
## <a name="example"></a>Esempio  
 Quanto segue [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] esempio definisce un <xref:System.Windows.Controls.TextBox> controllo che include un menu contestuale personalizzato.  
  
 Menu di scelta rapida viene definito mediante un <xref:System.Windows.Controls.ContextMenu> elemento.  Menu di scelta rapida se stessa è costituito da una serie di <xref:System.Windows.Controls.MenuItem> elementi e <xref:System.Windows.Controls.Separator> elementi.  Ciascuna <xref:System.Windows.Controls.MenuItem> elemento definisce un comando nel menu di scelta rapida; il <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> attributo definisce il testo visualizzato per il comando di menu e <xref:System.Windows.Controls.MenuItem.Click> attributo specifica un metodo del gestore per ogni voce di menu.  Il <xref:System.Windows.Controls.Separator> elemento consente semplicemente di una linea di separazione da sottoporre a rendering tra le voci di menu precedenti e successivi.  
  
 [!code-xaml[TextBox_ContextMenu#_TextBox_ContextMenuXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml#_textbox_contextmenuxaml)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato il codice di implementazione per la definizione del menu contesto precedente, nonché il codice che abilita e disabilita il menu di scelta rapida.  Il <xref:System.Windows.Controls.ContextMenu.Opened> evento viene utilizzato per abilitare o disabilitare alcuni comandi a seconda dello stato corrente di dinamicamente il <xref:System.Windows.Controls.TextBox>.  
  
 Per ripristinare il menu di scelta rapida predefiniti, usare il <xref:System.Windows.DependencyObject.ClearValue%2A> metodo per cancellare il valore della <xref:System.Windows.FrameworkElement.ContextMenu%2A> proprietà.  Per disabilitare completamente il menu di scelta rapida, impostare il <xref:System.Windows.FrameworkElement.ContextMenu%2A> proprietà su un riferimento null (`Nothing` in Visual Basic).  
  
 [!code-csharp[TextBox_ContextMenu#_TextBox_ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml.cs#_textbox_contextmenu)]
 [!code-vb[TextBox_ContextMenu#_TextBox_ContextMenu](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_ContextMenu/VisualBasic/Window1.xaml.vb#_textbox_contextmenu)]  
  
## <a name="see-also"></a>Vedere anche
- [Usare il controllo ortografico con un menu di scelta rapida](../../../../docs/framework/wpf/controls/how-to-use-spell-checking-with-a-context-menu.md)
- [Cenni preliminari sulla classe TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [Cenni preliminari sul controllo RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
