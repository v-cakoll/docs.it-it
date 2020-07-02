---
ms.openlocfilehash: 13d3799aeede86b01aa81ce1cd69b3c4c22311ca
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620482"
---
### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a>Il limite di annullamento predefinito per TextBox è 100

#### <a name="details"></a>Dettagli

In .NET Framework 4.5 il limite di annullamento predefinito per una casella di testo WPF è 100, anziché essere illimitato come in .NET Framework 4.0

#### <a name="suggestion"></a>Suggerimento

Se un limite di annullamento di 100 è troppo basso, il limite può essere impostato in modo esplicito con <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit>

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
