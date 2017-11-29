---
title: 499 - TransferEmitted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 07a26434-a7a0-40fc-b5d0-3520a04328ae
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7e786691ef3a6ee2a860461562c9de0f627fc907
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="499---transferemitted"></a><span data-ttu-id="5313c-102">499 - TransferEmitted</span><span class="sxs-lookup"><span data-stu-id="5313c-102">499 - TransferEmitted</span></span>
## <a name="properties"></a><span data-ttu-id="5313c-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="5313c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5313c-104">ID</span><span class="sxs-lookup"><span data-stu-id="5313c-104">ID</span></span>|<span data-ttu-id="5313c-105">499</span><span class="sxs-lookup"><span data-stu-id="5313c-105">499</span></span>|  
|<span data-ttu-id="5313c-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="5313c-106">Keywords</span></span>|<span data-ttu-id="5313c-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span><span class="sxs-lookup"><span data-stu-id="5313c-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span></span>|  
|<span data-ttu-id="5313c-108">Livello</span><span class="sxs-lookup"><span data-stu-id="5313c-108">Level</span></span>|<span data-ttu-id="5313c-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="5313c-109">LogAlways</span></span>|  
|<span data-ttu-id="5313c-110">Canale</span><span class="sxs-lookup"><span data-stu-id="5313c-110">Channel</span></span>|<span data-ttu-id="5313c-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="5313c-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5313c-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5313c-112">Description</span></span>  
 <span data-ttu-id="5313c-113">Questo evento viene generato quando si verifica l'evento di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="5313c-113">This event is emitted when the transfer event takes place.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5313c-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="5313c-114">Message</span></span>  
 <span data-ttu-id="5313c-115">Emissione evento di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="5313c-115">Transfer event emitted.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5313c-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5313c-116">Details</span></span>  
  
|<span data-ttu-id="5313c-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="5313c-117">Data Item Name</span></span>|<span data-ttu-id="5313c-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="5313c-118">Data Item Type</span></span>|<span data-ttu-id="5313c-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5313c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5313c-120">HostReference</span><span class="sxs-lookup"><span data-stu-id="5313c-120">HostReference</span></span>|`xs:string`|<span data-ttu-id="5313c-121">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="5313c-121">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="5313c-122">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="5313c-122">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="5313c-123">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="5313c-123">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="5313c-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5313c-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="5313c-125">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5313c-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
