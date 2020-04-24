---
ms.openlocfilehash: 394f2daebad7b6af94bee4d7876796e87fe8ab19
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135626"
---
### <a name="handling-corrupted-state-exceptions-is-not-supported"></a>La gestione delle eccezioni di stato danneggiato non è supportata

La gestione delle eccezioni di stato del processo danneggiato in .NET Core non è supportata.

#### <a name="change-description"></a>Descrizione modifica:

In precedenza, le eccezioni di stato del processo danneggiato potevano essere rilevate e gestite da gestori di eccezioni del codice gestito, ad esempio tramite un'istruzione [try-catch](../../../../docs/csharp/language-reference/keywords/try-catch.md) in C#.

A partire da .NET Core 1,0, le eccezioni di stato del processo danneggiate non possono essere gestite dal codice gestito. Il Common Language Runtime non recapita eccezioni di stato del processo danneggiate al codice gestito.

#### <a name="version-introduced"></a>Versione introdotta

1.0

#### <a name="recommended-action"></a>Azione consigliata

Evitare la necessità di gestire le eccezioni di stato del processo danneggiato risolvendo invece le situazioni che li portano. Se è assolutamente necessario gestire le eccezioni di stato del processo danneggiato, scrivere il gestore di eccezioni nel codice C o C++.

#### <a name="category"></a>Category

Principali librerie .NET

#### <a name="affected-apis"></a>API interessate

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=fullName>
- [legacyCorruptedStateExceptionsPolicy (elemento)](~/docs/framework/configure-apps/file-schema/runtime/legacycorruptedstateexceptionspolicy-element.md)

<!--

#### Affected APIs

- `T:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute`

-->
