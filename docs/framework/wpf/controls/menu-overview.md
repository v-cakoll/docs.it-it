---
title: Cenni preliminari sulla classe Menu
ms.date: 03/30/2017
helpviewer_keywords:
- Menu control [WPF]
- controls [WPF], Menu
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
ms.openlocfilehash: d5f53603ea22b2ae12a9846ba6bdce525790ce15
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360944"
---
# <a name="menu-overview"></a>Cenni preliminari sulla classe Menu
Il <xref:System.Windows.Controls.Menu> classe consente di organizzare gli elementi associati a comandi e gestori di eventi in ordine gerarchico. Ciascuna <xref:System.Windows.Controls.Menu> elemento contiene una raccolta di <xref:System.Windows.Controls.MenuItem> elementi.  
  
  
<a name="menu_control"></a>   
## <a name="menu-control"></a>Controllo Menu  
 Il <xref:System.Windows.Controls.Menu> controllo presenta un elenco di elementi che specificano i comandi o le opzioni per un'applicazione. In genere, facendo clic su un <xref:System.Windows.Controls.MenuItem> apre un sottomenu o parte di un'applicazione eseguire un comando.  
  
<a name="creating_menus"></a>   
## <a name="creating-menus"></a>Creazione di menu  
 L'esempio seguente crea una <xref:System.Windows.Controls.Menu> modificare il testo in un <xref:System.Windows.Controls.TextBox>. Il <xref:System.Windows.Controls.Menu> contiene <xref:System.Windows.Controls.MenuItem> agli oggetti che usano il <xref:System.Windows.Controls.MenuItem.Command%2A>, <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>, e <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> le proprietà e la <xref:System.Windows.Controls.MenuItem.Checked>, <xref:System.Windows.Controls.MenuItem.Unchecked>, e <xref:System.Windows.Controls.MenuItem.Click> eventi.  
  
 [!code-xaml[MenuItemCommandsAndEvents#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>   
## <a name="menuitems-with-keyboard-shortcuts"></a>MenuItems con abbreviazioni da tastiera  
 Tasti di scelta rapida sono combinazioni di caratteri che possono essere immessi con la tastiera per richiamare <xref:System.Windows.Controls.Menu> comandi. Il collegamento per **Copia** ad esempio è CTRL+C. Sono disponibili due proprietà da usare con voci di menu e tasti di scelta rapida, ovvero<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> o <xref:System.Windows.Controls.MenuItem.Command%2A>.  
  
<a name="menus_inputgesturetext"></a>   
### <a name="inputgesturetext"></a>InputGestureText  
 Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> proprietà per assegnare testo di scelta rapida da tastiera per <xref:System.Windows.Controls.MenuItem> controlli. In questo modo nella voce di menu vengono inserite solo le abbreviazioni da tastiera.  Non viene associato il comando con il <xref:System.Windows.Controls.MenuItem>. L'applicazione deve gestire l'input dell'utente per eseguire l'azione.  
  
 [!code-xaml[MenuEvent#6](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>   
### <a name="command"></a>Comando  
 Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Controls.MenuItem.Command%2A> proprietà per associare il **aperta** e **salvare** i comandi con <xref:System.Windows.Controls.MenuItem> controlli. Non solo la proprietà command associare un comando con un <xref:System.Windows.Controls.MenuItem>, ma fornisce anche il testo di input da usare come alternativa.  
  
 [!code-xaml[MenuEvent#8](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 Il <xref:System.Windows.Controls.MenuItem> classe include anche un <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> proprietà che specifica l'elemento in cui si verifica il comando. Se <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> non è impostato, l'elemento con lo stato attivo riceve il comando. Per altre informazioni sui comandi vedere [Cenni preliminari sull'esecuzione di comandi](../advanced/commanding-overview.md).  
  
<a name="menu_styling"></a>   
## <a name="menu-styling"></a>Applicazione di stili al testo  
 Con lo stile di controllo, è possibile modificare in modo significativo l'aspetto e il comportamento di <xref:System.Windows.Controls.Menu> controlli senza dover scrivere un controllo personalizzato. Oltre a impostare proprietà visive, è anche possibile applicare un <xref:System.Windows.Style> a singole parti di un controllo, modificare il comportamento delle parti del controllo tramite le proprietà, oppure aggiungere parti aggiuntive o modificare il layout di un controllo. Gli esempi seguenti illustrano diversi modi per aggiungere un <xref:System.Windows.Style> a un <xref:System.Windows.Controls.Menu> controllo.  
  
 Il primo esempio di codice definisce una <xref:System.Windows.Style> chiamato `Simple` che mostra come usare le impostazioni di sistema correnti nello stile. Il codice assegna il colore di `MenuHighlightBrush` come colore di sfondo del menu e `MenuTextBrush` come colore di primo piano del menu. Si noti l'uso delle chiavi di risorsa per assegnare i pennelli.  
  
 [!code-xaml[MenuStylesSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 L'esempio seguente usa <xref:System.Windows.Trigger> gli elementi che consentono di modificare l'aspetto di un <xref:System.Windows.Controls.MenuItem> in risposta a eventi che si verificano nel <xref:System.Windows.Controls.Menu>. Quando si sposta il puntatore del mouse su di <xref:System.Windows.Controls.Menu>, il colore primo piano e le caratteristiche del carattere delle voci di menu Modifica.  
  
 [!code-xaml[MenuStylesSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a>Vedere anche
- [Esempio di raccolta di controlli WPF](https://go.microsoft.com/fwlink/?LinkID=160053)
