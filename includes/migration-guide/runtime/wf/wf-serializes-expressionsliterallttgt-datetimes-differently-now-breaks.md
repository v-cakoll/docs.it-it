---
ms.openlocfilehash: 87013a04f7ff975e40a3c49c41c1c5acc2374066
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620411"
---
### <a name="wf-serializes-expressionsliterallttgt-datetimes-differently-now-breaks-custom-xaml-parsers"></a>WF serializza ora gli oggetti DateTimes Expressions.Literal&lt;T&gt; in modo diverso (interrompe i parser XAML personalizzati)

#### <a name="details"></a>Dettagli

L'oggetto <xref:System.Windows.Markup.ValueSerializer> associato convertirà un oggetto <xref:System.DateTime?displayProperty=fullName> o <xref:System.DateTimeOffset?displayProperty=fullName> i cui componenti Second e <xref:System.DateTime.Millisecond?displayProperty=fullName> sono diversi da zero e (per un valore <xref:System.DateTime?displayProperty=fullName>) la cui proprietà <xref:System.DateTime.Kind> non è Unspecified nella sintassi degli elementi di proprietà anziché una stringa. Tale modifica consente di eseguire il round trip dei valori di <xref:System.DateTime?displayProperty=fullName> e <xref:System.DateTimeOffset?displayProperty=fullName>. I parser XAML personalizzati che presuppongono che il codice XAML di input si trovi nella sintassi degli attributi non funzioneranno correttamente.

#### <a name="suggestion"></a>Suggerimento

Tale modifica consente di eseguire il round trip dei valori di <xref:System.DateTime?displayProperty=fullName> e <xref:System.DateTimeOffset?displayProperty=fullName>. I parser XAML personalizzati che presuppongono che il codice XAML di input si trovi nella sintassi degli attributi non funzioneranno correttamente.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime|
