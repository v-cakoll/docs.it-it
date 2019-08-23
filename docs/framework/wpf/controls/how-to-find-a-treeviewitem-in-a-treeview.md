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
ms.openlocfilehash: ad72c7a7fb11dfe605db4119dde831b47dd7c5a4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962087"
---
# <a name="how-to-find-a-treeviewitem-in-a-treeview"></a>Procedura: Trovare un oggetto TreeViewItem in un oggetto TreeView
Il <xref:System.Windows.Controls.TreeView> controllo fornisce un modo pratico per visualizzare i dati gerarchici. Se il <xref:System.Windows.Controls.TreeView> è associato a un'origine dati, la <xref:System.Windows.Controls.TreeView.SelectedItem%2A> proprietà rappresenta un modo pratico per recuperare rapidamente l'oggetto dati selezionato. In genere è consigliabile usare l'oggetto dati sottostante, ma in alcuni casi potrebbe essere necessario modificare a livello di codice i dati che <xref:System.Windows.Controls.TreeViewItem>contengono. Ad esempio, potrebbe essere necessario espandere <xref:System.Windows.Controls.TreeViewItem>a livello di codice o selezionare un altro elemento <xref:System.Windows.Controls.TreeView>in.  
  
 Per trovare un <xref:System.Windows.Controls.TreeViewItem> oggetto che contiene un oggetto dati specifico, è necessario attraversare ogni livello <xref:System.Windows.Controls.TreeView>di. Gli elementi in un <xref:System.Windows.Controls.TreeView> oggetto possono anche essere virtualizzati per migliorare le prestazioni. Nel caso in cui gli elementi potrebbero essere virtualizzati, è necessario anche realizzare <xref:System.Windows.Controls.TreeViewItem> un per verificare se contiene l'oggetto dati.  
  
## <a name="example"></a>Esempio  
  
## <a name="description"></a>Descrizione  
 Nell'esempio seguente viene eseguita <xref:System.Windows.Controls.TreeView> la ricerca di un oggetto specifico e viene restituito il <xref:System.Windows.Controls.TreeViewItem>contenitore dell'oggetto. L'esempio garantisce che venga <xref:System.Windows.Controls.TreeViewItem> creata un'istanza di ogni oggetto in modo che sia possibile cercare i relativi elementi figlio. Questo esempio funziona anche se <xref:System.Windows.Controls.TreeView> non usa elementi virtualizzati.  
  
> [!NOTE]
> Nell'esempio seguente viene utilizzato per <xref:System.Windows.Controls.TreeView>qualsiasi, indipendentemente dal modello di dati sottostante, e viene <xref:System.Windows.Controls.TreeViewItem> eseguita una ricerca ogni finché l'oggetto non viene trovato. Un'altra tecnica che offre prestazioni migliori consiste nel cercare il modello di dati per l'oggetto specificato, tenere traccia della relativa posizione all'interno della gerarchia dei dati e quindi <xref:System.Windows.Controls.TreeViewItem> trovare il <xref:System.Windows.Controls.TreeView>corrispondente in. Tuttavia, la tecnica che offre prestazioni migliori richiede la conoscenza del modello di dati e non può essere generalizzata per <xref:System.Windows.Controls.TreeView>un dato.  
  
## <a name="code"></a>Codice  
 [!code-csharp[TreeViewFindTVI#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[TreeViewFindTVI#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#1)]  
  
 Il codice precedente si basa su un oggetto <xref:System.Windows.Controls.VirtualizingStackPanel> personalizzato che espone un metodo `BringIntoView`denominato. Il codice seguente definisce l'oggetto <xref:System.Windows.Controls.VirtualizingStackPanel>personalizzato.  
  
 [!code-csharp[TreeViewFindTVI#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#2)]
 [!code-vb[TreeViewFindTVI#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#2)]  
  
 Nel codice XAML seguente viene illustrato come creare <xref:System.Windows.Controls.TreeView> un oggetto che utilizza <xref:System.Windows.Controls.VirtualizingStackPanel>l'oggetto personalizzato.  
  
 [!code-xaml[TreeViewFindTVI#3](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml#3)]  
  
## <a name="see-also"></a>Vedere anche

- [Migliorare le prestazioni di un controllo TreeView](how-to-improve-the-performance-of-a-treeview.md)
