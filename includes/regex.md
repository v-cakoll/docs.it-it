---
ms.openlocfilehash: b893966ceb65246ed6a7d214011b17ca14c50d5a
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85802851"
---

> [!WARNING]
> <span data-ttu-id="ba8b4-101">Quando <xref:System.Text.RegularExpressions> si usa per elaborare un input non attendibile, passare un timeout.</span><span class="sxs-lookup"><span data-stu-id="ba8b4-101">When using <xref:System.Text.RegularExpressions> to process untrusted input, pass a timeout.</span></span> <span data-ttu-id="ba8b4-102">Un utente malintenzionato può fornire l'input per `RegularExpressions` provocare un [attacco Denial of Service](https://www.us-cert.gov/ncas/tips/ST04-015).</span><span class="sxs-lookup"><span data-stu-id="ba8b4-102">A malicious user can provide input to `RegularExpressions` causing a [Denial-of-Service attack](https://www.us-cert.gov/ncas/tips/ST04-015).</span></span> <span data-ttu-id="ba8b4-103">Le API di ASP.NET Core Framework che usano `RegularExpressions` passano un timeout.</span><span class="sxs-lookup"><span data-stu-id="ba8b4-103">ASP.NET Core framework APIs that use `RegularExpressions` pass a timeout.</span></span>
