---
ms.openlocfilehash: 58cb3580c8701773452ae8338f036a94bbee80c5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77449399"
---
### <a name="change-in-default-value-of-useshellexecute"></a>Modifica del valore predefinito di UseShellExecute

<xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType>ha un valore `false` predefinito di in .NET Core. In .NET Framework il `true`valore predefinito è .

#### <a name="change-description"></a>Descrizione modifica:

<xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>consente di avviare direttamente un'applicazione, `Process.Start("mspaint.exe")` ad esempio, con codice come quello che avvia Paint. Consente inoltre di avviare indirettamente <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> un'applicazione associata se è impostata su `true`. In .NET Framework, il <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> `true`valore predefinito per `Process.Start("mytextfile.txt")` è , ovvero il codice, ad esempio lancerebbe Il Blocco note, se sono stati associati file *con estensione txt* a tale editor. Per impedire l'avvio indiretto di un'app `false`in .NET Framework, è necessario impostare in modo esplicito su <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> . In .NET Core, il <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> `false`valore predefinito per è . Ciò significa che, per impostazione predefinita, `Process.Start`le applicazioni associate non vengono avviate quando si chiama .

Questa modifica è stata introdotta in .NET Core per motivi di prestazioni. In <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> genere, viene utilizzato per avviare direttamente un'applicazione. L'avvio diretto di un'app non deve coinvolgere la shell di Windows e comporta il costo delle prestazioni associato. Per velocizzare questo caso predefinito, .NET <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> `false`Core modifica il valore predefinito di . È possibile attivare il percorso più lento se necessario.

#### <a name="version-introduced"></a>Versione introdotta

2.1

> [!NOTE]
> Nelle versioni precedenti di `UseShellExecute` .NET Core, non era implementato per Windows.

#### <a name="recommended-action"></a>Azione consigliata

Se l'app si basa sul <xref:System.Diagnostics.Process.Start(System.Diagnostics.ProcessStartInfo)?displayProperty=nameWithType> <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute> comportamento `true` precedente, <xref:System.Diagnostics.ProcessStartInfo> chiama con impostato su sull'oggetto.

#### <a name="category"></a>Category

CoreFx

#### <a name="affected-apis"></a>API interessate

- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.ProcessStartInfo?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Diagnostics.Process.Start`
- `M:System.Diagnostics.ProcessStartInfo`

-->
