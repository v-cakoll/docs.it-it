---
ms.openlocfilehash: 335647f899c79eff22e313fa40b2e2a73e7cfff0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379525"
---
### <a name="wf-serializes-expressionsliteralt-datetimes-differently-now-breaks-custom-xaml-parsers"></a>WF serializza ora gli oggetti DateTimes Expressions.Literal\<T> in modo diverso (interrompe i parser XAML personalizzati)

|   |   |
|---|---|
|Dettagli|L'oggetto <xref:System.Windows.Markup.ValueSerializer> associato convertirà un oggetto <xref:System.DateTime?displayProperty=name> o <xref:System.DateTimeOffset?displayProperty=name> i cui componenti Second e <xref:System.DateTime.Millisecond?displayProperty=name> sono diversi da zero e (per un valore <xref:System.DateTime?displayProperty=name>) la cui proprietà <xref:System.DateTime.Kind> non è Unspecified nella sintassi degli elementi di proprietà anziché una stringa. Tale modifica consente di eseguire il round trip dei valori di <xref:System.DateTime?displayProperty=name> e <xref:System.DateTimeOffset?displayProperty=name>. I parser XAML personalizzati che presuppongono che il codice XAML di input si trovi nella sintassi degli attributi non funzioneranno correttamente.|
|Suggerimento|Tale modifica consente di eseguire il round trip dei valori di <xref:System.DateTime?displayProperty=name> e <xref:System.DateTimeOffset?displayProperty=name>. I parser XAML personalizzati che presuppongono che il codice XAML di input si trovi nella sintassi degli attributi non funzioneranno correttamente.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|
