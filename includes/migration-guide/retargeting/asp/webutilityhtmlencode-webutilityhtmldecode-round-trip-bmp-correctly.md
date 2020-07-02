---
ms.openlocfilehash: acb5b467fc8f0692d8fa1b3b8263fd27308cc124
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617165"
---
### <a name="webutilityhtmlencode-and-webutilityhtmldecode-round-trip-bmp-correctly"></a>Round trip corretto di WebUtility.HtmlEncode e WebUtility.HtmlDecode per BMP

#### <a name="details"></a>Dettagli

Per le applicazioni destinate a .NET Framework 4.5, i caratteri al di fuori del piano di base multilinguistico (BMP, Basic Multilingual Plane) eseguono correttamente il round trip quando vengono passati ai metodi <xref:System.Net.WebUtility.HtmlDecode(System.String)>.

#### <a name="suggestion"></a>Suggerimento

Questa modifica non dovrebbe avere alcun effetto sulle applicazioni correnti, ma per ripristinare il comportamento originale, impostare l' `targetFramework` attributo dell' `<httpRuntime>` elemento su una stringa diversa da "4,5". È inoltre possibile impostare gli attributi `unicodeEncodingConformance` e `unicodeDecodingConformance` dell'elemento di configurazione `<webUtility>` per controllare questo comportamento indipendentemente dalla versione di destinazione di .NET Framework.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.5         |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Net.WebUtility.HtmlEncode(System.String)?displayProperty=nameWithType>
- <xref:System.Net.WebUtility.HtmlEncode(System.String,System.IO.TextWriter)?displayProperty=nameWithType>
