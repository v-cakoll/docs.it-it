---
ms.openlocfilehash: 395463225e3c1f1d168dd019ea75966ad54e5a8a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621259"
---
### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a>La modifica della proprietà IsEnabled dell'elemento padre di un controllo TextBlock influisce sui controlli figlio

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.6.2, la modifica della proprietà <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> dell'elemento padre di un controllo <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> influisce sui controlli figlio, ad esempio collegamenti ipertestuali e pulsanti, del controllo <xref:System.Windows.Controls.TextBlock?displayProperty=fullName>. In .NET Framework 4.6.1 e versioni precedenti i controlli all'interno di <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> non sempre riflettono lo stato della proprietà <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> dell'elemento padre <xref:System.Windows.Controls.TextBlock?displayProperty=fullName>.

#### <a name="suggestion"></a>Suggerimento

No. Questa modifica è conforme al comportamento previsto per i controlli all'interno di un controllo <xref:System.Windows.Controls.TextBlock?displayProperty=fullName>.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.6.2|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType></li></ul>|
