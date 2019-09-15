---
ms.openlocfilehash: 841cb06bf94844d9f4da9dc33e60bad0d43dcd84
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70997638"
---
### <a name="support-special-relative-uri-notation-when-unicode-is-present"></a>Supporto della notazione URI relativa speciale quando è presente Unicode

|   |   |
|---|---|
|Dettagli|<xref:System.Uri>non genererà più un <xref:System.NullReferenceException> oggetto quando <xref:System.Uri.TryCreate%2A> viene chiamato su determinati URI relativi che contengono Unicode. La riproduzione più semplice di <xref:System.NullReferenceException> è riportata di seguito, con due istruzioni equivalenti:<pre><code class="lang-csharp">bool success = Uri.TryCreate(&quot;http:%C3%A8&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;bool success = Uri.TryCreate(&quot;http:&#232;&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;</code></pre>Per riprodurre <xref:System.NullReferenceException>, gli elementi seguenti devono essere true:<ul><li>L'URI deve essere specificato come relativo, anteponendo 'http:' non seguito da '//'.</li><li>L'URI deve contenere Unicode codificato in percentuale o simboli non riservati.</li></ul>|
|Suggerimento|Gli utenti che si basano su questo comportamento per impedire l'uso di URI relativi devono invece specificare <xref:System.UriKind.Absolute?displayProperty=nameWithType> al momento della creazione di un URI.|
|Ambito|Microsoft Edge|
|Versione|4.7.2|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType></li></ul>|
