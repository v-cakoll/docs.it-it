---
ms.openlocfilehash: 5ad9c494fd02059e05cc744aad3b06cfc9399995
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77451888"
---
### <a name="default-value-of-httprequestmessageversion-changed-to-11"></a>Valore predefinito di HttpRequestMessage.Version modificato in 1.1

Il valore predefinito <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> della proprietà è stato modificato da 2.0 a 1.1.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="change-description"></a>Descrizione modifica:

In .NET Core da 1.0 a 2.0, il valore predefinito della <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> proprietà è 1.1. A partire da .NET Core 2.1, è stato modificato in 2.1.Starting with .NET Core 2.1, it was changed to 2.1.

A partire da .NET Core 3.0, il <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> numero di versione predefinito restituito dalla proprietà è ancora una volta 1.1.Starting with .NET Core 3.0, the default version number returned by the property is once 1.1.

#### <a name="recommended-action"></a>Azione consigliata

Aggiornare il codice se <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> dipende dalla proprietà che restituisce un valore predefinito di 2.0.Update your code if it depends on the property returning a default value of 2.0.

#### <a name="category"></a>Category

Rete

#### <a name="affected-apis"></a>API interessate

- <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Net.Http.HttpRequestMessage.Version`

-->
