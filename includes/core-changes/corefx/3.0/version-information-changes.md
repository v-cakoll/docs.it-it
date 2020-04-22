---
ms.openlocfilehash: 1580c8c8b7bdad91656f494537230293dbaaf93b
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021635"
---
### <a name="apis-that-report-version-now-report-product-and-not-file-version"></a><span data-ttu-id="dcd5b-101">API che segnalano ora la versione del report e non la versione del file</span><span class="sxs-lookup"><span data-stu-id="dcd5b-101">APIs that report version now report product and not file version</span></span>

<span data-ttu-id="dcd5b-102">Molte delle API che restituiscono versioni in .NET Core ora restituiscono la versione del prodotto anziché la versione del file.</span><span class="sxs-lookup"><span data-stu-id="dcd5b-102">Many of the APIs that return versions in .NET Core now return the product version rather than the file version.</span></span>

#### <a name="change-description"></a><span data-ttu-id="dcd5b-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="dcd5b-103">Change description</span></span>

<span data-ttu-id="dcd5b-104">In .NET Core 2.2 e versioni <xref:System.Environment.Version?displayProperty=nameWithType> <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>precedenti, metodi quali , , e la finestra di dialogo delle proprietà dei file per gli assembly .NET Core riflettono la versione del file.</span><span class="sxs-lookup"><span data-stu-id="dcd5b-104">In .NET Core 2.2 and previous versions, methods such as <xref:System.Environment.Version?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>, and the file properties dialog for .NET Core assemblies reflect the file version.</span></span> <span data-ttu-id="dcd5b-105">A partire da .NET Core 3.0, riflettono la versione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="dcd5b-105">Starting with .NET Core 3.0, they reflect the product version.</span></span>

<span data-ttu-id="dcd5b-106">Nella figura seguente viene illustrata la differenza nelle informazioni sulla versione per l'assembly *System.Runtime.dll* per .NET Core 2.2 (a sinistra) e .NET Core 3.0 (a destra) come visualizzato dalla finestra di dialogo delle proprietà del file di **Esplora risorse.**</span><span class="sxs-lookup"><span data-stu-id="dcd5b-106">The following figure illustrates the difference in version information for the *System.Runtime.dll* assembly for .NET Core 2.2 (on the left) and .NET Core 3.0 (on the right) as displayed by the **Windows Explorer** file properties dialog.</span></span>

![Differenza nelle informazioni sulla versione del prodotto](~/docs/images/core-changes/corefx/version-information-changes/file-details.png)

#### <a name="version-introduced"></a><span data-ttu-id="dcd5b-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="dcd5b-108">Version introduced</span></span>

<span data-ttu-id="dcd5b-109">3.0</span><span class="sxs-lookup"><span data-stu-id="dcd5b-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="dcd5b-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="dcd5b-110">Recommended action</span></span>

<span data-ttu-id="dcd5b-111">No.</span><span class="sxs-lookup"><span data-stu-id="dcd5b-111">None.</span></span> <span data-ttu-id="dcd5b-112">Questa modifica dovrebbe rendere intuitivo il rilevamento della versione anziché ottuso.</span><span class="sxs-lookup"><span data-stu-id="dcd5b-112">This change should make version detection intuitive rather than obtuse.</span></span>

#### <a name="category"></a><span data-ttu-id="dcd5b-113">Category</span><span class="sxs-lookup"><span data-stu-id="dcd5b-113">Category</span></span>

<span data-ttu-id="dcd5b-114">Librerie .NET di base</span><span class="sxs-lookup"><span data-stu-id="dcd5b-114">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="dcd5b-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="dcd5b-115">Affected APIs</span></span>

- <xref:System.Environment.Version?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>

<!--

### Affected APIs

- `P:System.Environment.Version`
- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
