---
ms.openlocfilehash: 1580c8c8b7bdad91656f494537230293dbaaf93b
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021635"
---
### <a name="apis-that-report-version-now-report-product-and-not-file-version"></a>API che segnalano ora la versione del report e non la versione del file

Molte delle API che restituiscono versioni in .NET Core ora restituiscono la versione del prodotto anziché la versione del file.

#### <a name="change-description"></a>Descrizione modifica:

In .NET Core 2.2 e versioni <xref:System.Environment.Version?displayProperty=nameWithType> <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>precedenti, metodi quali , , e la finestra di dialogo delle proprietà dei file per gli assembly .NET Core riflettono la versione del file. A partire da .NET Core 3.0, riflettono la versione del prodotto.

Nella figura seguente viene illustrata la differenza nelle informazioni sulla versione per l'assembly *System.Runtime.dll* per .NET Core 2.2 (a sinistra) e .NET Core 3.0 (a destra) come visualizzato dalla finestra di dialogo delle proprietà del file di **Esplora risorse.**

![Differenza nelle informazioni sulla versione del prodotto](~/docs/images/core-changes/corefx/version-information-changes/file-details.png)

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

No. Questa modifica dovrebbe rendere intuitivo il rilevamento della versione anziché ottuso.

#### <a name="category"></a>Category

Librerie .NET di base

#### <a name="affected-apis"></a>API interessate

- <xref:System.Environment.Version?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>

<!--

### Affected APIs

- `P:System.Environment.Version`
- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
