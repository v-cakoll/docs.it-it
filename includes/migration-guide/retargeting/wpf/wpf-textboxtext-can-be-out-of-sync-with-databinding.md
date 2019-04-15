---
ms.openlocfilehash: 8b0617d8f021a9534289fd7ae8539cd054684862
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234686"
---
### <a name="wpf-textboxtext-can-be-out-of-sync-with-databinding"></a>TextBox.Text di WPF può non essere sincronizzata con il data binding

|   |   |
|---|---|
|Dettagli|In alcuni casi, la proprietà <xref:System.Windows.Controls.TextBox.Text> riflette un valore precedente del valore della proprietà associata a dati se viene modificata durante un'operazione di scrittura di associazione dati.|
|Suggerimento|Non dovrebbe avere alcun impatto negativo. Tuttavia, è possibile ripristinare il comportamento precedente impostando la proprietà <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> su <code>false</code>.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType></li></ul>|
