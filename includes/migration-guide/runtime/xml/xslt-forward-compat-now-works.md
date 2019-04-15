---
ms.openlocfilehash: 2dd97fcce13ed1ac7baf4cd02f5881d31d7a9c4b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235488"
---
### <a name="xslt-forward-compat-now-works"></a>La compatibilità con le versioni successive di XSLT ora funziona

|   |   |
|---|---|
|Dettagli|In .NET Framework 4 la compatibilità con le versioni successive di XSLT 1.0 presenta i seguenti problemi:<ul><li>Il caricamento di un foglio di stile ha avuto esito negativo se la versione è stata impostata su 2.0 e il parser ha incontrato un costrutto XSLT 1.0 sconosciuto.</li><li>Il costrutto <code>xsl:sort</code> non è riuscito a ordinare i dati se la versione del foglio di stile era impostata su 1.1.</li></ul>In .NET Framework 4.5 questi problemi sono stati corretti e la modalità di compatibilità con le versioni successive di XSLT 1.0 funziona correttamente.|
|Suggerimento|La maggior parte delle app non dovrebbe essere interessata, tuttavia i dati verranno ordinati in modo diverso in alcuni casi ora che viene rispettato il costrutto xsl:sort. Se si usa <code>xsl:sort</code> nei fogli di stile 1.1, verificare che le app non dipendano dall'ordine dei dati non ordinato. Se le app si basano sul comportamento di ordinamento della versione 4.0, rimuovere <code>xsl:sort</code> dal foglio di stile.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Xml.Xsl.XslCompiledTransform?displayProperty=nameWithType></li></ul>|
