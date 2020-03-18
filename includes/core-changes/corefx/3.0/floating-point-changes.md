---
ms.openlocfilehash: ce4f09908b1025e8e5a0380c9bf035c6b0db479a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74568082"
---
### <a name="floating-point-formatting-and-parsing-behavior-changed"></a>Modifiche al comportamento di formattazione e analisi a virgola mobile

Il comportamento di analisi e formattazione a virgola mobile (da parte dei <xref:System.Double> tipi e) <xref:System.Single> sono ora compatibili con IEEE.

#### <a name="change-description"></a>Descrizione modifica:

In .NET Core 2.2 e <xref:System.Double.ToString%2A?displayProperty=nameWithType> versioni <xref:System.Single.ToString%2A?displayProperty=nameWithType>precedenti la formattazione <xref:System.Single.Parse%2A?displayProperty=nameWithType>con <xref:System.Single.TryParse%2A?displayProperty=nameWithType> e , e l'analisi con <xref:System.Double.Parse%2A?displayProperty=nameWithType>, <xref:System.Double.TryParse%2A?displayProperty=nameWithType>, e non sono compatibili con IEEE. Di conseguenza, è impossibile garantire che un valore verrà eseguito il roundtrip con qualsiasi stringa di formato standard o personalizzata supportata. Per alcuni input, il tentativo di analizzare un valore formattato può avere esito negativo e, per altri, il valore analizzato non è uguale al valore originale.

A partire da .NET Core 3.0, le operazioni di analisi e formattazione sono compatibili con IEEE 754. In questo modo si garantisce che il comportamento dei tipi a virgola mobile in .NET corrisponda a quello dei linguaggi compatibili con IEEE, ad esempio il linguaggio C. Per altre informazioni, vedere i miglioramenti di analisi e formattazione a virgola mobile nel post di blog di .NET Core 3.0.For more information, see the [Floating-point parsing and formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) blog post.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

La sezione "Potenziale impatto sul codice esistente" del post di accanalisi e formattazione a virgola mobile nel post di blog [di .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) suggerisce modifiche al codice se si osserva una modifica del comportamento rispetto alle applicazioni .NET Core 2.2 In genere, ciò comporta l'utilizzo di una stringa di formato standard o personalizzata diversa per applicare il comportamento desiderato. Alcuni risultati potrebbero non avere una soluzione alternativa se in precedenza non erano corretti.

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
