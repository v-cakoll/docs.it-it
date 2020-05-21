---
ms.openlocfilehash: 719f336e1b38597674d6ee8f0c5429dd965054b1
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721195"
---
### <a name="floating-point-formatting-and-parsing-behavior-changed"></a>Modifica del comportamento di analisi e formattazione a virgola mobile

L'analisi a virgola mobile e il comportamento di formattazione (per i <xref:System.Double> <xref:System.Single> tipi e) sono ora conformi a IEEE.

#### <a name="change-description"></a>Descrizione modifica:

In .NET Core 2,2 e versioni precedenti, la formattazione con e e l' <xref:System.Double.ToString%2A?displayProperty=nameWithType> <xref:System.Single.ToString%2A?displayProperty=nameWithType> analisi con <xref:System.Double.Parse%2A?displayProperty=nameWithType> , <xref:System.Double.TryParse%2A?displayProperty=nameWithType> , <xref:System.Single.Parse%2A?displayProperty=nameWithType> e <xref:System.Single.TryParse%2A?displayProperty=nameWithType> non sono conformi a IEEE. Di conseguenza, è impossibile garantire che un valore venga round trip con qualsiasi stringa di formato standard o personalizzata supportata. Per alcuni input, il tentativo di analizzare un valore formattato può avere esito negativo e, per altri, il valore analizzato non è uguale al valore originale.

A partire da .NET Core 3,0, le operazioni di analisi e formattazione sono conformi a IEEE 754. Ciò garantisce che il comportamento dei tipi a virgola mobile in .NET corrisponda a quello di linguaggi conformi a IEEE, ad esempio C#. Per ulteriori informazioni, vedere la pagina relativa ai miglioramenti apportati all' [analisi e alla formattazione a virgola mobile nel post di Blog di .NET Core 3,0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) .

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

La sezione "impatto potenziale sul codice esistente" dei miglioramenti apportati all' [analisi a virgola mobile e alla formattazione nel](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) post di Blog di .net core 3,0 suggerisce le modifiche al codice se si osserva una modifica del comportamento rispetto alle applicazioni .net core 2,2 in genere, ciò comporta l'uso di una stringa di formato standard o personalizzata diversa per applicare il comportamento desiderato. Alcuni risultati potrebbero non avere una soluzione alternativa se in precedenza non erano corretti.

#### <a name="category"></a>Category

Principali librerie .NET

#### <a name="affected-apis"></a>API interessate

- <xref:System.Double.ToString%2A?displayProperty=nameWithType>
- <xref:System.Single.ToString%2A?displayProperty=nameWithType>
- <xref:System.Double.Parse%2A?displayProperty=nameWithType>
- <xref:System.Double.TryParse%2A?displayProperty=nameWithType>
- <xref:System.Single.Parse%2A?displayProperty=nameWithType>
- <xref:System.Single.TryParse%2A?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `Overload:System.Double.ToString`
- `Overload:System.Single.ToString`
- `Overload:System.Double.Parse`
- `Overload:System.Double.TryParse`
- `Overload:System.Single.Parse`
- `Overload:System.Single.TryParse`

-->
