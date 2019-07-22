---
ms.openlocfilehash: 204fe32ec8b7fbaab89e37d7e761469212091728
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2019
ms.locfileid: "68237934"
---
### <a name="contractinvariant-or-contractrequirestexception-do-not-consider-stringisnullorempty-to-be-pure"></a>Contract.Invariant o Contract.Requires\<TException> non considera String.IsNullOrEmpty come puro

|   |   |
|---|---|
|Dettagli|Per le app destinate a .NET Framework 4.6.1, se il contratto invariante per <xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=nameWithType> o il contratto di precondizione per <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType)> chiama il metodo <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType>, il rewriter emette l'avviso del compilatore CC1036: &quot;Detected call to method 'System.String.IsNullOrWhiteSpace(System.String)' without [Pure] in method.&quot; (Rilevata chiamata al metodo 'System.String.IsNullOrWhiteSpace(System.String)' senza [Pure] nel metodo). Si tratta di un avviso del compilatore, non di un errore del compilatore.|
|Suggerimento|Questo comportamento è stato affrontato nel [problema GitHub n. 339](https://github.com/Microsoft/CodeContracts/issues/339). Per eliminare questo avviso, è possibile scaricare e compilare una versione aggiornata del codice sorgente per lo strumento Contratti di codice da [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md). Le informazioni per il download sono disponibili in fondo alla pagina.|
|Ambito|Secondario|
|Versione|4.6.1|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Diagnostics.Contracts.Contract.Invariant(System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Contracts.Contract.Requires(System.Boolean)?displayProperty=nameWithType></li></ul>|
