---
ms.openlocfilehash: de79182e326082786c1e0691f8888e30cd410f5d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235416"
---
### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a>Il limite di annullamento predefinito per TextBox è 100

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.5 il limite di annullamento predefinito per una casella di testo WPF è 100, anziché essere illimitato come in .NET Framework 4.0|
|Suggerimento|Se un limite di annullamento di 100 è troppo basso, il limite può essere impostato in modo esplicito con <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit>|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
