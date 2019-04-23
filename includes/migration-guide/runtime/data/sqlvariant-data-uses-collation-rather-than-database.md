---
ms.openlocfilehash: e7a5a95a5d13f3396d396ad0d74a19a0efa3a967
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235536"
---
### <a name="sqlvariant-data-uses-sqlvariant-collation-rather-than-database-collation"></a>I dati sql_variant usano regole di confronto sql_variant invece delle regole di confronto del database

|   |   |
|---|---|
|Dettagli|<code>sql_variant</code> I dati di sql_variant usano regole di confronto di <code>sql_variant</code> anziché regole di confronto di database.|
|Suggerimento|Questa modifica risolve il possibile danneggiamento dei dati se le regole di confronto del database differiscono da quelle di <code>sql_variant</code>. Le applicazioni basate su dati errati possono generare un errore.|
|Ambito|Trasparente|
|Versione|4.5|
|Tipo|Runtime|
