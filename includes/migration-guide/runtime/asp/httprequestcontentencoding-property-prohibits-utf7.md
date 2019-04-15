---
ms.openlocfilehash: 668d047d3247d64cb1400d4a9ea6887795fa0d44
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235426"
---
### <a name="httprequestcontentencoding-property-prohibits-utf7"></a>La proprietà HttpRequest.ContentEncoding non consente UTF7

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.5, la codifica UTF-7 non è consentita nel corpo di <xref:System.Web.HttpRequest?displayProperty=name>. In alcuni casi i dati per le applicazioni che dipendono dai dati UTF-7 in ingresso non verranno decodificati correttamente.|
|Suggerimento|È consigliabile aggiornare le applicazioni in modo da non usare la codifica UTF-7 in <xref:System.Web.HttpRequest?displayProperty=name>. In alternativa, è possibile ripristinare il comportamento legacy usando l'attributo <code>aspnet:AllowUtf7RequestContentEncoding</code> dell'elemento [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md).|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|
