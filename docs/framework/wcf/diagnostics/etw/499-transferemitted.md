---
title: 499 - TransferEmitted
ms.date: 03/30/2017
ms.assetid: 07a26434-a7a0-40fc-b5d0-3520a04328ae
ms.openlocfilehash: b1ade828ee6519288165e272e7d9f36fd6aca9ff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33469508"
---
# <a name="499---transferemitted"></a><span data-ttu-id="23bff-102">499 - TransferEmitted</span><span class="sxs-lookup"><span data-stu-id="23bff-102">499 - TransferEmitted</span></span>
## <a name="properties"></a><span data-ttu-id="23bff-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="23bff-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="23bff-104">Id</span><span class="sxs-lookup"><span data-stu-id="23bff-104">ID</span></span>|<span data-ttu-id="23bff-105">499</span><span class="sxs-lookup"><span data-stu-id="23bff-105">499</span></span>|  
|<span data-ttu-id="23bff-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="23bff-106">Keywords</span></span>|<span data-ttu-id="23bff-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span><span class="sxs-lookup"><span data-stu-id="23bff-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span></span>|  
|<span data-ttu-id="23bff-108">Livello</span><span class="sxs-lookup"><span data-stu-id="23bff-108">Level</span></span>|<span data-ttu-id="23bff-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="23bff-109">LogAlways</span></span>|  
|<span data-ttu-id="23bff-110">Canale</span><span class="sxs-lookup"><span data-stu-id="23bff-110">Channel</span></span>|<span data-ttu-id="23bff-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="23bff-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="23bff-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23bff-112">Description</span></span>  
 <span data-ttu-id="23bff-113">Questo evento viene generato quando si verifica l'evento di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="23bff-113">This event is emitted when the transfer event takes place.</span></span>  
  
## <a name="message"></a><span data-ttu-id="23bff-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="23bff-114">Message</span></span>  
 <span data-ttu-id="23bff-115">Emissione evento di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="23bff-115">Transfer event emitted.</span></span>  
  
## <a name="details"></a><span data-ttu-id="23bff-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="23bff-116">Details</span></span>  
  
|<span data-ttu-id="23bff-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="23bff-117">Data Item Name</span></span>|<span data-ttu-id="23bff-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="23bff-118">Data Item Type</span></span>|<span data-ttu-id="23bff-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23bff-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="23bff-120">HostReference</span><span class="sxs-lookup"><span data-stu-id="23bff-120">HostReference</span></span>|`xs:string`|<span data-ttu-id="23bff-121">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="23bff-121">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="23bff-122">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso&#124;percorso virtuale servizio&#124;nomeservizio '.</span><span class="sxs-lookup"><span data-stu-id="23bff-122">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="23bff-123">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="23bff-123">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="23bff-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="23bff-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="23bff-125">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="23bff-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
