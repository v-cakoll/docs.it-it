---
ms.openlocfilehash: 8e0c934cd8c3cb8c08a526c7e145436db6ecf4a5
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2019
ms.locfileid: "68237599"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a><span data-ttu-id="15219-101">Miglioramenti all'algoritmo di allocazione dello spazio per le righe con ridimensionamento proporzionale (Star) della griglia</span><span class="sxs-lookup"><span data-stu-id="15219-101">Improvements to Grid star-rows space allocating algorithm</span></span>

|   |   |
|---|---|
|<span data-ttu-id="15219-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="15219-102">Details</span></span>|<span data-ttu-id="15219-103">È stato corretto un bug nell'[algoritmo per l'allocazione delle dimensioni](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md) in un elemento <xref:System.Windows.Controls.Grid> introdotto in .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="15219-103">Fixed a bug in the [algorithm for allocating sizes to](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) in a <xref:System.Windows.Controls.Grid> introduced in .NET Framework 4.7.</span></span>  <span data-ttu-id="15219-104">In alcuni casi, ad esempio una griglia con <code>Height=&quot;Auto&quot;</code> contenente righe vuote, le righe venivano disposte nella posizione errata, anche totalmente all'esterno della griglia.</span><span class="sxs-lookup"><span data-stu-id="15219-104">In some cases, such as a Grid with <code>Height=&quot;Auto&quot;</code> containing empty rows, rows were arranged at the wrong position, possibly outside the Grid altogether.</span></span>|
|<span data-ttu-id="15219-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="15219-105">Suggestion</span></span>|<span data-ttu-id="15219-106">Perché l'applicazione possa usufruire di queste modifiche, è necessario che sia eseguita in .NET Framework 4.8 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="15219-106">In order for the application to benefit from these changes, it must run on the .NET Framework 4.8 or later.</span></span>|
|<span data-ttu-id="15219-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="15219-107">Scope</span></span>|<span data-ttu-id="15219-108">Principale</span><span class="sxs-lookup"><span data-stu-id="15219-108">Major</span></span>|
|<span data-ttu-id="15219-109">Versione</span><span class="sxs-lookup"><span data-stu-id="15219-109">Version</span></span>|<span data-ttu-id="15219-110">4.8</span><span class="sxs-lookup"><span data-stu-id="15219-110">4.8</span></span>|
|<span data-ttu-id="15219-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="15219-111">Type</span></span>|<span data-ttu-id="15219-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="15219-112">Runtime</span></span>|
