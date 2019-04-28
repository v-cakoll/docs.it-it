---
title: 4208 - RetryingSqlCommandDueToSqlError
ms.date: 03/30/2017
ms.assetid: a8e6483a-a6e4-4bbf-82ec-cd8b6e711aad
ms.openlocfilehash: a97336f12ccfe041b79328bcb48f4e7214a05b63
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774296"
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="0d993-102">4208 - RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="0d993-102">4208 - RetryingSqlCommandDueToSqlError</span></span>
## <a name="properties"></a><span data-ttu-id="0d993-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="0d993-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0d993-104">Id</span><span class="sxs-lookup"><span data-stu-id="0d993-104">ID</span></span>|<span data-ttu-id="0d993-105">4208</span><span class="sxs-lookup"><span data-stu-id="0d993-105">4208</span></span>|  
|<span data-ttu-id="0d993-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0d993-106">Keywords</span></span>|<span data-ttu-id="0d993-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="0d993-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="0d993-108">Livello</span><span class="sxs-lookup"><span data-stu-id="0d993-108">Level</span></span>|<span data-ttu-id="0d993-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="0d993-109">Information</span></span>|  
|<span data-ttu-id="0d993-110">Canale</span><span class="sxs-lookup"><span data-stu-id="0d993-110">Channel</span></span>|<span data-ttu-id="0d993-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0d993-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0d993-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d993-112">Description</span></span>  
 <span data-ttu-id="0d993-113">Indica che il provider SQL ripete un comando SQL a causa di un errore SQL.</span><span class="sxs-lookup"><span data-stu-id="0d993-113">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0d993-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="0d993-114">Message</span></span>  
 <span data-ttu-id="0d993-115">Nuovo tentativo di esecuzione di un comando SQL in seguito a un errore SQL numero %1.</span><span class="sxs-lookup"><span data-stu-id="0d993-115">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0d993-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0d993-116">Details</span></span>  
  
|<span data-ttu-id="0d993-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="0d993-117">Data Item Name</span></span>|<span data-ttu-id="0d993-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="0d993-118">Data Item Type</span></span>|<span data-ttu-id="0d993-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d993-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0d993-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="0d993-120">ErrorNumber</span></span>|<span data-ttu-id="0d993-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="0d993-121">xs:string</span></span>|<span data-ttu-id="0d993-122">Numero di errore SQL.</span><span class="sxs-lookup"><span data-stu-id="0d993-122">The SQL error number.</span></span>|  
|<span data-ttu-id="0d993-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0d993-123">AppDomain</span></span>|<span data-ttu-id="0d993-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="0d993-124">xs:string</span></span>|<span data-ttu-id="0d993-125">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0d993-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
