---
ms.openlocfilehash: 92c03328414410d56a2ff5f445639757367b42c7
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420428"
---
### <a name="processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start"></a>Process. StartInfo genera l'eccezione InvalidOperationException per i processi non avviati

La lettura della <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> proprietà per i processi non avviati dal codice genera un'eccezione <xref:System.InvalidOperationException> .

#### <a name="change-description"></a>Descrizione modifica:

In .NET Framework, l'accesso alla <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> proprietà per i processi non avviati dal codice restituisce un <xref:System.Diagnostics.ProcessStartInfo> oggetto fittizio. L'oggetto fittizio contiene i valori predefiniti per tutte le proprietà, ad eccezione di <xref:System.Diagnostics.ProcessStartInfo.EnvironmentVariables> .

A partire da .NET Core 1,0, se si legge la <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> proprietà per un processo che non è stato avviato (ovvero chiamando <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> ), <xref:System.InvalidOperationException> viene generata un'eccezione.

#### <a name="version-introduced"></a>Versione introdotta

1.0

#### <a name="recommended-action"></a>Azione consigliata

Non accedere alla <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> proprietà per i processi non avviati dal codice. Ad esempio, non leggere questa proprietà per i processi restituiti da <xref:System.Diagnostics.Process.GetProcesses%2A?displayProperty=nameWithType> .

#### <a name="category"></a>Category

Principali librerie .NET

#### <a name="affected-apis"></a>API interessate

- <xref:System.Diagnostics.Process.StartInfo?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Diagnostics.Process.StartInfo`

-->
