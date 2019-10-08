---
ms.openlocfilehash: 78d2ec6fb505573ad36d55a9ca0a20452b7fa244
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002880"
---
### <a name="default-value-of-httprequestmessageversion-changed-to-11"></a>Il valore predefinito di HttpRequestMessage. Version è stato modificato in 1,1 

Il valore predefinito della proprietà <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> è stato modificato da 2,0 a 1,1.

#### <a name="version-introduced"></a>Versione introdotta

.NET Core 3.0

#### <a name="details"></a>Dettagli

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

