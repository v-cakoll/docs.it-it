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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 01db76802b96bd32e8a01cf86b1e682defe97a06
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="6002c-102">4208 - RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="6002c-102">4208 - RetryingSqlCommandDueToSqlError</span></span>
## <a name="properties"></a><span data-ttu-id="6002c-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="6002c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6002c-104">ID</span><span class="sxs-lookup"><span data-stu-id="6002c-104">ID</span></span>|<span data-ttu-id="6002c-105">4208</span><span class="sxs-lookup"><span data-stu-id="6002c-105">4208</span></span>|  
|<span data-ttu-id="6002c-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="6002c-106">Keywords</span></span>|<span data-ttu-id="6002c-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="6002c-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="6002c-108">Livello</span><span class="sxs-lookup"><span data-stu-id="6002c-108">Level</span></span>|<span data-ttu-id="6002c-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="6002c-109">Information</span></span>|  
|<span data-ttu-id="6002c-110">Canale</span><span class="sxs-lookup"><span data-stu-id="6002c-110">Channel</span></span>|<span data-ttu-id="6002c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="6002c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6002c-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6002c-112">Description</span></span>  
 <span data-ttu-id="6002c-113">Indica che il provider SQL ripete un comando SQL a causa di un errore SQL.</span><span class="sxs-lookup"><span data-stu-id="6002c-113">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6002c-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="6002c-114">Message</span></span>  
 <span data-ttu-id="6002c-115">Nuovo tentativo di esecuzione di un comando SQL in seguito a un errore SQL numero %1.</span><span class="sxs-lookup"><span data-stu-id="6002c-115">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6002c-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6002c-116">Details</span></span>  
  
|<span data-ttu-id="6002c-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="6002c-117">Data Item Name</span></span>|<span data-ttu-id="6002c-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="6002c-118">Data Item Type</span></span>|<span data-ttu-id="6002c-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6002c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6002c-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="6002c-120">ErrorNumber</span></span>|<span data-ttu-id="6002c-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="6002c-121">xs:string</span></span>|<span data-ttu-id="6002c-122">Numero di errore SQL.</span><span class="sxs-lookup"><span data-stu-id="6002c-122">The SQL error number.</span></span>|  
|<span data-ttu-id="6002c-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6002c-123">AppDomain</span></span>|<span data-ttu-id="6002c-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="6002c-124">xs:string</span></span>|<span data-ttu-id="6002c-125">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="6002c-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
