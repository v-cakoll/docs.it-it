---
ms.openlocfilehash: d3e0a61601f60a389b662f6f74934b6e6dc6e663
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614915"
---
### <a name="the-default-hash-algorithm-for-wpf-packagedigitalsignaturemanager-is-now-sha256"></a>L'algoritmo hash predefinito per WPF PackageDigitalSignatureManager è ora SHA256

#### <a name="details"></a>Dettagli

`System.IO.Packaging.PackageDigitalSignatureManager` offre funzionalità per le firme digitali in relazione ai pacchetti WPF.  In .NET Framework 4.7 e versioni precedenti, l'algoritmo predefinito (<xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>) usato per firmare le parti di un pacchetto era SHA1.  A causa di problemi di sicurezza recenti con SHA1, questa impostazione predefinita è stata cambiata in SHA256 a partire da .NET Framework 4.7.1.  Questa modifica interessa la firma di tutti i pacchetti, inclusi i documenti XPS.

#### <a name="suggestion"></a>Suggerimento

Uno sviluppatore che vuole usare questa modifica per una versione del framework precedente a .NET Framework 4.7.1 o uno sviluppatore che richiede la funzionalità precedente per il framework .NET Framework 4.7.1 o versione successiva può impostare nel modo appropriato il flag AppContext seguente.  Se il valore è true viene usato come algoritmo predefinito SHA1; se è false viene usato SHA256.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.UseSha1AsDefaultHashAlgorithmForDigitalSignatures=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.7.1       |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>
