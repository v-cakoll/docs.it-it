---
ms.openlocfilehash: a14395895c6be586c862d1b49aa6bf6669e4203a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "68238032"
---
### <a name="calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a>La chiamata di Items.Refresh su un controllo WPF ListBox, ListView o DataGrid con elementi selezionati può determinare la visualizzazione di elementi duplicati nell'elemento

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.5, la chiamata di ListBox.Items.Refresh dal codice mentre sono presenti elementi selezionati in un controllo <xref:System.Windows.Controls.ListBox?displayProperty=name> può causare la duplicazione degli elementi selezionati nell'elenco. Si verifica un problema analogo con <xref:System.Windows.Controls.ListView?displayProperty=name> e <xref:System.Windows.Controls.DataGrid?displayProperty=name>. Questo problema è risolto in .NET Framework 4.6.|
|Suggerimento|Questo problema può essere evitato deselezionando gli elementi a livello di codice prima della chiamata di <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=name>, per poi selezionarli di nuovo dopo il completamento della chiamata. In alternativa, questo problema è stato corretto in .NET Framework 4.6 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework.|
|Scope|Minorenne|
|Versione|4.5|
|Type|Runtime|
|API interessate|<ul><li><xref:System.Windows.Data.CollectionView.Refresh?displayProperty=nameWithType></li></ul>|
