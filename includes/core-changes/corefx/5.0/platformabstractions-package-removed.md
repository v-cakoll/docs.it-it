---
ms.openlocfilehash: d85fb8df7afdc5f4c3faecebcd24d11677798bc9
ms.sourcegitcommit: 63bb83322814f5e5e5c5b69939b14a3139a6ca7e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2020
ms.locfileid: "85365615"
---
### <a name="microsoftdotnetplatformabstractions-package-removed"></a>Pacchetto Microsoft. DotNet. PlatformAbstractions rimosso

Non verranno generate nuove versioni del [pacchetto NuGet Microsoft. dotnet. PlatformAbstractions](https://www.nuget.org/packages/Microsoft.DotNet.PlatformAbstractions/) .

#### <a name="change-description"></a>Descrizione modifica:

In precedenza, le nuove versioni della <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> libreria venivano prodotte insieme alle nuove versioni di .NET Core. In futuro, non verrà aggiunta alcuna nuova funzionalità alla libreria e non verranno rilasciate nuove versioni principali. Tuttavia, le versioni esistenti della libreria continueranno a funzionare e verranno gestite.

La <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> libreria si sovrappone alle API già stabilite in System. \* namespaces. Alcune API, inoltre, non sono state <xref:Microsoft.DotNet.PlatformAbstractions> progettate con lo stesso livello di controllo e supporto a lungo termine come il resto del sistema. \* API. Ad esempio, <xref:Microsoft.DotNet.PlatformAbstractions> Usa l' `Platform` enumerazione per descrivere la piattaforma del sistema operativo corrente. Questo progetto di enumerazione è stato rifiutato in modo esplicito al momento della progettazione dell' <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType> API, per consentire nuove piattaforme e flessibilità futura.

Gli scenari abilitati dalla <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> libreria sono ora possibili senza di essa. Le versioni esistenti continueranno a funzionare anche in .NET 5,0 e versioni successive e verranno gestite insieme alle versioni precedenti di .NET Core. Tuttavia, le nuove funzionalità non verranno aggiunte alla libreria. Verranno invece aggiunte nuove funzionalità ad altre librerie e API.

#### <a name="version-introduced"></a>Versione introdotta

5,0 Preview 6

#### <a name="recommended-action"></a>Azione consigliata

- È possibile continuare a usare le versioni precedenti della libreria se soddisfano i requisiti.

- Se le versioni precedenti non soddisfano i requisiti, sostituire gli utilizzi delle `PlatformAbstractions` API con le sostituzioni consigliate.

  | `PlatformAbstractions`API | Sostituzione consigliata |
  |-|-|
  | `ApplicationEnvironment.ApplicationBasePath` | <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> |
  | <xref:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner> | <xref:System.HashCode?displayProperty=nameWithType> |
  | `RuntimeEnvironment.GetRuntimeIdentifier()` | <xref:System.Runtime.InteropServices.RuntimeInformation.RuntimeIdentifier?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystemPlatform` | <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType> |
  | `RuntimeEnvironment.RuntimeArchitecture` | <xref:System.Runtime.InteropServices.RuntimeInformation.ProcessArchitecture?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystem` | <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystemVersion` | <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> e <xref:System.Environment.OSVersion?displayProperty=nameWithType> |

  > [!NOTE]
  > La maggior parte dei casi d'uso per `RuntimeEnvironment.OperatingSystem` e `RuntimeEnvironment.OperatingSystemVersion` è a scopo di visualizzazione, ad esempio, la visualizzazione di un utente, la registrazione e la telemetria. Non è consigliabile prendere decisioni in fase di esecuzione in base a una versione del sistema operativo. <xref:System.Environment.OSVersion?displayProperty=nameWithType>restituisce ora la versione corretta per i sistemi operativi Windows e macOS. Tuttavia, per la maggior parte delle distribuzioni UNIX, ciò che è considerato la "versione del sistema operativo" non è altrettanto semplice. Ad esempio, potrebbe essere la versione del kernel Linux o la versione della distribuzione. Per la maggior parte delle piattaforme UNIX, <xref:System.Environment.OSVersion?displayProperty=nameWithType> e <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> restituiscono la versione restituita da `uname` . Per ottenere il nome della distro Linux e le informazioni sulla versione, l'approccio consigliato consiste nel leggere il file */etc/OS-release* .

#### <a name="category"></a>Category

Principali librerie .NET

#### <a name="affected-apis"></a>API interessate

- `Microsoft.DotNet.PlatformAbstractions.ApplicationEnvironment.ApplicationBasePath`
- <xref:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner?displayProperty=fullName>
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.GetRuntimeIdentifier()`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystem`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemPlatform`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemVersion`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.RuntimeArchitecture`

<!--

#### Affected APIs

- `P:Microsoft.DotNet.PlatformAbstractions.ApplicationEnvironment.ApplicationBasePath`
- `T:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner`
- `M:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.GetRuntimeIdentifier`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystem`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemPlatform`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemVersion`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.RuntimeArchitecture`

-->
