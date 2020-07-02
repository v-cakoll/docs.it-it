---
ms.openlocfilehash: 29c66edfeb1690199aac39b9c3076d161b2075d4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621343"
---
### <a name="contractinvariant-or-contractrequirestexception-do-not-consider-stringisnullorempty-to-be-pure"></a>Contract.Invariant o Contract.Requires\<TException> non considera pure IsNullOrEmpty

#### <a name="details"></a>Dettagli

Per le app destinate a .NET Framework 4.6.1, se il contratto invariante per <xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=nameWithType> o il contratto di precondizione per <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType)> chiama il <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType> metodo, il rewriter genera l'avviso del compilatore CC1036: &quot; chiamata rilevata al metodo ' System. String. IsNullOrWhteSpace (System. String)' senza [pure] nel metodo. &quot; Si tratta di un avviso del compilatore invece di un errore del compilatore.

#### <a name="suggestion"></a>Suggerimento

Questo comportamento è stato affrontato nel [problema GitHub n. 339](https://github.com/Microsoft/CodeContracts/issues/339). Per eliminare questo avviso, è possibile scaricare e compilare una versione aggiornata del codice sorgente per lo strumento Contratti di codice da [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md). Le informazioni per il download sono disponibili in fondo alla pagina.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.6.1|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Diagnostics.Contracts.Contract.Invariant(System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Contracts.Contract.Requires(System.Boolean)?displayProperty=nameWithType></li></ul>|
