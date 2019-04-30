---
title: 1005 - WorkflowApplicationIdled
ms.date: 03/30/2017
ms.assetid: 74d77dfa-f20d-4fe9-a6ae-e6d1b5fe4182
ms.openlocfilehash: 6bbd12e8025b6a127dbfec8e5d3690825c188c4d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008603"
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="2b906-102">1005 - WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="2b906-102">1005 - WorkflowApplicationIdled</span></span>
## <a name="properties"></a><span data-ttu-id="2b906-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="2b906-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2b906-104">Id</span><span class="sxs-lookup"><span data-stu-id="2b906-104">ID</span></span>|<span data-ttu-id="2b906-105">1005</span><span class="sxs-lookup"><span data-stu-id="2b906-105">1005</span></span>|  
|<span data-ttu-id="2b906-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2b906-106">Keywords</span></span>|<span data-ttu-id="2b906-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2b906-107">WFRuntime</span></span>|  
|<span data-ttu-id="2b906-108">Livello</span><span class="sxs-lookup"><span data-stu-id="2b906-108">Level</span></span>|<span data-ttu-id="2b906-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="2b906-109">Information</span></span>|  
|<span data-ttu-id="2b906-110">Canale</span><span class="sxs-lookup"><span data-stu-id="2b906-110">Channel</span></span>|<span data-ttu-id="2b906-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2b906-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2b906-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b906-112">Description</span></span>  
 <span data-ttu-id="2b906-113">Indica che un'applicazione flusso di lavoro è diventata inattiva.</span><span class="sxs-lookup"><span data-stu-id="2b906-113">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2b906-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="2b906-114">Message</span></span>  
 <span data-ttu-id="2b906-115">WorkflowApplication con ID: '%1' inattiva.</span><span class="sxs-lookup"><span data-stu-id="2b906-115">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2b906-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="2b906-116">Details</span></span>  
  
|<span data-ttu-id="2b906-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="2b906-117">Data Item Name</span></span>|<span data-ttu-id="2b906-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="2b906-118">Data Item Type</span></span>|<span data-ttu-id="2b906-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b906-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2b906-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="2b906-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="2b906-121">ID applicazione flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="2b906-121">The workflow application id</span></span>|  
|<span data-ttu-id="2b906-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2b906-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="2b906-123">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2b906-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
