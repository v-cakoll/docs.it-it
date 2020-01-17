---
ms.openlocfilehash: 9aff20e35469f9e786f0f790fda4ffaa04e76e64
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116432"
---
### <a name="default-value-of-httprequestmessageversion-changed-to-11"></a>Il valore predefinito di HttpRequestMessage. Version è stato modificato in 1,1

Il valore predefinito della proprietà <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> è stato modificato da 2,0 a 1,1.

#### <a name="version-introduced"></a>Versione introdotta

.NET Core 3.0

#### <a name="change-description"></a>Descrizione delle modifiche

In .NET Core da 1,0 a 2,0, il valore predefinito della proprietà <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> è 1,1. A partire da .NET Core 2,1, è stato modificato in 2,1.

A partire da .NET Core 3,0, il numero di versione predefinito restituito dalla proprietà <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> è ancora una volta 1,1.

#### <a name="recommended-action"></a>Azione consigliata

Aggiornare il codice se dipende dalla proprietà <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> la restituzione di un valore predefinito di 2,0.

#### <a name="category"></a>Categoria

Funzionalità di rete di

#### <a name="affected-apis"></a>API interessate

- <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName>

<!--
a def
### Affected APIs

- `P:System.Net.Http.HttpRequestMessage.Version`

-->
