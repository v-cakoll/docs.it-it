---
ms.openlocfilehash: 3f3f60f9752b9bd36d76387102c202d88b39c3ca
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65670157"
---
| .NET Standard              | [1.0]  | [1.1]  | [1.2] | [1.3] | [1.4] | [1.5]              | [1.6]              | [2.0]               |
|----------------------------|--------|--------|-------|-------|-------|--------------------|--------------------|---------------------|
| .NET Core                  | 1.0    | 1.0    | 1.0   | 1.0   | 1.0   | 1.0                | 1.0                | 2.0                 |
| .NET Framework <sup>1</sup>| 4.5    | 4.5    | 4.5.1 | 4.6   | 4.6.1 | 4.6.1 <sup>2</sup> | 4.6.1 <sup>2</sup> | 4.6.1 <sup>2</sup>  |
| Mono                       | 4.6    | 4.6    | 4.6   | 4.6   | 4.6   | 4.6                | 4.6                | 5.4                 |
| Xamarin.iOS                | 10.0   | 10.0   | 10.0  | 10.0  | 10.0  | 10.0               | 10.0               | 10.14               |
| Xamarin.Mac                | 3.0    | 3.0    | 3.0   | 3.0   | 3.0   | 3.0                | 3.0                | 3.8                 |
| Xamarin.Android            | 7.0    | 7.0    | 7.0   | 7.0   | 7.0   | 7.0                | 7.0                | 8.0                 |
| Piattaforma UWP (Universal Windows Platform) | 10.0   | 10.0   | 10.0  | 10.0  | 10.0  | 10.0.16299         | 10.0.16299         | 10.0.16299          |
| Unity                      | 2018.1 | 2018.1 | 2018.1| 2018.1| 2018.1| 2018.1             |  2018.1            | 2018.1              |

<sup>1 Le versioni elencate per .NET Framework si applicano agli strumenti .NET Core 2.0 SDK e versioni successive. Le versioni precedenti usavano un altro mapping per .NET Standard 1.5 e versioni successive. È possibile [scaricare gli strumenti di .NET Core per Visual Studio 2015](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md) se non è possibile eseguire l'aggiornamento a Visual Studio 2017.</sup>

<sup>2. le versioni elencate di seguito rappresentano le regole che NuGet usa per determinare se una determinata libreria .NET Standard è applicabile. Anche se NuGet considera che .NET Framework 4.6.1 supporta .NET Standard da 1.5 a 2.0, si verificano vari problemi quando si usano librerie .NET Standard compilate per queste versioni da progetti .NET Framework 4.6.1. Per i progetti .NET Framework che devono necessariamente usare queste librerie è consigliabile aggiornare il progetto impostando come destinazione .NET Framework 4.7.2 o versione successiva.</sup>

- Le colonne rappresentano le versioni di .NET Standard. Ogni cella di intestazione è un collegamento a un documento che mostra quali API sono state aggiunte nella specifica versione di .NET Standard.
- Le righe rappresentano le diverse implementazioni di .NET.
- Il numero di versione in ogni cella indica la versione *minima* dell'implementazione necessaria per usare tale specifica versione di .NET Standard come destinazione.
- Per una tabella interattiva, vedere [.NET Standard versions](https://dotnet.microsoft.com/platform/dotnet-standard#versions) (Versioni di .NET Standard).

[1.0]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.0.md
[1.1]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.1.md
[1.2]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.2.md
[1.3]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.3.md
[1.4]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.4.md
[1.5]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.5.md
[1.6]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.6.md
[2.0]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard2.0.md
