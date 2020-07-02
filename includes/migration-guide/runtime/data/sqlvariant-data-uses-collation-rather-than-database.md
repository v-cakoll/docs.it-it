---
ms.openlocfilehash: d606fbc4048421bc572cfe3db2e06bbcd4529e25
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620291"
---
### <a name="sql_variant-data-uses-sql_variant-collation-rather-than-database-collation"></a>I dati sql_variant usano regole di confronto sql_variant invece delle regole di confronto del database

#### <a name="details"></a>Dettagli

I dati di <code>sql_variant</code> usano regole di confronto di <code>sql_variant</code> anziché regole di confronto di database.

#### <a name="suggestion"></a>Suggerimento

Questa modifica risolve il possibile danneggiamento dei dati se le regole di confronto del database differiscono da quelle di <code>sql_variant</code>. Le applicazioni basate su dati errati possono generare un errore.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Modalità trasparente|
|Version|4.5|
|Type|Runtime|
