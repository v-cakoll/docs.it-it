---
title: 302 - UserDefinedWarningOccurred
ms.date: 03/30/2017
ms.assetid: 8d1f0bf1-0151-45e6-be92-573d397b54de
ms.openlocfilehash: c70857951309ef54ba460e96e948c9320269d30f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61596752"
---
# <a name="302---userdefinedwarningoccurred"></a><span data-ttu-id="471c7-102">302 - UserDefinedWarningOccurred</span><span class="sxs-lookup"><span data-stu-id="471c7-102">302 - UserDefinedWarningOccurred</span></span>
## <a name="properties"></a><span data-ttu-id="471c7-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="471c7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="471c7-104">Id</span><span class="sxs-lookup"><span data-stu-id="471c7-104">ID</span></span>|<span data-ttu-id="471c7-105">302</span><span class="sxs-lookup"><span data-stu-id="471c7-105">302</span></span>|  
|<span data-ttu-id="471c7-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="471c7-106">Keywords</span></span>|<span data-ttu-id="471c7-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="471c7-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="471c7-108">Livello</span><span class="sxs-lookup"><span data-stu-id="471c7-108">Level</span></span>|<span data-ttu-id="471c7-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="471c7-109">Warning</span></span>|  
|<span data-ttu-id="471c7-110">Canale</span><span class="sxs-lookup"><span data-stu-id="471c7-110">Channel</span></span>|<span data-ttu-id="471c7-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="471c7-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="471c7-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="471c7-112">Description</span></span>  
 <span data-ttu-id="471c7-113">Questo evento viene generato dal codice utente.</span><span class="sxs-lookup"><span data-stu-id="471c7-113">This event is emitted from user code.</span></span> <span data-ttu-id="471c7-114">Gli sviluppatori possono generare questo evento nel caso in cui si verifichi un evento di avviso definito dal cliente nel servizio.</span><span class="sxs-lookup"><span data-stu-id="471c7-114">Developers can emit this event when a custom-defined warning event occurs in their service.</span></span> <span data-ttu-id="471c7-115">A tale scopo utilizzare le interfacce API <xref:System.Diagnostics.Eventing>.</span><span class="sxs-lookup"><span data-stu-id="471c7-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="471c7-116">È inoltre disponibile un esempio WCF che esegue il wrapping dell'interfaccia API e illustra come generare correttamente questo evento.</span><span class="sxs-lookup"><span data-stu-id="471c7-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="471c7-117">Messaggio</span><span class="sxs-lookup"><span data-stu-id="471c7-117">Message</span></span>  
 <span data-ttu-id="471c7-118">Nome:'%1', riferimento:'%2', payload:%3</span><span class="sxs-lookup"><span data-stu-id="471c7-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="471c7-119">Dettagli</span><span class="sxs-lookup"><span data-stu-id="471c7-119">Details</span></span>  
  
|<span data-ttu-id="471c7-120">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="471c7-120">Data Item Name</span></span>|<span data-ttu-id="471c7-121">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="471c7-121">Data Item Type</span></span>|<span data-ttu-id="471c7-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="471c7-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="471c7-123">Nome</span><span class="sxs-lookup"><span data-stu-id="471c7-123">Name</span></span>|`xs:string`|<span data-ttu-id="471c7-124">Nome dell'evento definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="471c7-124">The user-defined name of the event.</span></span>|  
|<span data-ttu-id="471c7-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="471c7-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="471c7-126">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="471c7-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="471c7-127">Il formato viene definito come ' percorso virtuale dell'applicazione nome sito Web&#124;percorso virtuale del servizio&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="471c7-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="471c7-128">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="471c7-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="471c7-129">Payload</span><span class="sxs-lookup"><span data-stu-id="471c7-129">Payload</span></span>|`xs:string`|<span data-ttu-id="471c7-130">Payload dell'evento definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="471c7-130">The user-defined payload of the event.</span></span>|
