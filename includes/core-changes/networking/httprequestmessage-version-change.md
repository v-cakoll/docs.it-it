---
ms.openlocfilehash: b50a108d2efbfd3da0d690cb02537a12f766b26b
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2019
ms.locfileid: "72237378"
---
### <a name="default-value-of-httprequestmessageversion-changed-to-11"></a>Il valore predefinito di HttpRequestMessage. Version è stato modificato in 1,1 

Il valore predefinito della proprietà <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> è stato modificato da 2,0 a 1,1.

#### <a name="version-introduced"></a>Versione introdotta

.NET Core 3.0

#### <a name="change-description"></a>Descrizione della modifica

In .NET Core da 1,0 a 2,0, il valore predefinito della proprietà <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> è 1,1. A partire da .NET Core 2,1, è stato modificato in 2,1. 

A partire da .NET Core 3,0, il numero di versione predefinito restituito dalla proprietà <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> è ancora una volta 1,1.
 
#### <a name="recommended-action"></a>Azione consigliata

Aggiornare il codice se dipende dalla proprietà <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> che restituisce un valore predefinito di 2,0.

#### <a name="category"></a>Category

Rete

#### <a name="affected-apis"></a>API interessate

- <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName>

<!--
a def
### Affected APIs

- `P:System.Net.Http.HttpRequestMessage.Version`

-- >

