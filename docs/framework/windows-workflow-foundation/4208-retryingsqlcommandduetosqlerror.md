---
title: 4208 - RetryingSqlCommandDueToSqlError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8e6483a-a6e4-4bbf-82ec-cd8b6e711aad
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 51374a25ee11b3344e950670cc7882db42d39779
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="bd270-102">4208 - RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="bd270-102">4208 - RetryingSqlCommandDueToSqlError</span></span>
## <a name="properties"></a><span data-ttu-id="bd270-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="bd270-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bd270-104">ID</span><span class="sxs-lookup"><span data-stu-id="bd270-104">ID</span></span>|<span data-ttu-id="bd270-105">4208</span><span class="sxs-lookup"><span data-stu-id="bd270-105">4208</span></span>|  
|<span data-ttu-id="bd270-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="bd270-106">Keywords</span></span>|<span data-ttu-id="bd270-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="bd270-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="bd270-108">Livello</span><span class="sxs-lookup"><span data-stu-id="bd270-108">Level</span></span>|<span data-ttu-id="bd270-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="bd270-109">Information</span></span>|  
|<span data-ttu-id="bd270-110">Canale</span><span class="sxs-lookup"><span data-stu-id="bd270-110">Channel</span></span>|<span data-ttu-id="bd270-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="bd270-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bd270-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bd270-112">Description</span></span>  
 <span data-ttu-id="bd270-113">Indica che il provider SQL ripete un comando SQL a causa di un errore SQL.</span><span class="sxs-lookup"><span data-stu-id="bd270-113">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bd270-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="bd270-114">Message</span></span>  
 <span data-ttu-id="bd270-115">Nuovo tentativo di esecuzione di un comando SQL in seguito a un errore SQL numero %1.</span><span class="sxs-lookup"><span data-stu-id="bd270-115">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bd270-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="bd270-116">Details</span></span>  
  
|<span data-ttu-id="bd270-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="bd270-117">Data Item Name</span></span>|<span data-ttu-id="bd270-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="bd270-118">Data Item Type</span></span>|<span data-ttu-id="bd270-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bd270-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bd270-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="bd270-120">ErrorNumber</span></span>|<span data-ttu-id="bd270-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="bd270-121">xs:string</span></span>|<span data-ttu-id="bd270-122">Numero di errore SQL.</span><span class="sxs-lookup"><span data-stu-id="bd270-122">The SQL error number.</span></span>|  
|<span data-ttu-id="bd270-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bd270-123">AppDomain</span></span>|<span data-ttu-id="bd270-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="bd270-124">xs:string</span></span>|<span data-ttu-id="bd270-125">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="bd270-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
