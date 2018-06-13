---
title: 'Procedura: trovare un oggetto TreeViewItem in un oggetto TreeView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], finding a TreeViewItem
- TreeViewItem [WPF], finding
ms.assetid: 72ecd40c-3939-4e01-b617-5e9daa6074d9
ms.openlocfilehash: cff931312e6bc6db5ae5f26c0db80ad2f43825f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554755"
---
# <a name="how-to-find-a-treeviewitem-in-a-treeview"></a>Procedura: trovare un oggetto TreeViewItem in un oggetto TreeView
Il <xref:System.Windows.Controls.TreeView> controllo fornisce un modo pratico per visualizzare i dati gerarchici. Se il <xref:System.Windows.Controls.TreeView> è associato a un'origine dati, il <xref:System.Windows.Controls.TreeView.SelectedItem%2A> proprietà fornisce un modo pratico per recuperare rapidamente l'oggetto dati selezionato. È in genere preferibile utilizzare l'oggetto dati sottostante, ma talvolta potrebbe essere necessario modificare a livello di codice che contiene i dati <xref:System.Windows.Controls.TreeViewItem>. Ad esempio, potrebbe essere necessario espandere a livello di codice il <xref:System.Windows.Controls.TreeViewItem>, oppure selezionare un elemento diverso nella <xref:System.Windows.Controls.TreeView>.  
  
 Per trovare un <xref:System.Windows.Controls.TreeViewItem> che contiene un oggetto dati specifico, è necessario scorrere ogni livello del <xref:System.Windows.Controls.TreeView>. Gli elementi in un <xref:System.Windows.Controls.TreeView> può anche essere virtualizzato per migliorare le prestazioni. Nel caso in cui gli elementi potrebbero essere virtualizzati, è inoltre necessario eseguire un <xref:System.Windows.Controls.TreeViewItem> per verificare se contiene l'oggetto dati.  
  
## <a name="example"></a>Esempio  
  
## <a name="description"></a>Descrizione  
 Le ricerche di esempio seguente un <xref:System.Windows.Controls.TreeView> per un oggetto specifico e restituisce l'oggetto contenente <xref:System.Windows.Controls.TreeViewItem>. Nell'esempio garantisce che ogni <xref:System.Windows.Controls.TreeViewItem> viene creata un'istanza in modo che i relativi elementi figlio è possibile eseguire ricerche. Questo esempio funziona anche se il <xref:System.Windows.Controls.TreeView> non utilizza gli elementi virtualizzati.  
  
> [!NOTE]
>  Nell'esempio seguente è applicabile a qualsiasi <xref:System.Windows.Controls.TreeView>, indipendentemente dal modello di dati sottostante e ricerche ogni <xref:System.Windows.Controls.TreeViewItem> fino a quando non viene trovato l'oggetto. Un'altra tecnica che offre prestazioni migliori è eseguire ricerche nel modello di dati per l'oggetto specificato, tenere traccia della relativa posizione all'interno della gerarchia di dati e quindi individuare la corrispondente <xref:System.Windows.Controls.TreeViewItem> nel <xref:System.Windows.Controls.TreeView>. Tuttavia, la tecnica che offre prestazioni migliori richiede una conoscenza del modello di dati e non può essere generalizzata per un dato <xref:System.Windows.Controls.TreeView>.  
  
## <a name="code"></a>Codice  
 [!code-csharp[TreeViewFindTVI#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[TreeViewFindTVI#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#1)]  
  
 Il codice precedente si basa su un oggetto personalizzato <xref:System.Windows.Controls.VirtualizingStackPanel> che espone un metodo denominato `BringIntoView`. Il codice seguente definisce l'oggetto personalizzato <xref:System.Windows.Controls.VirtualizingStackPanel>.  
  
 [!code-csharp[TreeViewFindTVI#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#2)]
 [!code-vb[TreeViewFindTVI#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#2)]  
  
 Il codice XAML seguente viene illustrato come creare un <xref:System.Windows.Controls.TreeView> che utilizza l'oggetto personalizzato <xref:System.Windows.Controls.VirtualizingStackPanel>.  
  
 [!code-xaml[TreeViewFindTVI#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml#3)]  
  
## <a name="see-also"></a>Vedere anche  
 [Migliorare le prestazioni di un controllo TreeView](../../../../docs/framework/wpf/controls/how-to-improve-the-performance-of-a-treeview.md)
