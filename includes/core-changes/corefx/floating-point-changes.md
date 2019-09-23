---
ms.openlocfilehash: ce4f09908b1025e8e5a0380c9bf035c6b0db479a
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182015"
---
### <a name="floating-point-formatting-and-parsing-behavior-changed"></a>Modifica del comportamento di analisi e formattazione a virgola mobile

L'analisi a virgola mobile e il comportamento di <xref:System.Double> formattazione <xref:System.Single> (per i tipi e) sono ora conformi a IEEE.

#### <a name="change-description"></a>Descrizione della modifica

In .NET Core 2,2 e versioni precedenti, la formattazione <xref:System.Double.ToString%2A?displayProperty=nameWithType> con <xref:System.Single.ToString%2A?displayProperty=nameWithType>e e l'analisi con <xref:System.Double.Parse%2A?displayProperty=nameWithType>, <xref:System.Double.TryParse%2A?displayProperty=nameWithType>, <xref:System.Single.Parse%2A?displayProperty=nameWithType>e <xref:System.Single.TryParse%2A?displayProperty=nameWithType> non sono conformi a IEEE. Di conseguenza, è impossibile garantire che un valore venga round trip con qualsiasi stringa di formato standard o personalizzata supportata. Per alcuni input, il tentativo di analizzare un valore formattato può avere esito negativo e, per altri, il valore analizzato non è uguale al valore originale.

A partire da .NET Core 3,0, le operazioni di analisi e formattazione sono conformi a IEEE 754. Ciò garantisce che il comportamento dei tipi a virgola mobile in .NET corrisponda a quello di linguaggi conformi C#a IEEE, ad esempio. Per ulteriori informazioni, vedere la pagina relativa ai miglioramenti apportati all' [analisi e alla formattazione a virgola mobile nel post di Blog di .NET Core 3,0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) .

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

La sezione "impatto potenziale sul codice esistente" dei miglioramenti apportati all' [analisi e alla formattazione a virgola mobile nel](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) post di Blog di .net core 3,0 suggerisce le modifiche al codice se si osserva una modifica del comportamento rispetto alle applicazioni .net core 2,2 in genere. Ciò comporta l'uso di una stringa di formato standard o personalizzata diversa per applicare il comportamento desiderato. Alcuni risultati potrebbero non avere una soluzione alternativa se in precedenza non erano corretti.

#### <a name="category"></a>Category

CoreFx

#### <a name="affected-apis"></a>API interessate

- <xref:System.Double.ToString%2A?displayProperty=nameWithType>
- <xref:System.Single.ToString%2A?displayProperty=nameWithType>
- <xref:System.Double.Parse%2A?displayProperty=nameWithType>
- <xref:System.Double.TryParse%2A?displayProperty=nameWithType>
- <xref:System.Single.Parse%2A?displayProperty=nameWithType>
- <xref:System.Single.TryParse%2A?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `Overload:System.Double.ToString`
- `Overload:System.Single.ToString`
- `Overload:System.Double.Parse`
- `Overload:System.Double.TryParse`
- `Overload:System.Single.Parse`
- `Overload:System.Single.TryParse`

-->
