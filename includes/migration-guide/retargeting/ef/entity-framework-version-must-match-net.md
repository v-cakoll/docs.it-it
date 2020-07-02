---
ms.openlocfilehash: 863e7035827537e0f943af05c2f0232029b99db8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617192"
---
### <a name="entity-framework-version-must-match-the-net-framework-version"></a><span data-ttu-id="9d366-101">La versione di Entity Framework deve corrispondere alla versione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9d366-101">Entity Framework version must match the .NET Framework version</span></span>

#### <a name="details"></a><span data-ttu-id="9d366-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="9d366-102">Details</span></span>

<span data-ttu-id="9d366-103">La versione di Entity Framework (EF) deve corrispondere alla versione .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9d366-103">The Entity Framework (EF) version should be matched with the .NET Framework version.</span></span> <span data-ttu-id="9d366-104">Per .NET Framework 4.5 è consigliato Entity Framework 5.</span><span class="sxs-lookup"><span data-stu-id="9d366-104">Entity Framework 5 is recommended for .NET Framework 4.5.</span></span> <span data-ttu-id="9d366-105">Esistono alcuni problemi noti con Entity Framework 4.x in un progetto .NET Framework 4.5 in relazione a <xref:System.ComponentModel.DataAnnotations>.</span><span class="sxs-lookup"><span data-stu-id="9d366-105">There are some known issues with EF 4.x in a .NET Framework 4.5 project around <xref:System.ComponentModel.DataAnnotations>.</span></span> <span data-ttu-id="9d366-106">In .NET Framework 4,5 questi elementi sono stati spostati in un assembly diverso, pertanto si verificano problemi di individuazione delle annotazioni da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="9d366-106">In .NET Framework 4.5, these were moved to a different assembly, so there are issues determining which annotations to use.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9d366-107">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="9d366-107">Suggestion</span></span>

<span data-ttu-id="9d366-108">Eseguire l'aggiornamento a Entity Framework 5 per .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="9d366-108">Upgrade to Entity Framework 5 for .NET Framework 4.5</span></span>

| <span data-ttu-id="9d366-109">Nome</span><span class="sxs-lookup"><span data-stu-id="9d366-109">Name</span></span>    | <span data-ttu-id="9d366-110">Valore</span><span class="sxs-lookup"><span data-stu-id="9d366-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9d366-111">Scope</span><span class="sxs-lookup"><span data-stu-id="9d366-111">Scope</span></span>   | <span data-ttu-id="9d366-112">Principale</span><span class="sxs-lookup"><span data-stu-id="9d366-112">Major</span></span>       |
| <span data-ttu-id="9d366-113">Version</span><span class="sxs-lookup"><span data-stu-id="9d366-113">Version</span></span> | <span data-ttu-id="9d366-114">4.5</span><span class="sxs-lookup"><span data-stu-id="9d366-114">4.5</span></span>         |
| <span data-ttu-id="9d366-115">Type</span><span class="sxs-lookup"><span data-stu-id="9d366-115">Type</span></span>    | <span data-ttu-id="9d366-116">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="9d366-116">Retargeting</span></span> |
