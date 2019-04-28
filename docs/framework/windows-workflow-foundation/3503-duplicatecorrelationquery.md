---
title: 3503 - DuplicateCorrelationQuery
ms.date: 03/30/2017
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
ms.openlocfilehash: 37a689b30b0bcab9124472deb98627afbe30dfee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755597"
---
# <a name="3503---duplicatecorrelationquery"></a><span data-ttu-id="eb8c6-102">3503 - DuplicateCorrelationQuery</span><span class="sxs-lookup"><span data-stu-id="eb8c6-102">3503 - DuplicateCorrelationQuery</span></span>
## <a name="properties"></a><span data-ttu-id="eb8c6-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="eb8c6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eb8c6-104">Id</span><span class="sxs-lookup"><span data-stu-id="eb8c6-104">ID</span></span>|<span data-ttu-id="eb8c6-105">3503</span><span class="sxs-lookup"><span data-stu-id="eb8c6-105">3503</span></span>|  
|<span data-ttu-id="eb8c6-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="eb8c6-106">Keywords</span></span>|<span data-ttu-id="eb8c6-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="eb8c6-107">WFServices</span></span>|  
|<span data-ttu-id="eb8c6-108">Livello</span><span class="sxs-lookup"><span data-stu-id="eb8c6-108">Level</span></span>|<span data-ttu-id="eb8c6-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="eb8c6-109">Warning</span></span>|  
|<span data-ttu-id="eb8c6-110">Canale</span><span class="sxs-lookup"><span data-stu-id="eb8c6-110">Channel</span></span>|<span data-ttu-id="eb8c6-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="eb8c6-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="eb8c6-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eb8c6-112">Description</span></span>  
 <span data-ttu-id="eb8c6-113">Indica che è stato trovato un elemento CorrelationQuery duplicato.</span><span class="sxs-lookup"><span data-stu-id="eb8c6-113">Indicates a duplicate CorrelationQuery was found.</span></span> <span data-ttu-id="eb8c6-114">La query duplicata non verrà usata per il calcolo della correlazione.</span><span class="sxs-lookup"><span data-stu-id="eb8c6-114">The duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="eb8c6-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="eb8c6-115">Message</span></span>  
 <span data-ttu-id="eb8c6-116">CorrelationQuery duplicata trovata con Where='%1'.</span><span class="sxs-lookup"><span data-stu-id="eb8c6-116">A duplicate CorrelationQuery was found with Where='%1'.</span></span> <span data-ttu-id="eb8c6-117">La query duplicata non verrà usata per il calcolo della correlazione.</span><span class="sxs-lookup"><span data-stu-id="eb8c6-117">This duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="eb8c6-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="eb8c6-118">Details</span></span>  
  
|<span data-ttu-id="eb8c6-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="eb8c6-119">Data Item Name</span></span>|<span data-ttu-id="eb8c6-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="eb8c6-120">Data Item Type</span></span>|<span data-ttu-id="eb8c6-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eb8c6-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="eb8c6-122">Dove</span><span class="sxs-lookup"><span data-stu-id="eb8c6-122">Where</span></span>|<span data-ttu-id="eb8c6-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="eb8c6-123">xs:string</span></span>|<span data-ttu-id="eb8c6-124">La parte Where della query di correlazione.</span><span class="sxs-lookup"><span data-stu-id="eb8c6-124">The Where portion of the correlation query.</span></span>|  
|<span data-ttu-id="eb8c6-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="eb8c6-125">AppDomain</span></span>|<span data-ttu-id="eb8c6-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="eb8c6-126">xs:string</span></span>|<span data-ttu-id="eb8c6-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="eb8c6-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
