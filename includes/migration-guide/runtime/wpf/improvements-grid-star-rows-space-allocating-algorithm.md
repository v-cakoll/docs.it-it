---
ms.openlocfilehash: 8e0c934cd8c3cb8c08a526c7e145436db6ecf4a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "68237599"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a><span data-ttu-id="c2ae2-101">Miglioramenti all'algoritmo di allocazione dello spazio per le righe con ridimensionamento proporzionale (Star) della griglia</span><span class="sxs-lookup"><span data-stu-id="c2ae2-101">Improvements to Grid star-rows space allocating algorithm</span></span>

|   |   |
|---|---|
|<span data-ttu-id="c2ae2-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c2ae2-102">Details</span></span>|<span data-ttu-id="c2ae2-103">È stato corretto un bug nell'[algoritmo per l'allocazione delle dimensioni](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md) in un elemento <xref:System.Windows.Controls.Grid> introdotto in .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="c2ae2-103">Fixed a bug in the [algorithm for allocating sizes to](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) in a <xref:System.Windows.Controls.Grid> introduced in .NET Framework 4.7.</span></span>  <span data-ttu-id="c2ae2-104">In alcuni casi, ad esempio una griglia con <code>Height=&quot;Auto&quot;</code> contenente righe vuote, le righe venivano disposte nella posizione errata, anche totalmente all'esterno della griglia.</span><span class="sxs-lookup"><span data-stu-id="c2ae2-104">In some cases, such as a Grid with <code>Height=&quot;Auto&quot;</code> containing empty rows, rows were arranged at the wrong position, possibly outside the Grid altogether.</span></span>|
|<span data-ttu-id="c2ae2-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="c2ae2-105">Suggestion</span></span>|<span data-ttu-id="c2ae2-106">Perché l'applicazione possa usufruire di queste modifiche, è necessario che sia eseguita in .NET Framework 4.8 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="c2ae2-106">In order for the application to benefit from these changes, it must run on the .NET Framework 4.8 or later.</span></span>|
|<span data-ttu-id="c2ae2-107">Scope</span><span class="sxs-lookup"><span data-stu-id="c2ae2-107">Scope</span></span>|<span data-ttu-id="c2ae2-108">Principale</span><span class="sxs-lookup"><span data-stu-id="c2ae2-108">Major</span></span>|
|<span data-ttu-id="c2ae2-109">Versione</span><span class="sxs-lookup"><span data-stu-id="c2ae2-109">Version</span></span>|<span data-ttu-id="c2ae2-110">4.8</span><span class="sxs-lookup"><span data-stu-id="c2ae2-110">4.8</span></span>|
|<span data-ttu-id="c2ae2-111">Type</span><span class="sxs-lookup"><span data-stu-id="c2ae2-111">Type</span></span>|<span data-ttu-id="c2ae2-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="c2ae2-112">Runtime</span></span>|
