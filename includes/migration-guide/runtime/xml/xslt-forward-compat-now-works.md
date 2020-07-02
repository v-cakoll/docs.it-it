---
ms.openlocfilehash: e3b9711ac66901d69838de4c9f309d086b06fd4d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620518"
---
### <a name="xslt-forward-compat-now-works"></a>La compatibilità con le versioni successive di XSLT ora funziona

#### <a name="details"></a>Dettagli

In .NET Framework 4 la compatibilità con le versioni successive di XSLT 1.0 presenta i seguenti problemi:<ul><li>Il caricamento di un foglio di stile ha avuto esito negativo se la versione è stata impostata su 2.0 e il parser ha incontrato un costrutto XSLT 1.0 sconosciuto.</li><li>Il costrutto <code>xsl:sort</code> non è riuscito a ordinare i dati se la versione del foglio di stile era impostata su 1.1.</li></ul>In .NET Framework 4.5 questi problemi sono stati corretti e la modalità di compatibilità con le versioni successive di XSLT 1.0 funziona correttamente.

#### <a name="suggestion"></a>Suggerimento

La maggior parte delle app non dovrebbe essere interessata, tuttavia i dati verranno ordinati in modo diverso in alcuni casi ora che viene rispettato il costrutto xsl:sort. Se si usa <code>xsl:sort</code> nei fogli di stile 1.1, verificare che le app non dipendano dall'ordine dei dati non ordinato. Se le app si basano sul comportamento di ordinamento della versione 4.0, rimuovere <code>xsl:sort</code> dal foglio di stile.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Xml.Xsl.XslCompiledTransform?displayProperty=nameWithType></li></ul>|
