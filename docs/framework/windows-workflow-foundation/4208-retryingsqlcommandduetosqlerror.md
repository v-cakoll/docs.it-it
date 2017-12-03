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
ms.openlocfilehash: b3bfe7547fafb17503c972646d344263117d9d86
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="2f929-102">4208 - RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="2f929-102">4208 - RetryingSqlCommandDueToSqlError</span></span>
## <a name="properties"></a><span data-ttu-id="2f929-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="2f929-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2f929-104">ID</span><span class="sxs-lookup"><span data-stu-id="2f929-104">ID</span></span>|<span data-ttu-id="2f929-105">4208</span><span class="sxs-lookup"><span data-stu-id="2f929-105">4208</span></span>|  
|<span data-ttu-id="2f929-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2f929-106">Keywords</span></span>|<span data-ttu-id="2f929-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="2f929-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="2f929-108">Livello</span><span class="sxs-lookup"><span data-stu-id="2f929-108">Level</span></span>|<span data-ttu-id="2f929-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="2f929-109">Information</span></span>|  
|<span data-ttu-id="2f929-110">Canale</span><span class="sxs-lookup"><span data-stu-id="2f929-110">Channel</span></span>|<span data-ttu-id="2f929-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2f929-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2f929-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2f929-112">Description</span></span>  
 <span data-ttu-id="2f929-113">Indica che il provider SQL ripete un comando SQL a causa di un errore SQL.</span><span class="sxs-lookup"><span data-stu-id="2f929-113">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2f929-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="2f929-114">Message</span></span>  
 <span data-ttu-id="2f929-115">Nuovo tentativo di esecuzione di un comando SQL in seguito a un errore SQL numero %1.</span><span class="sxs-lookup"><span data-stu-id="2f929-115">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2f929-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="2f929-116">Details</span></span>  
  
|<span data-ttu-id="2f929-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="2f929-117">Data Item Name</span></span>|<span data-ttu-id="2f929-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="2f929-118">Data Item Type</span></span>|<span data-ttu-id="2f929-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2f929-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2f929-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="2f929-120">ErrorNumber</span></span>|<span data-ttu-id="2f929-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f929-121">xs:string</span></span>|<span data-ttu-id="2f929-122">Numero di errore SQL.</span><span class="sxs-lookup"><span data-stu-id="2f929-122">The SQL error number.</span></span>|  
|<span data-ttu-id="2f929-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2f929-123">AppDomain</span></span>|<span data-ttu-id="2f929-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f929-124">xs:string</span></span>|<span data-ttu-id="2f929-125">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2f929-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
