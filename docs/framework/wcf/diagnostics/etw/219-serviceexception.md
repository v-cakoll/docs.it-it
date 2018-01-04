---
title: 219 - ServiceException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fceff5c748076c75c942f515e2621edff5106f4e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="219---serviceexception"></a><span data-ttu-id="be2b0-102">219 - ServiceException</span><span class="sxs-lookup"><span data-stu-id="be2b0-102">219 - ServiceException</span></span>
## <a name="properties"></a><span data-ttu-id="be2b0-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="be2b0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="be2b0-104">Id</span><span class="sxs-lookup"><span data-stu-id="be2b0-104">ID</span></span>|<span data-ttu-id="be2b0-105">219</span><span class="sxs-lookup"><span data-stu-id="be2b0-105">219</span></span>|  
|<span data-ttu-id="be2b0-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="be2b0-106">Keywords</span></span>|<span data-ttu-id="be2b0-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="be2b0-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="be2b0-108">Livello</span><span class="sxs-lookup"><span data-stu-id="be2b0-108">Level</span></span>|<span data-ttu-id="be2b0-109">Errore</span><span class="sxs-lookup"><span data-stu-id="be2b0-109">Error</span></span>|  
|<span data-ttu-id="be2b0-110">Canale</span><span class="sxs-lookup"><span data-stu-id="be2b0-110">Channel</span></span>|<span data-ttu-id="be2b0-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="be2b0-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="be2b0-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be2b0-112">Description</span></span>  
 <span data-ttu-id="be2b0-113">Questo evento viene generato quando un servizio WCF incontra un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="be2b0-113">This event is emitted when a WCF service encounters an unhandled exception.</span></span> <span data-ttu-id="be2b0-114">Include eccezioni non gestite durante l'attivazione, durante l'elaborazione dei messaggi e nel codice utente.</span><span class="sxs-lookup"><span data-stu-id="be2b0-114">This includes unhandled exceptions during activation, during message processing, and in user code.</span></span>  
  
## <a name="message"></a><span data-ttu-id="be2b0-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="be2b0-115">Message</span></span>  
 <span data-ttu-id="be2b0-116">Riscontrata un'eccezione non gestita di tipo '%2' durante l'elaborazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="be2b0-116">There was an unhandled exception of type '%2' during message processing.</span></span> <span data-ttu-id="be2b0-117">ToString completo dell'eccezione: %1.</span><span class="sxs-lookup"><span data-stu-id="be2b0-117">Full Exception ToString: %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="be2b0-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="be2b0-118">Details</span></span>  
  
|<span data-ttu-id="be2b0-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="be2b0-119">Data Item Name</span></span>|<span data-ttu-id="be2b0-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="be2b0-120">Data Item Type</span></span>|<span data-ttu-id="be2b0-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be2b0-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="be2b0-122">ExceptionToString</span><span class="sxs-lookup"><span data-stu-id="be2b0-122">ExceptionToString</span></span>|`xs:string`|<span data-ttu-id="be2b0-123">Risultato della chiamata di `ToString`() all'eccezione CLR.</span><span class="sxs-lookup"><span data-stu-id="be2b0-123">The result of calling `ToString`() on the CLR exception.</span></span>|  
|<span data-ttu-id="be2b0-124">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="be2b0-124">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="be2b0-125">Nome completo CLR del tipo di eccezione.</span><span class="sxs-lookup"><span data-stu-id="be2b0-125">The CLR FullName of the exception's type.</span></span>|  
|<span data-ttu-id="be2b0-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="be2b0-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="be2b0-127">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="be2b0-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="be2b0-128">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="be2b0-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="be2b0-129">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="be2b0-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="be2b0-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="be2b0-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="be2b0-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="be2b0-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
