---
ms.openlocfilehash: 5ad9c494fd02059e05cc744aad3b06cfc9399995
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451888"
---
### <a name="default-value-of-httprequestmessageversion-changed-to-11"></a>Il valore predefinito di HttpRequestMessage. Version è stato modificato in 1,1

Il valore predefinito della proprietà <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> è stato modificato da 2,0 a 1,1.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="change-description"></a>Descrizione della modifica

In .NET Core da 1,0 a 2,0, il valore predefinito della proprietà <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> è 1,1. A partire da .NET Core 2,1, è stato modificato in 2,1.

A partire da .NET Core 3,0, il numero di versione predefinito restituito dalla proprietà <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> è ancora una volta 1,1.

#### <a name="recommended-action"></a>Azione consigliata

Aggiornare il codice se dipende dalla proprietà <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> la restituzione di un valore predefinito di 2,0.

#### <a name="category"></a>Category

Rete

#### <a name="affected-apis"></a>API interessate

- <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Net.Http.HttpRequestMessage.Version`

-->
