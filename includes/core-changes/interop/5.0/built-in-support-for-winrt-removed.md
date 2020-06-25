---
ms.openlocfilehash: d21b2e092d460fdfc367d0f490228ed44ad5c6cc
ms.sourcegitcommit: 63bb83322814f5e5e5c5b69939b14a3139a6ca7e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2020
ms.locfileid: "85365649"
---
### <a name="built-in-support-for-winrt-is-removed-from-net"></a>Il supporto predefinito per WinRT è stato rimosso da .NET

Il supporto incorporato per l'utilizzo delle API di [Windows Runtime (WinRT)](/uwp/winrt-cref/winrt-type-system) in .NET è stato rimosso.

#### <a name="version-introduced"></a>Versione introdotta

5,0 Preview 6

#### <a name="change-description"></a>Descrizione modifica:

In precedenza, CoreCLR poteva usare [i file di metadati Windows (WinMD)](/uwp/winrt-cref/winmd-files) in Active e utilizzare i tipi WinRT. A partire da .NET 5,0, CoreCLR non può più utilizzare direttamente i file WinMD.

Se si tenta di fare riferimento a un assembly non supportato, si otterrà <xref:System.IO.FileNotFoundException> . Se si attiva una classe WinRT, si otterrà <xref:System.PlatformNotSupportedException> .

Questa modifica di rilievo è stata apportata per i motivi seguenti:

- WinRT può quindi essere sviluppato e migliorato separatamente dal runtime .NET.
- Per la simmetria con i sistemi di interoperabilità forniti per altri sistemi operativi, ad esempio iOS e Android.
- Per sfruttare le altre funzionalità di .NET, ad esempio le funzionalità di C#, IL collegamento Intermediate Language (IL) e la compilazione AOT (Ahead of Time).
- Per semplificare la codebase del runtime .NET.

#### <a name="recommended-action"></a>Azione consigliata

- Rimuovere i riferimenti al [pacchetto Microsoft. Windows. Sdk. Contracts](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts) e sostituirli con i riferimenti al [pacchetto Microsoft.Windows.Sdk.NET](https://www.nuget.org/packages/microsoft.windows.sdk.net).

- Usare la catena di strumenti [C#/WinRT](/windows/uwp/csharp-winrt/) per generare o personalizzare i tipi e le API WinRT in .NET 5,0 e versioni successive.

#### <a name="category"></a>Category

Interoperabilità

#### <a name="affected-apis"></a>API interessate

- <xref:System.IO.WindowsRuntimeStorageExtensions?displayProperty=fullName>
- <xref:System.IO.WindowsRuntimeStreamExtensions?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.WindowsRuntime?displayProperty=fullName>
- <xref:System.WindowsRuntimeSystemExtensions?displayProperty=fullName>
- <xref:Windows.Foundation.Point?displayProperty=fullName>
- <xref:Windows.Foundation.Size?displayProperty=fullName>
- <xref:Windows.UI.Color?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.IO.WindowsRuntimeStorageExtensions`
- `T: System.IO.WindowsRuntimeStreamExtensions`
- `N:System.Runtime.InteropServices.WindowsRuntime`
- `T:System.WindowsRuntimeSystemExtensions`
- `T:Windows.Foundation.Point`
- `T:Windows.Foundation.Size`
- `T:Windows.UI.Color`

-->
