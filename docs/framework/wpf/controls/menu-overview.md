---
title: Cenni preliminari sulla classe Menu
ms.date: 03/30/2017
helpviewer_keywords:
- Menu control [WPF]
- controls [WPF], Menu
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
ms.openlocfilehash: 4c3e8398ad058c50df535fea88dd9f366b7f24ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="menu-overview"></a>Cenni preliminari sulla classe Menu
La <xref:System.Windows.Controls.Menu> classe consente di organizzare gli elementi associati a comandi e gestori eventi in ordine gerarchico. Ogni <xref:System.Windows.Controls.Menu> elemento contiene una raccolta di <xref:System.Windows.Controls.MenuItem> elementi.  
  
  
<a name="menu_control"></a>   
## <a name="menu-control"></a>Controllo Menu  
 Il <xref:System.Windows.Controls.Menu> consente di visualizzare un elenco di elementi che specificano le opzioni per un'applicazione o i comandi. In genere, facendo clic su un <xref:System.Windows.Controls.MenuItem> viene aperto un sottomenu o fa sì che un'applicazione eseguire un comando.  
  
<a name="creating_menus"></a>   
## <a name="creating-menus"></a>Creazione di menu  
 Nell'esempio seguente viene creato un <xref:System.Windows.Controls.Menu> per modificare il testo in un <xref:System.Windows.Controls.TextBox>. Il <xref:System.Windows.Controls.Menu> contiene <xref:System.Windows.Controls.MenuItem> gli oggetti che utilizzano il <xref:System.Windows.Controls.MenuItem.Command%2A>, <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>, e <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> proprietà e <xref:System.Windows.Controls.MenuItem.Checked>, <xref:System.Windows.Controls.MenuItem.Unchecked>, e <xref:System.Windows.Controls.MenuItem.Click> eventi.  
  
 [!code-xaml[MenuItemCommandsAndEvents#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>   
## <a name="menuitems-with-keyboard-shortcuts"></a>MenuItems con abbreviazioni da tastiera  
 Tasti di scelta rapida sono combinazioni di caratteri che possono essere immessi con la tastiera per richiamare <xref:System.Windows.Controls.Menu> comandi. Il collegamento per **Copia** ad esempio è CTRL+C. Sono disponibili due proprietà da utilizzare con voci di menu e tasti di scelta rapida:<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> o <xref:System.Windows.Controls.MenuItem.Command%2A>.  
  
<a name="menus_inputgesturetext"></a>   
### <a name="inputgesturetext"></a>InputGestureText  
 Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> proprietà a cui assegnare il testo di scelta rapida da tastiera per <xref:System.Windows.Controls.MenuItem> controlli. In questo modo nella voce di menu vengono inserite solo le abbreviazioni da tastiera.  Non associare il comando con il <xref:System.Windows.Controls.MenuItem>. L'applicazione deve gestire l'input dell'utente per eseguire l'azione.  
  
 [!code-xaml[MenuEvent#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>   
### <a name="command"></a>Comando  
 Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Controls.MenuItem.Command%2A> proprietà per associare il **aprire** e **salvare** comandi con <xref:System.Windows.Controls.MenuItem> controlli. La proprietà command non associa solo un comando con un <xref:System.Windows.Controls.MenuItem>, ma fornisce anche il testo di input da utilizzare come un collegamento.  
  
 [!code-xaml[MenuEvent#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 Il <xref:System.Windows.Controls.MenuItem> classe include inoltre un <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> proprietà che specifica l'elemento in cui si verifica il comando. Se <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> non è impostata, l'elemento con stato attivo della tastiera riceve il comando. Per altre informazioni sui comandi vedere [Cenni preliminari sull'esecuzione di comandi](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
<a name="menu_styling"></a>   
## <a name="menu-styling"></a>Applicazione di stili al testo  
 Con lo stile di controllo, è possibile modificare drasticamente l'aspetto e il comportamento di <xref:System.Windows.Controls.Menu> controlli senza dover scrivere un controllo personalizzato. Oltre a impostare la proprietà visive, è inoltre possibile applicare un <xref:System.Windows.Style> a singole parti di un controllo, il comportamento di parti del controllo tramite le proprietà, modificare o aggiungere parti aggiuntive o modificare il layout di un controllo. Gli esempi seguenti illustrano diversi modi per aggiungere un <xref:System.Windows.Style> per un <xref:System.Windows.Controls.Menu> controllo.  
  
 Nel primo esempio di codice definisce un <xref:System.Windows.Style> chiamato `Simple` che viene illustrato come utilizzare le impostazioni di sistema correnti nello stile. Il codice assegna il colore di `MenuHighlightBrush` come colore di sfondo del menu e `MenuTextBrush` come colore di primo piano del menu. Si noti l'uso delle chiavi di risorsa per assegnare i pennelli.  
  
 [!code-xaml[MenuStylesSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 L'esempio seguente usa <xref:System.Windows.Trigger> gli elementi che consentono di modificare l'aspetto di un <xref:System.Windows.Controls.MenuItem> in risposta a eventi che si verificano nel <xref:System.Windows.Controls.Menu>. Quando si sposta il puntatore del mouse su di <xref:System.Windows.Controls.Menu>, il colore primo piano e le caratteristiche del carattere delle voci di menu Modifica.  
  
 [!code-xaml[MenuStylesSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a>Vedere anche  
 [Esempio di raccolta di controlli WPF](http://go.microsoft.com/fwlink/?LinkID=160053)
