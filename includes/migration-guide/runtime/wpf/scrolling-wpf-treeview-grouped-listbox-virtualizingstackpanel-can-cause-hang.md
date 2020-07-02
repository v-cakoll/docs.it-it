---
ms.openlocfilehash: 1be68c2968d0eaa9024007bcf37abf9e44c36f1c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622056"
---
### <a name="scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a>Lo scorrimento di un controllo TreeView WPF o ListBox raggruppato in un VirtualizingStackPanel può causare un blocco

#### <a name="details"></a>Dettagli

In .NET Framework 4.5, lo scorrimento di un controllo <xref:System.Windows.Controls.TreeView?displayProperty=fullName> WPF in un pannello Stack virtualizzato può causare blocchi se sono presenti margini nel viewport (tra gli elementi nel controllo <xref:System.Windows.Controls.TreeView?displayProperty=fullName>, ad esempio, o in un elemento ItemsPresenter). In alcuni casi, inoltre, elementi di dimensioni diverse nella visualizzazione possono causare instabilità anche se non sono presenti margini.

#### <a name="suggestion"></a>Suggerimento

È possibile evitare questo bug eseguendo l'aggiornamento a .NET Framework 4.5.1. In alternativa, i margini possono essere rimossi dalle raccolte di visualizzazioni (ad esempio <xref:System.Windows.Controls.TreeView?displayProperty=fullName>) all'interno di pannelli Stack virtualizzati, se tutti gli elementi contenuti sono della stessa dimensione.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Principale|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)?displayProperty=nameWithType></li></ul>|
