---
ms.openlocfilehash: bae6d7c0f8843211c721c68ce6f16000b35b4401
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620458"
---
### <a name="new-enum-values-in-wpfs-pagerangeselection"></a>Nuovi valori enumerazione in PageRangeSelection di WPF

#### <a name="details"></a>Dettagli

Sono stati aggiunti due nuovi membri (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=fullName> e <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=fullName>) all'enumerazione <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>.

#### <a name="suggestion"></a>Suggerimento

Nella maggior parte dei casi queste modifiche non influiscono sul codice utente. È tuttavia consigliabile modificare il codice che dipende da un determinato numero di elementi esistenti nelle chiamate <xref:System.Enum.GetNames(System.Type)> o <xref:System.Enum.GetValues(System.Type)> per il tipo <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Windows.Controls.PageRangeSelection?displayProperty=nameWithType></li></ul>|
