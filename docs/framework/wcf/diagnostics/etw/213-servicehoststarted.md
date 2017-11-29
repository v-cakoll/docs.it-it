---
title: 213 - ServiceHostStarted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6f7facc-342f-46bb-9d52-a470178ba6bb
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 61d79adce71be9ef93e9232e01a8cba5f5319f79
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="213---servicehoststarted"></a><span data-ttu-id="ca9a6-102">213 - ServiceHostStarted</span><span class="sxs-lookup"><span data-stu-id="ca9a6-102">213 - ServiceHostStarted</span></span>
## <a name="properties"></a><span data-ttu-id="ca9a6-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ca9a6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ca9a6-104">ID</span><span class="sxs-lookup"><span data-stu-id="ca9a6-104">ID</span></span>|<span data-ttu-id="ca9a6-105">213</span><span class="sxs-lookup"><span data-stu-id="ca9a6-105">213</span></span>|  
|<span data-ttu-id="ca9a6-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ca9a6-106">Keywords</span></span>|<span data-ttu-id="ca9a6-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost</span><span class="sxs-lookup"><span data-stu-id="ca9a6-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost</span></span>|  
|<span data-ttu-id="ca9a6-108">Livello</span><span class="sxs-lookup"><span data-stu-id="ca9a6-108">Level</span></span>|<span data-ttu-id="ca9a6-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="ca9a6-109">LogAlways</span></span>|  
|<span data-ttu-id="ca9a6-110">Canale</span><span class="sxs-lookup"><span data-stu-id="ca9a6-110">Channel</span></span>|<span data-ttu-id="ca9a6-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="ca9a6-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ca9a6-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ca9a6-112">Description</span></span>  
 <span data-ttu-id="ca9a6-113">Questo evento viene generato quando viene avviato un host del servizio ospitato su Web.</span><span class="sxs-lookup"><span data-stu-id="ca9a6-113">This event is emitted when a Web-hosted service host is started.</span></span> <span data-ttu-id="ca9a6-114">Ciò si verifica in genere quando il servizio viene attivato da un messaggio,</span><span class="sxs-lookup"><span data-stu-id="ca9a6-114">This typically happens when the service is activated by a message.</span></span> <span data-ttu-id="ca9a6-115">ma anche se viene configurato per essere avviato in modo automatico.</span><span class="sxs-lookup"><span data-stu-id="ca9a6-115">It may also happen if the service is configured to be automatically started.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ca9a6-116">Messaggio</span><span class="sxs-lookup"><span data-stu-id="ca9a6-116">Message</span></span>  
 <span data-ttu-id="ca9a6-117">ServiceHost avviato: '%1'.</span><span class="sxs-lookup"><span data-stu-id="ca9a6-117">ServiceHost started: '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ca9a6-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ca9a6-118">Details</span></span>  
  
|<span data-ttu-id="ca9a6-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="ca9a6-119">Data Item Name</span></span>|<span data-ttu-id="ca9a6-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="ca9a6-120">Data Item Type</span></span>|<span data-ttu-id="ca9a6-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ca9a6-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ca9a6-122">Nome tipo servizio</span><span class="sxs-lookup"><span data-stu-id="ca9a6-122">Service Type Name</span></span>|`xs:string`|<span data-ttu-id="ca9a6-123">Nome completo CLR del tipo di implementazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="ca9a6-123">The CLR FullName of the type of the service implementation.</span></span>|  
|<span data-ttu-id="ca9a6-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="ca9a6-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="ca9a6-125">Per i servizi ospitati su Web questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="ca9a6-125">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="ca9a6-126">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="ca9a6-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="ca9a6-127">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="ca9a6-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="ca9a6-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ca9a6-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="ca9a6-129">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ca9a6-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
