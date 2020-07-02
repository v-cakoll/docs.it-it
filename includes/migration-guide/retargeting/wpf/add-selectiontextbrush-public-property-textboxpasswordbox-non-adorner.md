---
ms.openlocfilehash: aade03c29ff16053a97683499cf719a98ae33f3f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616266"
---
### <a name="add-selectiontextbrush-public-property-to-textboxpasswordbox-non-adorner-selection"></a>Aggiungere la proprietà pubblica SelectionTextBrush alla selezione non basata su Adorner TextBox/PasswordBox

#### <a name="details"></a>Dettagli

Nelle applicazioni WPF l'uso della [selezione testo non basata su Adorner](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-TextBox-PasswordBox-text-selection-does-not-follow-system-colors.md) per <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.PasswordBox> consente ora agli sviluppatori di impostare la nuova proprietà SelectionTextBrush per modificare il rendering del testo selezionato.  Per impostazione predefinita, questo colore viene modificato con <xref:System.Windows.SystemColors.HighlightTextBrushKey>.  Se la selezione testo non basata su Adorner non è abilitata, questa proprietà non produce alcun effetto.

#### <a name="suggestion"></a>Suggerimento

Dopo che la selezione testo non basata su Adorner è stata abilitata, è possibile usare le proprietà <xref:System.Windows.Controls.PasswordBox.SelectionTextBrush?displayProperty=nameWithType> e <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush> per modificare l'aspetto del testo selezionato. A tale scopo, usare XAML:

<pre><code class="lang-xaml">&lt;TextBox SelectionBrush=&quot;Red&quot; SelectionTextBrush=&quot;White&quot;  SelectionOpacity=&quot;0.5&quot;&#13;&#10;Foreground=&quot;Blue&quot; CaretBrush=&quot;Blue&quot;&gt;&#13;&#10;This is some text.&#13;&#10;&lt;/TextBox&gt;&#13;&#10;</code></pre>

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Principale       |
| Version | 4.8         |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrushProperty?displayProperty=nameWithType>
- <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush?displayProperty=nameWithType>
- [System.Windows.Controls.TextBox](xref:System.Windows.Controls.TextBox)
- [System.Windows.Controls.PasswordBox](xref:System.Windows.Controls.PasswordBox)
