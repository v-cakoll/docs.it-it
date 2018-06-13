---
title: 213 - ServiceHostStarted
ms.date: 03/30/2017
ms.assetid: a6f7facc-342f-46bb-9d52-a470178ba6bb
ms.openlocfilehash: 819efa2e13c94e2c7a16c24f6ba9c7ef2b87ef8c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458474"
---
# <a name="213---servicehoststarted"></a><span data-ttu-id="14885-102">213 - ServiceHostStarted</span><span class="sxs-lookup"><span data-stu-id="14885-102">213 - ServiceHostStarted</span></span>
## <a name="properties"></a><span data-ttu-id="14885-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="14885-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="14885-104">Id</span><span class="sxs-lookup"><span data-stu-id="14885-104">ID</span></span>|<span data-ttu-id="14885-105">213</span><span class="sxs-lookup"><span data-stu-id="14885-105">213</span></span>|  
|<span data-ttu-id="14885-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="14885-106">Keywords</span></span>|<span data-ttu-id="14885-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost</span><span class="sxs-lookup"><span data-stu-id="14885-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost</span></span>|  
|<span data-ttu-id="14885-108">Livello</span><span class="sxs-lookup"><span data-stu-id="14885-108">Level</span></span>|<span data-ttu-id="14885-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="14885-109">LogAlways</span></span>|  
|<span data-ttu-id="14885-110">Canale</span><span class="sxs-lookup"><span data-stu-id="14885-110">Channel</span></span>|<span data-ttu-id="14885-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="14885-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="14885-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="14885-112">Description</span></span>  
 <span data-ttu-id="14885-113">Questo evento viene generato quando viene avviato un host del servizio ospitato su Web.</span><span class="sxs-lookup"><span data-stu-id="14885-113">This event is emitted when a Web-hosted service host is started.</span></span> <span data-ttu-id="14885-114">Ciò si verifica in genere quando il servizio viene attivato da un messaggio,</span><span class="sxs-lookup"><span data-stu-id="14885-114">This typically happens when the service is activated by a message.</span></span> <span data-ttu-id="14885-115">ma anche se viene configurato per essere avviato in modo automatico.</span><span class="sxs-lookup"><span data-stu-id="14885-115">It may also happen if the service is configured to be automatically started.</span></span>  
  
## <a name="message"></a><span data-ttu-id="14885-116">Messaggio</span><span class="sxs-lookup"><span data-stu-id="14885-116">Message</span></span>  
 <span data-ttu-id="14885-117">ServiceHost avviato: '%1'.</span><span class="sxs-lookup"><span data-stu-id="14885-117">ServiceHost started: '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="14885-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="14885-118">Details</span></span>  
  
|<span data-ttu-id="14885-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="14885-119">Data Item Name</span></span>|<span data-ttu-id="14885-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="14885-120">Data Item Type</span></span>|<span data-ttu-id="14885-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="14885-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="14885-122">Nome tipo servizio</span><span class="sxs-lookup"><span data-stu-id="14885-122">Service Type Name</span></span>|`xs:string`|<span data-ttu-id="14885-123">Nome completo CLR del tipo di implementazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="14885-123">The CLR FullName of the type of the service implementation.</span></span>|  
|<span data-ttu-id="14885-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="14885-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="14885-125">Per i servizi ospitati su Web questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="14885-125">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="14885-126">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso&#124;percorso virtuale servizio&#124;nomeservizio '.</span><span class="sxs-lookup"><span data-stu-id="14885-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="14885-127">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="14885-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="14885-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="14885-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="14885-129">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="14885-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
