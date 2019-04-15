---
ms.openlocfilehash: 4c6a89f9753989a5ad061e847dff70d2af0b3cf4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234726"
---
### <a name="entity-framework-version-must-match-the-net-framework-version"></a><span data-ttu-id="2739f-101">La versione di Entity Framework deve corrispondere alla versione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2739f-101">Entity Framework version must match the .NET Framework version</span></span>

|   |   |
|---|---|
|<span data-ttu-id="2739f-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="2739f-102">Details</span></span>|<span data-ttu-id="2739f-103">La versione di Entity Framework deve corrispondere alla versione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2739f-103">The entity framework version should be matched with the .NET framework version.</span></span> <span data-ttu-id="2739f-104">Per .NET Framework 4.5 è consigliato Entity Framework 5.</span><span class="sxs-lookup"><span data-stu-id="2739f-104">Entity Framework 5 is recommended for .NET Framework 4.5.</span></span> <span data-ttu-id="2739f-105">Esistono alcuni problemi noti con Entity Framework 4.x in un progetto .NET Framework 4.5 in relazione a <xref:System.ComponentModel.DataAnnotations>.</span><span class="sxs-lookup"><span data-stu-id="2739f-105">There are some known issues with EF 4.x in a .NET Framework 4.5 project around <xref:System.ComponentModel.DataAnnotations>.</span></span> <span data-ttu-id="2739f-106">In .NET 4.5, questi elementi sono stati spostati in un assembly diverso, pertanto vi sono problemi a determinare quali annotazioni usare.</span><span class="sxs-lookup"><span data-stu-id="2739f-106">In .NET 4.5, these were moved to a different assembly, so there are issues determining which annotations to use.</span></span>|
|<span data-ttu-id="2739f-107">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="2739f-107">Suggestion</span></span>|<span data-ttu-id="2739f-108">Eseguire l'aggiornamento a Entity Framework 5 per .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="2739f-108">Upgrade to Entity Framework 5 for .NET Framework 4.5</span></span>|
|<span data-ttu-id="2739f-109">Ambito</span><span class="sxs-lookup"><span data-stu-id="2739f-109">Scope</span></span>|<span data-ttu-id="2739f-110">Principale</span><span class="sxs-lookup"><span data-stu-id="2739f-110">Major</span></span>|
|<span data-ttu-id="2739f-111">Versione</span><span class="sxs-lookup"><span data-stu-id="2739f-111">Version</span></span>|<span data-ttu-id="2739f-112">4.5</span><span class="sxs-lookup"><span data-stu-id="2739f-112">4.5</span></span>|
|<span data-ttu-id="2739f-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="2739f-113">Type</span></span>|<span data-ttu-id="2739f-114">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="2739f-114">Retargeting</span></span>|
