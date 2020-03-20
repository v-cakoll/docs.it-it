---
ms.openlocfilehash: 735278848cb7399e414a128afc650a0a1f882337
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857479"
---
### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a>La modifica della proprietà IsEnabled dell'elemento padre di un controllo TextBlock influisce sui controlli figlio

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.6.2, la modifica della proprietà <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> dell'elemento padre di un controllo <xref:System.Windows.Controls.TextBlock?displayProperty=name> influisce sui controlli figlio, ad esempio collegamenti ipertestuali e pulsanti, del controllo <xref:System.Windows.Controls.TextBlock?displayProperty=name>. In .NET Framework 4.6.1 e versioni precedenti i controlli all'interno di <xref:System.Windows.Controls.TextBlock?displayProperty=name> non sempre riflettono lo stato della proprietà <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> dell'elemento padre <xref:System.Windows.Controls.TextBlock?displayProperty=name>.|
|Suggerimento|No. Questa modifica è conforme al comportamento previsto per i controlli all'interno di un controllo <xref:System.Windows.Controls.TextBlock?displayProperty=name>.|
|Scope|Minorenne|
|Versione|4.6.2|
|Type|Runtime|
|API interessate|<ul><li><xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType></li></ul>|
