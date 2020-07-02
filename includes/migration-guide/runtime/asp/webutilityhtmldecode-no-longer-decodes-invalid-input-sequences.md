---
ms.openlocfilehash: 0b7d6d9543035ab0a8fdda675ae71572ace12a1f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620164"
---
### <a name="webutilityhtmldecode-no-longer-decodes-invalid-input-sequences"></a>WebUtility.HtmlDecode non decodifica più sequenze di input non valide

#### <a name="details"></a>Dettagli

Per impostazione predefinita, i metodi di decodifica non decodificano più una sequenza di input non valido in una stringa UTF-16 non valida. Al contrario, viene restituito l'input originale.

#### <a name="suggestion"></a>Suggerimento

La modifica dell'output del decodificatore è importante solo se si archiviano dati binari anziché dati UTF-16 nelle stringhe. Per controllare questo comportamento in modo esplicito, impostare l'attributo <code>aspnet:AllowRelaxedUnicodeDecoding</code> dell'elemento [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/index.md) su <code>true</code> per abilitare il comportamento legacy o su <code>false</code> per abilitare il comportamento corrente.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Net.WebUtility.HtmlDecode(System.String)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.HtmlDecode(System.String,System.IO.TextWriter)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.UrlDecode(System.String)?displayProperty=nameWithType></li></ul>|
