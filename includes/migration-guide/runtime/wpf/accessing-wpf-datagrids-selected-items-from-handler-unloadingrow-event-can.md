---
ms.openlocfilehash: 7ac0cac53ab2fa7657d0ae58f11d9e777631acc9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620437"
---
### <a name="accessing-a-wpf-datagrids-selected-items-from-a-handler-of-the-datagrids-unloadingrow-event-can-cause-a-nullreferenceexception"></a>L'accesso agli elementi selezionati di un elemento DataGrid WPF da parte di un gestore dell'evento UnloadingRow di DataGrid può determinare un'eccezione NullReferenceException

#### <a name="details"></a>Dettagli

A causa di un bug in .NET Framework 4.5, i gestori eventi per gli eventi <xref:System.Windows.Controls.DataGrid> che includono la rimozione di una riga possono originare un'eccezione <xref:System.NullReferenceException?displayProperty=fullName> se accedono alle proprietà <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=fullName> o <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> di <xref:System.Windows.Controls.DataGrid>.

#### <a name="suggestion"></a>Suggerimento

Questo problema è stato corretto in .NET Framework 4.6 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Windows.Controls.DataGrid.UnloadingRow?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.UnloadingRowDetails?displayProperty=nameWithType></li></ul>|
