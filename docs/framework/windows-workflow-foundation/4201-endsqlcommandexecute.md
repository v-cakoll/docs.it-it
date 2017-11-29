---
title: 4201 - EndSqlCommandExecute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae0dbc15-f98c-4096-a8d9-fbe4dc36f1cd
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 57c413ddae884f50e8f65eac146ccf5b2fc84b8a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="4201---endsqlcommandexecute"></a><span data-ttu-id="104f3-102">4201 - EndSqlCommandExecute</span><span class="sxs-lookup"><span data-stu-id="104f3-102">4201 - EndSqlCommandExecute</span></span>
## <a name="properties"></a><span data-ttu-id="104f3-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="104f3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="104f3-104">ID</span><span class="sxs-lookup"><span data-stu-id="104f3-104">ID</span></span>|<span data-ttu-id="104f3-105">4201</span><span class="sxs-lookup"><span data-stu-id="104f3-105">4201</span></span>|  
|<span data-ttu-id="104f3-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="104f3-106">Keywords</span></span>|<span data-ttu-id="104f3-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="104f3-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="104f3-108">Livello</span><span class="sxs-lookup"><span data-stu-id="104f3-108">Level</span></span>|<span data-ttu-id="104f3-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="104f3-109">Verbose</span></span>|  
|<span data-ttu-id="104f3-110">Canale</span><span class="sxs-lookup"><span data-stu-id="104f3-110">Channel</span></span>|<span data-ttu-id="104f3-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="104f3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="104f3-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="104f3-112">Description</span></span>  
 <span data-ttu-id="104f3-113">Indica che un comando SQL ha completato l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="104f3-113">Indicates a SQL command has finished executing.</span></span>  
  
## <a name="message"></a><span data-ttu-id="104f3-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="104f3-114">Message</span></span>  
 <span data-ttu-id="104f3-115">Fine esecuzione comando SQL: %1</span><span class="sxs-lookup"><span data-stu-id="104f3-115">End SQL command execution: %1</span></span>  
  
## <a name="details"></a><span data-ttu-id="104f3-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="104f3-116">Details</span></span>  
  
|<span data-ttu-id="104f3-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="104f3-117">Data Item Name</span></span>|<span data-ttu-id="104f3-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="104f3-118">Data Item Type</span></span>|<span data-ttu-id="104f3-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="104f3-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="104f3-120">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="104f3-120">SqlCommand</span></span>|<span data-ttu-id="104f3-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="104f3-121">xs:string</span></span>|<span data-ttu-id="104f3-122">Comando SQL eseguito.</span><span class="sxs-lookup"><span data-stu-id="104f3-122">The SQL command that was executed.</span></span>|  
|<span data-ttu-id="104f3-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="104f3-123">AppDomain</span></span>|<span data-ttu-id="104f3-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="104f3-124">xs:string</span></span>|<span data-ttu-id="104f3-125">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="104f3-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
