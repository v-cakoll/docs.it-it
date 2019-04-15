---
ms.openlocfilehash: 1d2d6133683360b97569e49402e7c8c4d182b65d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235501"
---
### <a name="objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a>ObjectContext.Translate e ObjectContext.ExecuteStoreQuery ora supportano il tipo enum

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.0 il parametro generico <code>T</code> dei metodi <code>ObjectContext.Translate</code> e <code>ObjectContext.ExecuteStoreQuery</code> non può essere un tipo enum. Questo scenario è ora supportato.|
|Suggerimento|Se si chiama Translate o ExecuteStoreQuery su un tipo enum in .NET Framework 4.0, viene restituito '0'. Se tale comportamento è quello desiderabile, le chiamate devono essere sostituite con una costante 0 (o l'enum equivalente).|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader,System.String,System.Data.Objects.MergeOption)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.String,System.Data.Objects.MergeOption,System.Object[])?displayProperty=nameWithType></li></ul>|
