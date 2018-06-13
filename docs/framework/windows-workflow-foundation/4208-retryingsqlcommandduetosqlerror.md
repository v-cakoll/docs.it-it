---
title: 4208 - RetryingSqlCommandDueToSqlError
ms.date: 03/30/2017
ms.assetid: a8e6483a-a6e4-4bbf-82ec-cd8b6e711aad
ms.openlocfilehash: a97336f12ccfe041b79328bcb48f4e7214a05b63
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511595"
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="b4c20-102">4208 - RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="b4c20-102">4208 - RetryingSqlCommandDueToSqlError</span></span>
## <a name="properties"></a><span data-ttu-id="b4c20-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="b4c20-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b4c20-104">ID</span><span class="sxs-lookup"><span data-stu-id="b4c20-104">ID</span></span>|<span data-ttu-id="b4c20-105">4208</span><span class="sxs-lookup"><span data-stu-id="b4c20-105">4208</span></span>|  
|<span data-ttu-id="b4c20-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b4c20-106">Keywords</span></span>|<span data-ttu-id="b4c20-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="b4c20-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="b4c20-108">Livello</span><span class="sxs-lookup"><span data-stu-id="b4c20-108">Level</span></span>|<span data-ttu-id="b4c20-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="b4c20-109">Information</span></span>|  
|<span data-ttu-id="b4c20-110">Canale</span><span class="sxs-lookup"><span data-stu-id="b4c20-110">Channel</span></span>|<span data-ttu-id="b4c20-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b4c20-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b4c20-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b4c20-112">Description</span></span>  
 <span data-ttu-id="b4c20-113">Indica che il provider SQL ripete un comando SQL a causa di un errore SQL.</span><span class="sxs-lookup"><span data-stu-id="b4c20-113">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b4c20-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="b4c20-114">Message</span></span>  
 <span data-ttu-id="b4c20-115">Nuovo tentativo di esecuzione di un comando SQL in seguito a un errore SQL numero %1.</span><span class="sxs-lookup"><span data-stu-id="b4c20-115">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b4c20-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b4c20-116">Details</span></span>  
  
|<span data-ttu-id="b4c20-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="b4c20-117">Data Item Name</span></span>|<span data-ttu-id="b4c20-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="b4c20-118">Data Item Type</span></span>|<span data-ttu-id="b4c20-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b4c20-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b4c20-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="b4c20-120">ErrorNumber</span></span>|<span data-ttu-id="b4c20-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="b4c20-121">xs:string</span></span>|<span data-ttu-id="b4c20-122">Numero di errore SQL.</span><span class="sxs-lookup"><span data-stu-id="b4c20-122">The SQL error number.</span></span>|  
|<span data-ttu-id="b4c20-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b4c20-123">AppDomain</span></span>|<span data-ttu-id="b4c20-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="b4c20-124">xs:string</span></span>|<span data-ttu-id="b4c20-125">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b4c20-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
