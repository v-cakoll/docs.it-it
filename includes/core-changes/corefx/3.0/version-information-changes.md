---
ms.openlocfilehash: 5612ebce67946e22aaeeba861115ce4f8967e1f5
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344443"
---
### <a name="apis-that-report-version-now-report-product-and-not-file-version"></a><span data-ttu-id="03253-101">API che segnalano ora la versione del prodotto e non la versione del file</span><span class="sxs-lookup"><span data-stu-id="03253-101">APIs that report version now report product and not file version</span></span>

<span data-ttu-id="03253-102">Molte API che restituiscono versioni in .NET Core restituiscono ora la versione del prodotto anziché la versione del file.</span><span class="sxs-lookup"><span data-stu-id="03253-102">Many of the APIs that return versions in .NET Core now return the product version rather than the file version.</span></span>

#### <a name="change-description"></a><span data-ttu-id="03253-103">Descrizione delle modifiche</span><span class="sxs-lookup"><span data-stu-id="03253-103">Change description</span></span>

<span data-ttu-id="03253-104">In .NET Core 2,2 e versioni precedenti, i metodi come <xref:System.Environment.Version?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>e la finestra di dialogo Proprietà file per gli assembly .NET Core riflettono la versione del file.</span><span class="sxs-lookup"><span data-stu-id="03253-104">In .NET Core 2.2 and previous versions, methods such as <xref:System.Environment.Version?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>, and the file properties dialog for .NET Core assemblies reflect the file version.</span></span> <span data-ttu-id="03253-105">A partire da .NET Core 3,0, riflettono la versione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="03253-105">Starting with .NET Core 3.0, they reflect the product version.</span></span>

<span data-ttu-id="03253-106">La figura seguente illustra la differenza nelle informazioni sulla versione per l'assembly *System. Runtime. dll* per .net core 2,2 (a sinistra) e .net core 3,0 (sulla destra) come visualizzato nella finestra di dialogo Proprietà file di **Esplora risorse** .</span><span class="sxs-lookup"><span data-stu-id="03253-106">The following figure illustrates the difference in version information for the *System.Runtime.dll* assembly for .NET Core 2.2 (on the left) and .NET Core 3.0 (on the right) as displayed by the **Windows Explorer** file properties dialog.</span></span>

![Differenza nelle informazioni sulla versione del prodotto](~/docs/images/core-changes/corefx/version-information-changes/file-details.png)

#### <a name="version-introduced"></a><span data-ttu-id="03253-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="03253-108">Version introduced</span></span>

<span data-ttu-id="03253-109">3.0</span><span class="sxs-lookup"><span data-stu-id="03253-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="03253-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="03253-110">Recommended action</span></span>

<span data-ttu-id="03253-111">nessuna.</span><span class="sxs-lookup"><span data-stu-id="03253-111">None.</span></span> <span data-ttu-id="03253-112">Questa modifica dovrebbe rendere intuitivo il rilevamento della versione anziché ottuso.</span><span class="sxs-lookup"><span data-stu-id="03253-112">This change should make version detection intuitive rather than obtuse.</span></span>

#### <a name="category"></a><span data-ttu-id="03253-113">Categoria</span><span class="sxs-lookup"><span data-stu-id="03253-113">Category</span></span>

<span data-ttu-id="03253-114">CoreFx</span><span class="sxs-lookup"><span data-stu-id="03253-114">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="03253-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="03253-115">Affected APIs</span></span>

- <xref:System.Environment.Version?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>

<!--

### Affected APIs

- `P:System.Environment.Version`
- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
