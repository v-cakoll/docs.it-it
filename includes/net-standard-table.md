---
ms.openlocfilehash: 9e95db8a1530fabd30b5344c87728b9210c0ad69
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802837"
---
| .NET Standard              | [1.0]  | [1.1]  | [1.2] | [1.3] | [1.4] | [1.5]              | [1.6]              | [2.0]               | [2.1] |
|----------------------------|--------|--------|-------|-------|-------|--------------------|--------------------|---------------------|---------------------
| .NET Core                  | 1.0    | 1.0    | 1.0   | 1.0   | 1.0   | 1.0                | 1.0                | 2.0                 | 3.0 |
| .NET Framework <sup>1</sup>| 4.5    | 4.5    | 4.5.1 | 4.6   | 4.6.1 | 4.6.1 <sup>2</sup> | 4.6.1 <sup>2</sup> | 4.6.1 <sup>2</sup>  | N/A<sup>3</sup> |
| Mono                       | 4.6    | 4.6    | 4.6   | 4.6   | 4.6   | 4.6                | 4.6                | 5.4                 | 6.4 |
| Xamarin.iOS                | 10.0   | 10.0   | 10.0  | 10.0  | 10.0  | 10.0               | 10.0               | 10.14               | 12.16 |
| Xamarin.Mac                | 3.0    | 3.0    | 3.0   | 3.0   | 3.0   | 3.0                | 3.0                | 3.8                 | 5.16 |
| Xamarin.Android            | 7.0    | 7.0    | 7.0   | 7.0   | 7.0   | 7.0                | 7.0                | 8.0                 | 10.0 |
| Piattaforma UWP (Universal Windows Platform) | 10.0   | 10.0   | 10.0  | 10.0  | 10.0  | 10.0.16299         | 10.0.16299         | 10.0.16299          | TBD |
| Unity                      | 2018.1 | 2018.1 | 2018.1| 2018.1| 2018.1| 2018.1             |  2018.1            | 2018.1              | TBD |

<sup>1 le versioni elencate per .NET Framework si applicano a .NET Core 2,0 SDK e versioni successive degli strumenti. Le versioni precedenti usavano un mapping diverso per .NET Standard 1,5 e versioni successive. È possibile [scaricare gli strumenti per gli strumenti di .NET Core per Visual studio 2015](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md) se non è possibile eseguire l'aggiornamento a visual studio 2017 o versione successiva.</sup>

<sup>2 le versioni elencate di seguito rappresentano le regole utilizzate da NuGet per determinare se una determinata libreria di .NET Standard è applicabile. Sebbene NuGet consideri .NET Framework 4.6.1 come supporto .NET Standard da 1,5 a 2,0, esistono diversi problemi con l'utilizzo di librerie .NET Standard compilate per tali versioni da .NET Framework progetti 4.6.1. Per i progetti .NET Framework che devono usare tali librerie, è consigliabile aggiornare il progetto per la destinazione .NET Framework 4.7.2 o versione successiva.</sup>

<sup>3 .NET Framework non supporterà .NET Standard 2,1 o versioni successive. Per ulteriori informazioni, vedere l' [annuncio di .NET Standard 2,1](https://devblogs.microsoft.com/dotnet/announcing-net-standard-2-1/).</sup>

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
[2.1]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard2.1.md
