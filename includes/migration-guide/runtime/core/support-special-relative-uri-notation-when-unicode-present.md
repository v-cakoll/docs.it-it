---
ms.openlocfilehash: 841cb06bf94844d9f4da9dc33e60bad0d43dcd84
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "70997638"
---
### <a name="support-special-relative-uri-notation-when-unicode-is-present"></a>Supporto della notazione URI relativa speciale quando è presente Unicode

|   |   |
|---|---|
|Dettagli|<xref:System.Uri>non genererà <xref:System.NullReferenceException> più <xref:System.Uri.TryCreate%2A> un quando si chiama su determinati URI relativi contenenti Unicode. La riproduzione più <xref:System.NullReferenceException> semplice del è di seguito, con le due affermazioni equivalenti:<pre><code class="lang-csharp">bool success = Uri.TryCreate(&quot;http:%C3%A8&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;bool success = Uri.TryCreate(&quot;http:&#232;&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;</code></pre>Per riprodurre <xref:System.NullReferenceException>, gli elementi seguenti devono essere true:<ul><li>L'URI deve essere specificato come relativo, anteponendo 'http:' non seguito da '//'.</li><li>L'URI deve contenere Unicode codificato in percentuale o simboli non riservati.</li></ul>|
|Suggerimento|Gli utenti che si basano su questo comportamento per impedire l'uso di URI relativi devono invece specificare <xref:System.UriKind.Absolute?displayProperty=nameWithType> al momento della creazione di un URI.|
|Scope|Microsoft Edge|
|Versione|4.7.2|
|Type|Runtime|
|API interessate|<ul><li><xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType></li></ul>|
