---
ms.openlocfilehash: 62702de022656e45466a45f4150e518226a3fecc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621994"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a><span data-ttu-id="4e789-101">Miglioramenti all'algoritmo di allocazione dello spazio per le righe con ridimensionamento proporzionale (Star) della griglia</span><span class="sxs-lookup"><span data-stu-id="4e789-101">Improvements to Grid star-rows space allocating algorithm</span></span>

#### <a name="details"></a><span data-ttu-id="4e789-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="4e789-102">Details</span></span>

<span data-ttu-id="4e789-103">È stato corretto un bug nell'[algoritmo per l'allocazione delle dimensioni](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md) in un elemento <xref:System.Windows.Controls.Grid> introdotto in .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="4e789-103">Fixed a bug in the [algorithm for allocating sizes to](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) in a <xref:System.Windows.Controls.Grid> introduced in .NET Framework 4.7.</span></span>  <span data-ttu-id="4e789-104">In alcuni casi, ad esempio una griglia con <code>Height=&quot;Auto&quot;</code> contenente righe vuote, le righe venivano disposte nella posizione errata, anche totalmente all'esterno della griglia.</span><span class="sxs-lookup"><span data-stu-id="4e789-104">In some cases, such as a Grid with <code>Height=&quot;Auto&quot;</code> containing empty rows, rows were arranged at the wrong position, possibly outside the Grid altogether.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4e789-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="4e789-105">Suggestion</span></span>

<span data-ttu-id="4e789-106">Perché l'applicazione possa usufruire di queste modifiche, è necessario che sia eseguita in .NET Framework 4.8 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="4e789-106">In order for the application to benefit from these changes, it must run on the .NET Framework 4.8 or later.</span></span>

| <span data-ttu-id="4e789-107">Nome</span><span class="sxs-lookup"><span data-stu-id="4e789-107">Name</span></span>    | <span data-ttu-id="4e789-108">Valore</span><span class="sxs-lookup"><span data-stu-id="4e789-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4e789-109">Scope</span><span class="sxs-lookup"><span data-stu-id="4e789-109">Scope</span></span>   |<span data-ttu-id="4e789-110">Principale</span><span class="sxs-lookup"><span data-stu-id="4e789-110">Major</span></span>|
|<span data-ttu-id="4e789-111">Version</span><span class="sxs-lookup"><span data-stu-id="4e789-111">Version</span></span>|<span data-ttu-id="4e789-112">4.8</span><span class="sxs-lookup"><span data-stu-id="4e789-112">4.8</span></span>|
|<span data-ttu-id="4e789-113">Type</span><span class="sxs-lookup"><span data-stu-id="4e789-113">Type</span></span>|<span data-ttu-id="4e789-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="4e789-114">Runtime</span></span>|
