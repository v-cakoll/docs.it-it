---
ms.openlocfilehash: af8cb9435be078351e3430dc8ded3f7cac377948
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620497"
---
### <a name="wpf-treeviewitem-must-be-used-within-a-treeview"></a>TreeViewItem WPF va usato in una TreeView

#### <a name="details"></a>Dettagli

È stata introdotta una modifica nella versione 4.5 che limita l'uso di elementi <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> all'esterno di una <xref:System.Windows.Controls.TreeView?displayProperty=fullName>. Il problema può presentarsi nelle condizioni seguenti:<ul><li>L'elemento padre visivo di <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> non è un pannello. (L'elemento padre di un <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> generato per una <xref:System.Windows.Controls.TreeView?displayProperty=fullName> sarà un pannello)</li><li><xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> è un discendente di un <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> che funge da &quot;host di elementi&quot; per un controllo elenco (ListBox, DataGrid, ListView e così via). La virtualizzazione non deve essere abilitata.</li><li><xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> prevede lo scorrimento per elementi (<code>ScrollUnit=&quot;Item&quot;</code>).</li><li>Qualcuno chiama <code>VirtualizingStackPanel.MakeVisible(v)</code> per scorrere fino a un elemento <code>v</code> e visualizzarlo. Questa operazione può essere eseguita in modo esplicito o implicito in diversi modi. Probabilmente il modo più comune è il semplice clic su <code>v</code> per spostare lo stato attivo della tastiera sull'elemento.</li><li>La catena elemento padre visivo da <code>v</code> a <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> passa attraverso <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName>.</li></ul>In altre parole, questo si verifica quando si usa un elemento <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> all'esterno di un <xref:System.Windows.Controls.TreeView?displayProperty=fullName> e l'utente fa clic su un discendente di <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> per visualizzarlo. Se non vi sono discendenti attivabili per <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> non si noterà mai il problema. Un esempio di situazione in cui si verifica questo problema è quando un <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> corrisponde alla radice di un DataTemplate. Quando si verifica il problema, viene generata un'eccezione InvalidCastException all'interno del framework WPF.

#### <a name="suggestion"></a>Suggerimento

Verrà reso disponibile un hotfix per questo problema.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.5|
|Type|Runtime|
