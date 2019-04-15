---
ms.openlocfilehash: 14b8930044381d1d86ec7984d36a5c3588eebd81
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59233943"
---
### <a name="the-default-hash-algorithm-for-wpfs-markup-compiler-is-now-sha256"></a>SHA256 usato come nuovo algoritmo hash predefinito per il compilatore di markup di WPF

|   |   |
|---|---|
|Dettagli|MarkupCompiler WPF offre servizi di compilazione per i file di markup XAML.  In .NET Framework 4.7.1 e versioni precedenti, l'algoritmo hash predefinito usato per i checksum era SHA1. A causa di problemi di sicurezza recenti con SHA1, questa impostazione predefinita è stata cambiata in SHA256 a partire da .NET Framework 4.7.2.  Questa modifica interessa la generazione di tutti i checksum per i file di markup durante la compilazione.|
|Suggerimento|Uno sviluppatore che ha come destinazione .NET Framework 4.7.2 o versione successiva e vuole ripristinare SHA1 come comportamento hash deve impostare il flag AppContext seguente.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Markup.DoNotUseSha256ForMarkupCompilerChecksumAlgorithm=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Uno sviluppatore che vuole utilizzare l'hash SHA256 con una versione di .NET Framework precedente alla versione 4.7.2 come destinazione deve impostare il flag AppContext seguente.  Si noti che la versione installata di .NET Framework deve corrispondere alla versione 4.7.2 o successiva.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Markup.DoNotUseSha256ForMarkupCompilerChecksumAlgorithm=false&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Ambito|Trasparente|
|Versione|4.7.2|
|Tipo|Ridestinazione|
