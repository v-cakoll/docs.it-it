---
ms.openlocfilehash: 7d3568fef933758c40e47cefa86c24d31d4119fc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620131"
---
### <a name="httprequestcontentencoding-property-prohibits-utf7"></a>La proprietà HttpRequest.ContentEncoding non consente UTF7

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.5, la codifica UTF-7 non è consentita nel corpo di <xref:System.Web.HttpRequest?displayProperty=fullName>. In alcuni casi i dati per le applicazioni che dipendono dai dati UTF-7 in ingresso non verranno decodificati correttamente.

#### <a name="suggestion"></a>Suggerimento

È consigliabile aggiornare le applicazioni in modo da non usare la codifica UTF-7 in <xref:System.Web.HttpRequest?displayProperty=fullName>. In alternativa, è possibile ripristinare il comportamento legacy usando l'attributo <code>aspnet:AllowUtf7RequestContentEncoding</code> dell'elemento [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md).

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|
