---
ms.openlocfilehash: 53fc2a51a7995e9b6ad43e28429313d2aea9abf1
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/30/2019
ms.locfileid: "66379249"
---
### <a name="scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-result-in-an-unresponsive-application"></a>Lo scorrimento di un controllo TreeView WPF o ListBox raggruppato in VirtualizingStackPanel può causare rallentare la risposta di un'applicazione

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.5 lo scorrimento di un controllo <xref:System.Windows.Controls.TreeView?displayProperty=name> WPF in un pannello Stack virtualizzato può rallentare la risposta di un'applicazione se sono presenti margini nel viewport (ad esempio tra gli elementi nel controllo <xref:System.Windows.Controls.TreeView?displayProperty=name> oppure in un elemento ItemsPresenter). In alcuni casi, inoltre, elementi di dimensioni diverse nella visualizzazione possono causare instabilità anche se non sono presenti margini.|
|Suggerimento|È possibile evitare questo bug eseguendo l'aggiornamento a .NET Framework 4.5.1. In alternativa, i margini possono essere rimossi dalle raccolte di visualizzazioni (ad esempio <xref:System.Windows.Controls.TreeView?displayProperty=name>) all'interno di pannelli Stack virtualizzati, se tutti gli elementi contenuti sono della stessa dimensione.|
|Ambito|Principale|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)?displayProperty=nameWithType></li></ul>|
