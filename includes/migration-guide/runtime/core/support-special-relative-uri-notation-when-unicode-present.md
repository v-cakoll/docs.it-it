---
ms.openlocfilehash: c8a6870a9d34889dd8f5305035744bfc63be6af6
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760738"
---
### <a name="support-special-relative-uri-notation-when-unicode-is-present"></a>Supporto della notazione URI relativa speciale quando è presente Unicode

|   |   |
|---|---|
|Dettagli|<xref:System.Uri> non genera più <xref:System.NullReferenceException> quando si chiama <xref:System.Uri.TryCreate%2A> per URI relativi specifici contenenti Unicode. Di seguito è riportata la riproduzione più semplice di <xref:System.NullReferenceException>, con le due istruzioni equivalenti:<pre><code class="lang-csharp">bool success = Uri.TryCreate(&quot;http:%C3%A8&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;bool success = Uri.TryCreate(&quot;http:&#232;&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;</code></pre>Per riprodurre <xref:System.NullReferenceException>, gli elementi seguenti devono essere true:<ul><li>L'URI deve essere specificato come relativo, anteponendo 'http:' non seguito da '//'.</li><li>L'URI deve contenere Unicode codificato in percentuale o simboli non riservati.</li></ul>|
|Suggerimento|Gli utenti che si basano su questo comportamento per impedire l'uso di URI relativi devono invece specificare <xref:System.UriKind.Absolute?displayProperty=nameWithType> al momento della creazione di un URI.|
|Ambito|Microsoft Edge|
|Versione|4.7.2|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType></li></ul>|

