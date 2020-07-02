---
ms.openlocfilehash: cd59818fe674e10a206725bea8a74c4aceed99b1
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620470"
---
### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a>Il testo selezionato nel controllo TextBox WPF viene visualizzato con un colore diverso quando la casella di testo è inattiva

#### <a name="details"></a>Dettagli

In .NET Framework 4.5, se una casella di testo WPF è inattiva (non ha lo stato attivo), il testo selezionato nella casella verrà visualizzato con un colore diverso rispetto a quando il controllo è attivo.

#### <a name="suggestion"></a>Suggerimento

È possibile ripristinare il comportamento precedente di .NET Framework 4.0 impostando la proprietà <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> su <code>false</code>.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
