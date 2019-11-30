---
ms.openlocfilehash: ff156afb3da4b921517fd841c5de2295265a8d7b
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567743"
---
### <a name="default-value-of-httprequestmessageversion-changed-to-11"></a>Il valore predefinito di HttpRequestMessage. Version è stato modificato in 1,1

Il valore predefinito della proprietà <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> è stato modificato da 2,0 a 1,1.

#### <a name="version-introduced"></a>Versione introdotta

.NET Core 3.0

#### <a name="change-description"></a>Descrizione della modifica

In .NET Core da 1,0 a 2,0, il valore predefinito della proprietà <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> è 1,1. A partire da .NET Core 2,1, è stato modificato in 2,1.

A partire da .NET Core 3,0, il numero di versione predefinito restituito dalla proprietà <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> è ancora una volta 1,1.

#### <a name="recommended-action"></a>Azione consigliata

Aggiornare il codice se dipende dalla proprietà <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> la restituzione di un valore predefinito di 2,0.

#### <a name="category"></a>Category

Funzionalità di rete di

#### <a name="affected-apis"></a>API interessate

- <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName>

<!--
a def
### Affected APIs

- `P:System.Net.Http.HttpRequestMessage.Version`

-- >

