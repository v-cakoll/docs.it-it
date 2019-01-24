---
title: 'Procedura: Trovare un oggetto TreeViewItem in un oggetto TreeView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], finding a TreeViewItem
- TreeViewItem [WPF], finding
ms.assetid: 72ecd40c-3939-4e01-b617-5e9daa6074d9
ms.openlocfilehash: bce4f059e76b0ebea29b023eba2e9e2f59813035
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54636027"
---
# <a name="how-to-find-a-treeviewitem-in-a-treeview"></a>Procedura: Trovare un oggetto TreeViewItem in un oggetto TreeView
Il <xref:System.Windows.Controls.TreeView> controllo fornisce un modo pratico per visualizzare i dati gerarchici. Se il <xref:System.Windows.Controls.TreeView> è associato a un'origine dati, il <xref:System.Windows.Controls.TreeView.SelectedItem%2A> proprietà fornisce un modo pratico per poter recuperare rapidamente l'oggetto dati selezionato. È in genere è preferibile utilizzare con l'oggetto dati sottostante, ma in alcuni casi potrebbe essere necessario modificare a livello di codice che contiene i dati <xref:System.Windows.Controls.TreeViewItem>. Ad esempio, potrebbe essere necessario espandere a livello di codice le <xref:System.Windows.Controls.TreeViewItem>, o selezionare un elemento diverso nella <xref:System.Windows.Controls.TreeView>.  
  
 Per trovare una <xref:System.Windows.Controls.TreeViewItem> che contiene un oggetto dati specifico, è necessario scorrere ogni livello del <xref:System.Windows.Controls.TreeView>. Gli elementi in un <xref:System.Windows.Controls.TreeView> può anche essere virtualizzato per migliorare le prestazioni. Nel caso in cui gli elementi potrebbero essere virtualizzati, è inoltre necessario tenere presente un <xref:System.Windows.Controls.TreeViewItem> per verificare se contiene l'oggetto dati.  
  
## <a name="example"></a>Esempio  
  
## <a name="description"></a>Descrizione  
 L'esempio seguente cerca un' <xref:System.Windows.Controls.TreeView> per un oggetto specifico e restituisce l'oggetto contenente <xref:System.Windows.Controls.TreeViewItem>. L'esempio garantisce che ogni <xref:System.Windows.Controls.TreeViewItem> viene creata un'istanza in modo che i relativi elementi figlio possono essere cercati. In questo esempio funziona anche se il <xref:System.Windows.Controls.TreeView> non usa gli elementi virtualizzati.  
  
> [!NOTE]
>  Nell'esempio seguente funziona per eventuali <xref:System.Windows.Controls.TreeView>, indipendentemente dal modello di dati sottostante e le ricerche ogni <xref:System.Windows.Controls.TreeViewItem> fino a quando non viene trovato l'oggetto. È un'altra tecnica che offre prestazioni migliori per cercare il modello di dati per l'oggetto specificato, tenere traccia della relativa posizione all'interno della gerarchia di dati e quindi trovare corrispondente <xref:System.Windows.Controls.TreeViewItem> nella <xref:System.Windows.Controls.TreeView>. Tuttavia, la tecnica che offre prestazioni migliori richiede la conoscenza del modello di dati e non può essere generalizzata per qualsiasi dato <xref:System.Windows.Controls.TreeView>.  
  
## <a name="code"></a>Codice  
 [!code-csharp[TreeViewFindTVI#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[TreeViewFindTVI#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#1)]  
  
 Il codice precedente si basa su una classe personalizzata <xref:System.Windows.Controls.VirtualizingStackPanel> che espone un metodo denominato `BringIntoView`. Il codice seguente definisce l'oggetto personalizzato <xref:System.Windows.Controls.VirtualizingStackPanel>.  
  
 [!code-csharp[TreeViewFindTVI#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#2)]
 [!code-vb[TreeViewFindTVI#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#2)]  
  
 il XAML seguente viene illustrato come creare un <xref:System.Windows.Controls.TreeView> che usa l'oggetto personalizzato <xref:System.Windows.Controls.VirtualizingStackPanel>.  
  
 [!code-xaml[TreeViewFindTVI#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml#3)]  
  
## <a name="see-also"></a>Vedere anche
- [Migliorare le prestazioni di un controllo TreeView](../../../../docs/framework/wpf/controls/how-to-improve-the-performance-of-a-treeview.md)
