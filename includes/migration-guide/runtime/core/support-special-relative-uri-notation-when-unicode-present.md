---
ms.openlocfilehash: 08a9292c5a41e7b9b7c1bcc18ec96460de19863f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621184"
---
### <a name="support-special-relative-uri-notation-when-unicode-is-present"></a>Supporto della notazione URI relativa speciale quando è presente Unicode

#### <a name="details"></a>Dettagli

<xref:System.Uri>non genererà più un oggetto <xref:System.NullReferenceException> quando viene chiamato <xref:System.Uri.TryCreate%2A> su determinati URI relativi che contengono Unicode. La riproduzione più semplice di <xref:System.NullReferenceException> è riportata di seguito, con due istruzioni equivalenti:<pre><code class="lang-csharp">bool success = Uri.TryCreate(&quot;http:%C3%A8&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;bool success = Uri.TryCreate(&quot;http:&#232;&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;</code></pre>Per riprodurre <xref:System.NullReferenceException>, gli elementi seguenti devono essere true:<ul><li>L'URI deve essere specificato come relativo, anteponendo 'http:' non seguito da '//'.</li><li>L'URI deve contenere Unicode codificato in percentuale o simboli non riservati.</li></ul>

#### <a name="suggestion"></a>Suggerimento

Gli utenti che si basano su questo comportamento per impedire l'uso di URI relativi devono invece specificare <xref:System.UriKind.Absolute?displayProperty=nameWithType> al momento della creazione di un URI.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.7.2|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType></li></ul>|
