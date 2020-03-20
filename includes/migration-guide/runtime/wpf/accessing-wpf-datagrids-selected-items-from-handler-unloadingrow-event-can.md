---
ms.openlocfilehash: cda5df4b673412a7c8c59f80f89c19c13dc81dc1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858388"
---
### <a name="accessing-a-wpf-datagrids-selected-items-from-a-handler-of-the-datagrids-unloadingrow-event-can-cause-a-nullreferenceexception"></a>L'accesso agli elementi selezionati di un elemento DataGrid WPF da parte di un gestore dell'evento UnloadingRow di DataGrid può determinare un'eccezione NullReferenceException

|   |   |
|---|---|
|Dettagli|A causa di un bug in .NET Framework 4.5, i gestori eventi per gli eventi <xref:System.Windows.Controls.DataGrid> che includono la rimozione di una riga possono originare un'eccezione <xref:System.NullReferenceException?displayProperty=name> se accedono alle proprietà <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=name> o <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> di <xref:System.Windows.Controls.DataGrid>.|
|Suggerimento|Questo problema è stato corretto in .NET Framework 4.6 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework.|
|Scope|Minorenne|
|Versione|4.5|
|Type|Runtime|
|API interessate|<ul><li><xref:System.Windows.Controls.DataGrid.UnloadingRow?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.UnloadingRowDetails?displayProperty=nameWithType></li></ul>|
