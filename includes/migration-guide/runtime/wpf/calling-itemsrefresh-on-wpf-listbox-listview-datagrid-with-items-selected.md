---
ms.openlocfilehash: 710d1517397f423fa40cc0c4a26c3499aac6179e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620422"
---
### <a name="calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a>La chiamata di Items.Refresh su un controllo WPF ListBox, ListView o DataGrid con elementi selezionati può determinare la visualizzazione di elementi duplicati nell'elemento

#### <a name="details"></a>Dettagli

In .NET Framework 4.5, la chiamata di ListBox.Items.Refresh dal codice mentre sono presenti elementi selezionati in un controllo <xref:System.Windows.Controls.ListBox?displayProperty=fullName> può causare la duplicazione degli elementi selezionati nell'elenco. Si verifica un problema analogo con <xref:System.Windows.Controls.ListView?displayProperty=fullName> e <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>. Questo problema è risolto in .NET Framework 4.6.

#### <a name="suggestion"></a>Suggerimento

Questo problema può essere evitato deselezionando gli elementi a livello di codice prima della chiamata di <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=fullName>, per poi selezionarli di nuovo dopo il completamento della chiamata. In alternativa, questo problema è stato corretto in .NET Framework 4.6 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Windows.Data.CollectionView.Refresh?displayProperty=nameWithType></li></ul>|
