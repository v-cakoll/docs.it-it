---
ms.openlocfilehash: b3cc04d5675ea63a0a6b967e293da8a1bd79830d
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595682"
---
### <a name="uribuilder-properties-no-longer-prepend-leading-characters"></a>Le Proprietà UriBuilder non precedono più caratteri iniziali

<xref:System.UriBuilder.Fragment?displayProperty=nameWithType>non antepone più un carattere `#` di primo <xref:System.UriBuilder.Query?displayProperty=nameWithType> livello e non antepone più `?` un carattere di primo livello quando ne è già presente uno.

#### <a name="change-description"></a>Descrizione modifica:

In .NET Framework, le <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> proprietà <xref:System.UriBuilder.Query?displayProperty=nameWithType> e antepono `#` sempre `?` un carattere o rispettivamente al valore archiviato. Questo comportamento può comportare `#` la `?` presenza di più caratteri o nel valore archiviato se la stringa contiene già uno di questi caratteri iniziali. Ad esempio, il valore di <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> potrebbe diventare `##main`.

A partire da .NET Core 1,0, queste proprietà non antepono più i `#` caratteri o `?` al valore archiviato se ne è già presente uno all'inizio della stringa.

#### <a name="version-introduced"></a>Versione introdotta

1.0

#### <a name="recommended-action"></a>Azione consigliata

Non è più necessario rimuovere in modo esplicito uno di questi caratteri iniziali durante l'impostazione dei valori delle proprietà. Questa operazione è particolarmente utile quando si aggiungono valori, perché non è più necessario rimuovere l'oggetto principale `#` o `?` ogni volta che si aggiunge.

Il frammento di codice seguente, ad esempio, Mostra la differenza di comportamento tra .NET Framework e .NET Core.

```csharp
var builder = new UriBuilder();
builder.Query = "one=1";
builder.Query += "&two=2";
builder.Query += "&three=3";
builder.Query += "&four=4";

Console.WriteLine(builder.Query);
```

- In .NET Framework, l'output è `????one=1&two=2&three=3&four=4`.
- In .NET Core, l'output è `?one=1&two=2&three=3&four=4`.

#### <a name="category"></a>Category

Principali librerie .NET

#### <a name="affected-apis"></a>API interessate

- <xref:System.UriBuilder.Fragment?displayProperty=fullName>
- <xref:System.UriBuilder.Query?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.UriBuilder.Fragment`
- `T:System.UriBuilder.Query`

-->
