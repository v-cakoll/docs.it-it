---
title: Cenni preliminari sulla classe Menu
ms.date: 03/30/2017
helpviewer_keywords:
- Menu control [WPF]
- controls [WPF], Menu
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
ms.openlocfilehash: 53bc8f10e61b6e4e9e1f3b9a484340d9e2ec2a85
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186965"
---
# <a name="menu-overview"></a>Cenni preliminari sulla classe Menu
La <xref:System.Windows.Controls.Menu> classe consente di organizzare gli elementi associati ai comandi e ai gestori eventi in un ordine gerarchico. Ogni <xref:System.Windows.Controls.Menu> elemento contiene <xref:System.Windows.Controls.MenuItem> una raccolta di elementi.  

<a name="menu_control"></a>
## <a name="menu-control"></a>Controllo Menu  
 Il <xref:System.Windows.Controls.Menu> controllo presenta un elenco di elementi che specificano comandi o opzioni per un'applicazione. In genere, <xref:System.Windows.Controls.MenuItem> facendo clic su un apre un sottomenu o viene emesso un comando da parte di un'applicazione.  
  
<a name="creating_menus"></a>
## <a name="creating-menus"></a>Creazione di menu  
 Nell'esempio riportato di seguito viene creato un <xref:System.Windows.Controls.Menu> oggetto per modificare il testo in un oggetto <xref:System.Windows.Controls.TextBox>. L'oggetto <xref:System.Windows.Controls.Menu> <xref:System.Windows.Controls.MenuItem> contiene <xref:System.Windows.Controls.MenuItem.Command%2A>oggetti <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>che <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> utilizzano <xref:System.Windows.Controls.MenuItem.Checked> <xref:System.Windows.Controls.MenuItem.Unchecked>le <xref:System.Windows.Controls.MenuItem.Click> proprietà , e e gli eventi , e .  
  
 [!code-xaml[MenuItemCommandsAndEvents#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>
## <a name="menuitems-with-keyboard-shortcuts"></a>MenuItems con abbreviazioni da tastiera  
 I tasti di scelta rapida sono combinazioni <xref:System.Windows.Controls.Menu> di caratteri che possono essere immesse con la tastiera per richiamare i comandi. Il collegamento per **Copia** ad esempio è CTRL+C. Sono disponibili due proprietà da utilizzare con<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> <xref:System.Windows.Controls.MenuItem.Command%2A>i tasti di scelta rapida e le voci di menu, oppure .  
  
<a name="menus_inputgesturetext"></a>
### <a name="inputgesturetext"></a>InputGestureText  
 Nell'esempio seguente viene <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> illustrato come utilizzare la <xref:System.Windows.Controls.MenuItem> proprietà per assegnare il testo da tastiera ai controlli. In questo modo nella voce di menu vengono inserite solo le abbreviazioni da tastiera.  Non associa il comando <xref:System.Windows.Controls.MenuItem>all'oggetto . L'applicazione deve gestire l'input dell'utente per eseguire l'azione.  
  
 [!code-xaml[MenuEvent#6](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>
### <a name="command"></a>Comando  
 Nell'esempio seguente viene <xref:System.Windows.Controls.MenuItem.Command%2A> illustrato come utilizzare la proprietà <xref:System.Windows.Controls.MenuItem> per associare i comandi **Open** e **Save** ai controlli. Non solo la proprietà command associa <xref:System.Windows.Controls.MenuItem>un comando a un oggetto , ma fornisce anche il testo del movimento di input da utilizzare come scelta rapida.  
  
 [!code-xaml[MenuEvent#8](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 La <xref:System.Windows.Controls.MenuItem> classe dispone <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> anche di una proprietà , che specifica l'elemento in cui si verifica il comando. Se <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> non è impostato, l'elemento con lo stato attivo della tastiera riceve il comando. Per altre informazioni sui comandi vedere [Cenni preliminari sull'esecuzione di comandi](../advanced/commanding-overview.md).  
  
<a name="menu_styling"></a>
## <a name="menu-styling"></a>Applicazione di stili al testo  
 Con lo stile dei controlli, è <xref:System.Windows.Controls.Menu> possibile modificare notevolmente l'aspetto e il comportamento dei controlli senza dover scrivere un controllo personalizzato. Oltre a impostare le proprietà visive, è anche possibile applicare un <xref:System.Windows.Style> oggetto a singole parti di un controllo, modificare il comportamento di parti del controllo tramite proprietà o aggiungere parti aggiuntive o modificare il layout di un controllo. Negli esempi seguenti vengono illustrati <xref:System.Windows.Style> diversi <xref:System.Windows.Controls.Menu> modi per aggiungere un oggetto a un controllo.  
  
 Nel primo esempio di <xref:System.Windows.Style> `Simple` codice viene definita una chiamata che mostra come utilizzare le impostazioni di sistema correnti nello stile. Il codice assegna il colore di `MenuHighlightBrush` come colore di sfondo del menu e `MenuTextBrush` come colore di primo piano del menu. Si noti l'uso delle chiavi di risorsa per assegnare i pennelli.  
  
 [!code-xaml[MenuStylesSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 Nell'esempio <xref:System.Windows.Trigger> seguente vengono utilizzati elementi che <xref:System.Windows.Controls.MenuItem> consentono di modificare l'aspetto di un in risposta agli eventi che si verificano nel <xref:System.Windows.Controls.Menu>file . Quando si sposta il <xref:System.Windows.Controls.Menu>mouse sul , il colore di primo piano e le caratteristiche del carattere delle voci di menu cambiano.  
  
 [!code-xaml[MenuStylesSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a>Vedere anche

- [Esempio di raccolta di controlli WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
