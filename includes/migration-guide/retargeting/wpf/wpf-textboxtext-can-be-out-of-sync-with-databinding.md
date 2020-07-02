---
ms.openlocfilehash: d0de1a262d57c67dd4dfb258d5ac013af5d8783d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617231"
---
### <a name="wpf-textboxtext-can-be-out-of-sync-with-databinding"></a>TextBox.Text di WPF può non essere sincronizzata con il data binding

#### <a name="details"></a>Dettagli

In alcuni casi, la proprietà <xref:System.Windows.Controls.TextBox.Text> riflette un valore precedente del valore della proprietà associata a dati se viene modificata durante un'operazione di scrittura di associazione dati.

#### <a name="suggestion"></a>Suggerimento

Non dovrebbe avere alcun impatto negativo. Tuttavia, è possibile ripristinare il comportamento precedente impostando la proprietà <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> su `false`.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.5         |
|Type|Ridestinazione

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType>
