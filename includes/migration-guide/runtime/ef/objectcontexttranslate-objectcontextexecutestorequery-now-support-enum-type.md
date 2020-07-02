---
ms.openlocfilehash: 6af8e97423c04abca25feb8d77ea9ab6e198a4f0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620331"
---
### <a name="objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a>ObjectContext.Translate e ObjectContext.ExecuteStoreQuery ora supportano il tipo enum

#### <a name="details"></a>Dettagli

In .NET Framework 4.0 il parametro generico <code>T</code> dei metodi <code>ObjectContext.Translate</code> e <code>ObjectContext.ExecuteStoreQuery</code> non può essere un tipo enum. Questo scenario è ora supportato.

#### <a name="suggestion"></a>Suggerimento

Se si chiama Translate o ExecuteStoreQuery su un tipo enum in .NET Framework 4.0, viene restituito '0'. Se tale comportamento è quello desiderabile, le chiamate devono essere sostituite con una costante 0 (o l'enum equivalente).

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime|

#### <a name="affected-apis"></a>API interessate

-<xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader,System.String,System.Data.Objects.MergeOption)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.String,System.Data.Objects.MergeOption,System.Object[])?displayProperty=nameWithType></li></ul>|
