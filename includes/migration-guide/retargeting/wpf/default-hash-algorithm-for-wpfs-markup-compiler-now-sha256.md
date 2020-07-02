---
ms.openlocfilehash: 4303b177ffe01328965c909a5a3809414fcead91
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614929"
---
### <a name="the-default-hash-algorithm-for-wpfs-markup-compiler-is-now-sha256"></a>SHA256 usato come nuovo algoritmo hash predefinito per il compilatore di markup di WPF

#### <a name="details"></a>Dettagli

MarkupCompiler WPF offre servizi di compilazione per i file di markup XAML.  In .NET Framework 4.7.1 e versioni precedenti, l'algoritmo hash predefinito usato per i checksum era SHA1. A causa di problemi di sicurezza recenti con SHA1, questa impostazione predefinita è stata cambiata in SHA256 a partire da .NET Framework 4.7.2.  Questa modifica interessa la generazione di tutti i checksum per i file di markup durante la compilazione.

#### <a name="suggestion"></a>Suggerimento

Uno sviluppatore che ha come destinazione .NET Framework 4.7.2 o versione successiva e vuole ripristinare SHA1 come comportamento hash deve impostare il flag AppContext seguente.

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Markup.DoNotUseSha256ForMarkupCompilerChecksumAlgorithm=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

Uno sviluppatore che vuole utilizzare l'hash SHA256 con una versione di .NET Framework precedente alla versione 4.7.2 come destinazione deve impostare il flag AppContext seguente.  Si noti che la versione installata di .NET Framework deve corrispondere alla versione 4.7.2 o successiva.

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Markup.DoNotUseSha256ForMarkupCompilerChecksumAlgorithm=false&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Modalità trasparente |
| Version | 4.7.2       |
| Type    | Ridestinazione |
