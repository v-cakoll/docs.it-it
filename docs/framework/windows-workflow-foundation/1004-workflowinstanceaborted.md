---
title: 1004 - WorkflowInstanceAborted
ms.date: 03/30/2017
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
ms.openlocfilehash: d34f6f1ab6af8e06a0f28fb043faf9fe16a8b211
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008616"
---
# <a name="1004---workflowinstanceaborted"></a><span data-ttu-id="06028-102">1004 - WorkflowInstanceAborted</span><span class="sxs-lookup"><span data-stu-id="06028-102">1004 - WorkflowInstanceAborted</span></span>

## <a name="properties"></a><span data-ttu-id="06028-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="06028-103">Properties</span></span>

|||
|-|-|
|<span data-ttu-id="06028-104">Id</span><span class="sxs-lookup"><span data-stu-id="06028-104">ID</span></span>|<span data-ttu-id="06028-105">1004</span><span class="sxs-lookup"><span data-stu-id="06028-105">1004</span></span>|
|<span data-ttu-id="06028-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="06028-106">Keywords</span></span>|<span data-ttu-id="06028-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="06028-107">WFRuntime</span></span>|
|<span data-ttu-id="06028-108">Livello</span><span class="sxs-lookup"><span data-stu-id="06028-108">Level</span></span>|<span data-ttu-id="06028-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="06028-109">Information</span></span>|
|<span data-ttu-id="06028-110">Canale</span><span class="sxs-lookup"><span data-stu-id="06028-110">Channel</span></span>|<span data-ttu-id="06028-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="06028-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|

## <a name="description"></a><span data-ttu-id="06028-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="06028-112">Description</span></span>

<span data-ttu-id="06028-113">Indica che un'istanza del flusso di lavoro è stata interrotta con un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="06028-113">Indicates a workflow instance has aborted with an exception.</span></span>

## <a name="message"></a><span data-ttu-id="06028-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="06028-114">Message</span></span>

<span data-ttu-id="06028-115">WorkflowInstance con ID: '%1' interrotta con un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="06028-115">WorkflowInstance Id: '%1' was aborted with an exception.</span></span>

## <a name="details"></a><span data-ttu-id="06028-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="06028-116">Details</span></span>

|<span data-ttu-id="06028-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="06028-117">Data Item Name</span></span>|<span data-ttu-id="06028-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="06028-118">Data Item Type</span></span>|<span data-ttu-id="06028-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="06028-119">Description</span></span>|
|--------------------|--------------------|-----------------|
|<span data-ttu-id="06028-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="06028-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="06028-121">ID istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="06028-121">The instance id for the workflow</span></span>|
|<span data-ttu-id="06028-122">Eccezione</span><span class="sxs-lookup"><span data-stu-id="06028-122">Exception</span></span>|`xs:string`|<span data-ttu-id="06028-123">Dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="06028-123">The exception details for the exception</span></span>|
|<span data-ttu-id="06028-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="06028-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="06028-125">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="06028-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
