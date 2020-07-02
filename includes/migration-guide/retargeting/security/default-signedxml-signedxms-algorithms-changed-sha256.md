---
ms.openlocfilehash: e2ae329d027d605e6331afe422e550990fab1042
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614812"
---
### <a name="default-signedxml-and-signedxms-algorithms-changed-to-sha256"></a>Algoritmi predefiniti SignedXML e SignedXMS modificati in SHA256

#### <a name="details"></a>Dettagli

In .NET Framework 4.7 e versioni precedenti l'impostazione predefinita per SignedXML e SignedCMS era SHA1 per alcune operazioni. A partire da .NET Framework 4.7.1, per queste operazioni SHA256 è abilitato per impostazione predefinita. Questa modifica è necessaria perché SHA1 non è più considerato sicuro.

#### <a name="suggestion"></a>Suggerimento

Esistono due nuovi valori di cambio di contesto per controllare se per impostazione predefinita viene usato SHA1 (non sicuro) o SHA256:

- Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms
- Switch.System. Security. Cryptography. Pkcs. UseInsecureHashAlgorithms per le applicazioni destinate a .NET Framework 4.7.1 e versioni successive, se l'uso di SHA256 è indesiderato, è possibile ripristinare il valore predefinito di SHA1 aggiungendo l'opzione di configurazione seguente alla sezione [Runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'app:

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=true;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=true" />
```

Per le applicazioni destinate a .NET Framework 4.7.1 e versioni precedenti, è possibile scegliere esplicitamente questa modifica aggiungendo la seguente opzione di configurazione alla sezione [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'app:

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=false;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=false" />
```

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.7.1       |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Security.Cryptography.Pkcs.CmsSigner?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.Reference?displayProperty=nameWithType>
