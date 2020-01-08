---
ms.openlocfilehash: 7c0930f6606aa96d2863dc740aef8e9cab724b37
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344861"
---
### <a name="change-in-default-value-of-useshellexecute"></a>Modificare il valore predefinito di UseShellExecute

<xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> ha un valore predefinito di `false` in .NET Core. In .NET Framework, il valore predefinito è `true`.

#### <a name="change-description"></a>Descrizione delle modifiche

<xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> consente di avviare direttamente un'applicazione, ad esempio con codice come `Process.Start("mspaint.exe")` che avvia Paint. Consente inoltre di avviare indirettamente un'applicazione associata se <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> è impostata su `true`. In .NET Framework, il valore predefinito per <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> è `true`, vale a dire che il codice, ad esempio `Process.Start("mytextfile.txt")` avvierà il blocco note, se i file con *estensione txt* sono stati associati con tale editor. Per impedire l'avvio indiretto di un'app in .NET Framework, è necessario impostare in modo esplicito <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> su `false`. In .NET Core, il valore predefinito per <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> è `false`. Ciò significa che, per impostazione predefinita, le applicazioni associate non vengono avviate quando si chiama `Process.Start`.

Questa modifica è stata introdotta in .NET Core per motivi di prestazioni. In genere, <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> viene usato per avviare direttamente un'applicazione. L'avvio diretto di un'app non deve coinvolgere la shell di Windows e sostenere il costo delle prestazioni associato. Per rendere più veloce questo caso predefinito, .NET Core modifica il valore predefinito di <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> in `false`. Se necessario, è possibile acconsentire esplicitamente al percorso più lento.

#### <a name="version-introduced"></a>Versione introdotta

2.1

> [!NOTE]
> Nelle versioni precedenti di .NET Core, `UseShellExecute` non è stato implementato per Windows.

#### <a name="recommended-action"></a>Azione consigliata

Se l'app si basa sul comportamento precedente, chiamare <xref:System.Diagnostics.Process.Start(System.Diagnostics.ProcessStartInfo)?displayProperty=nameWithType> con <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute> impostato su `true` sull'oggetto <xref:System.Diagnostics.ProcessStartInfo>.

#### <a name="category"></a>Categoria

CoreFx

#### <a name="affected-apis"></a>API interessate

- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.ProcessStartInfo?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Diagnostics.Process.Start`
- `M:System.Diagnostics.ProcessStartInfo`

-->
