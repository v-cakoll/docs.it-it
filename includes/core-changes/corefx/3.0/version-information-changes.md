---
ms.openlocfilehash: 5612ebce67946e22aaeeba861115ce4f8967e1f5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75344443"
---
### <a name="apis-that-report-version-now-report-product-and-not-file-version"></a><span data-ttu-id="dfdaa-101">API che segnalano ora la versione del report e non la versione del file</span><span class="sxs-lookup"><span data-stu-id="dfdaa-101">APIs that report version now report product and not file version</span></span>

<span data-ttu-id="dfdaa-102">Molte delle API che restituiscono versioni in .NET Core ora restituiscono la versione del prodotto anziché la versione del file.</span><span class="sxs-lookup"><span data-stu-id="dfdaa-102">Many of the APIs that return versions in .NET Core now return the product version rather than the file version.</span></span>

#### <a name="change-description"></a><span data-ttu-id="dfdaa-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="dfdaa-103">Change description</span></span>

<span data-ttu-id="dfdaa-104">In .NET Core 2.2 e versioni <xref:System.Environment.Version?displayProperty=nameWithType> <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>precedenti, metodi quali , , e la finestra di dialogo delle proprietà dei file per gli assembly .NET Core riflettono la versione del file.</span><span class="sxs-lookup"><span data-stu-id="dfdaa-104">In .NET Core 2.2 and previous versions, methods such as <xref:System.Environment.Version?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>, and the file properties dialog for .NET Core assemblies reflect the file version.</span></span> <span data-ttu-id="dfdaa-105">A partire da .NET Core 3.0, riflettono la versione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="dfdaa-105">Starting with .NET Core 3.0, they reflect the product version.</span></span>

<span data-ttu-id="dfdaa-106">Nella figura seguente viene illustrata la differenza nelle informazioni sulla versione per l'assembly *System.Runtime.dll* per .NET Core 2.2 (a sinistra) e .NET Core 3.0 (a destra) come visualizzato dalla finestra di dialogo delle proprietà del file di **Esplora risorse.**</span><span class="sxs-lookup"><span data-stu-id="dfdaa-106">The following figure illustrates the difference in version information for the *System.Runtime.dll* assembly for .NET Core 2.2 (on the left) and .NET Core 3.0 (on the right) as displayed by the **Windows Explorer** file properties dialog.</span></span>

![Differenza nelle informazioni sulla versione del prodotto](~/docs/images/core-changes/corefx/version-information-changes/file-details.png)

#### <a name="version-introduced"></a><span data-ttu-id="dfdaa-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="dfdaa-108">Version introduced</span></span>

<span data-ttu-id="dfdaa-109">3.0</span><span class="sxs-lookup"><span data-stu-id="dfdaa-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="dfdaa-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="dfdaa-110">Recommended action</span></span>

<span data-ttu-id="dfdaa-111">No.</span><span class="sxs-lookup"><span data-stu-id="dfdaa-111">None.</span></span> <span data-ttu-id="dfdaa-112">Questa modifica dovrebbe rendere intuitivo il rilevamento della versione anziché ottuso.</span><span class="sxs-lookup"><span data-stu-id="dfdaa-112">This change should make version detection intuitive rather than obtuse.</span></span>

#### <a name="category"></a><span data-ttu-id="dfdaa-113">Category</span><span class="sxs-lookup"><span data-stu-id="dfdaa-113">Category</span></span>

<span data-ttu-id="dfdaa-114">CoreFx</span><span class="sxs-lookup"><span data-stu-id="dfdaa-114">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="dfdaa-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="dfdaa-115">Affected APIs</span></span>

- <xref:System.Environment.Version?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>

<!--

### Affected APIs

- `P:System.Environment.Version`
- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
