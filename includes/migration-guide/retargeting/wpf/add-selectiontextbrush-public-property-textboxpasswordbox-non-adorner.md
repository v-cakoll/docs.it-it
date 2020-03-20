---
ms.openlocfilehash: e04134ec731c5e7bede3388621078c6518805ec2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803477"
---
### <a name="add-selectiontextbrush-public-property-to-textboxpasswordbox-non-adorner-selection"></a>Aggiungere la proprietà pubblica SelectionTextBrush alla selezione non basata su Adorner TextBox/PasswordBox

|   |   |
|---|---|
|Dettagli|Nelle applicazioni WPF l'uso della [selezione testo non basata su Adorner](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-TextBox-PasswordBox-text-selection-does-not-follow-system-colors.md) per <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.PasswordBox> consente ora agli sviluppatori di impostare la nuova proprietà SelectionTextBrush per modificare il rendering del testo selezionato.  Per impostazione predefinita, questo colore viene modificato con <xref:System.Windows.SystemColors.HighlightTextBrushKey>.  Se la selezione testo non basata su Adorner non è abilitata, questa proprietà non produce alcun effetto.|
|Suggerimento|Dopo che la selezione testo non basata su Adorner è stata abilitata, è possibile usare le proprietà <xref:System.Windows.Controls.PasswordBox.SelectionTextBrush?displayProperty=nameWithType> e <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush> per modificare l'aspetto del testo selezionato. A tale scopo, usare XAML:<pre><code class="lang-xaml">&lt;TextBox SelectionBrush=&quot;Red&quot; SelectionTextBrush=&quot;White&quot;  SelectionOpacity=&quot;0.5&quot;&#13;&#10;Foreground=&quot;Blue&quot; CaretBrush=&quot;Blue&quot;&gt;&#13;&#10;This is some text.&#13;&#10;&lt;/TextBox&gt;&#13;&#10;</code></pre>|
|Scope|Principale|
|Versione|4.8|
|Type|Ridestinazione|
|API interessate|<ul><li><xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrushProperty?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush?displayProperty=nameWithType></li><li>[System.Windows.Controls.TextBox](xref:System.Windows.Controls.TextBox)</li><li>[System.Windows.Controls.PasswordBox](xref:System.Windows.Controls.PasswordBox)</li></ul>|
