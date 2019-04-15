---
ms.openlocfilehash: 0887379fb23e9e66c6cc55a3774545162634c3f0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236710"
---
### <a name="scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a>Lo scorrimento di un controllo TreeView WPF o ListBox raggruppato in un VirtualizingStackPanel può causare un blocco

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.5, lo scorrimento di un controllo <xref:System.Windows.Controls.TreeView?displayProperty=name> WPF in un pannello Stack virtualizzato può causare blocchi se sono presenti margini nel viewport (tra gli elementi nel controllo <xref:System.Windows.Controls.TreeView?displayProperty=name>, ad esempio, o in un elemento ItemsPresenter). In alcuni casi, inoltre, elementi di dimensioni diverse nella visualizzazione possono causare instabilità anche se non sono presenti margini.|
|Suggerimento|È possibile evitare questo bug eseguendo l'aggiornamento a .NET Framework 4.5.1. In alternativa, i margini possono essere rimossi dalle raccolte di visualizzazioni (ad esempio <xref:System.Windows.Controls.TreeView?displayProperty=name>) all'interno di pannelli Stack virtualizzati, se tutti gli elementi contenuti sono della stessa dimensione.|
|Ambito|Principale|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)?displayProperty=nameWithType></li></ul>|
