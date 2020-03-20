---
ms.openlocfilehash: 204fe32ec8b7fbaab89e37d7e761469212091728
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "68237934"
---
### <a name="contractinvariant-or-contractrequirestexception-do-not-consider-stringisnullorempty-to-be-pure"></a>Contract.Invariant o Contract.Requires\<TException> non considera String.IsNullOrEmpty come puro

|   |   |
|---|---|
|Dettagli|Per le app destinate a .NET Framework 4.6.1, se il contratto invariante <xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=nameWithType> per o il contratto di precondizione per <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType)> chiama il <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType> metodo, il rewriter genera l'avviso del compilatore CC1036: &quot;chiamata rilevata al metodo 'System.String.IsNullOrWhteSpace(System.String)' senza [Pure] nel metodo. &quot; Si tratta di un avviso del compilatore anziché un errore del compilatore.|
|Suggerimento|Questo comportamento è stato affrontato nel [problema GitHub n. 339](https://github.com/Microsoft/CodeContracts/issues/339). Per eliminare questo avviso, è possibile scaricare e compilare una versione aggiornata del codice sorgente per lo strumento Contratti di codice da [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md). Le informazioni per il download sono disponibili in fondo alla pagina.|
|Scope|Minorenne|
|Versione|4.6.1|
|Type|Runtime|
|API interessate|<ul><li><xref:System.Diagnostics.Contracts.Contract.Invariant(System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Contracts.Contract.Requires(System.Boolean)?displayProperty=nameWithType></li></ul>|
