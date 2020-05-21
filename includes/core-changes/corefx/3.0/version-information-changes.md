---
ms.openlocfilehash: bb264e406c6604c3606e564d99018eda0f9e8d89
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721043"
---
### <a name="apis-that-report-version-now-report-product-and-not-file-version"></a>API che segnalano ora la versione del prodotto e non la versione del file

Molte API che restituiscono versioni in .NET Core restituiscono ora la versione del prodotto anziché la versione del file.

#### <a name="change-description"></a>Descrizione modifica:

In .NET Core 2,2 e versioni precedenti, i metodi come <xref:System.Environment.Version?displayProperty=nameWithType> , <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> e la finestra di dialogo Proprietà file per gli assembly .NET Core riflettono la versione del file. A partire da .NET Core 3,0, riflettono la versione del prodotto.

La figura seguente illustra la differenza nelle informazioni sulla versione per l'assembly *System. Runtime. dll* per .net core 2,2 (a sinistra) e .net core 3,0 (sulla destra) come visualizzato nella finestra di dialogo Proprietà file di **Esplora risorse** .

![Differenza nelle informazioni sulla versione del prodotto](~/docs/images/core-changes/corefx/version-information-changes/file-details.png)

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

No. Questa modifica dovrebbe rendere intuitivo il rilevamento della versione anziché ottuso.

#### <a name="category"></a>Category

Principali librerie .NET

#### <a name="affected-apis"></a>API interessate

- <xref:System.Environment.Version?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Environment.Version`
- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
