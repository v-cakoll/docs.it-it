---
title: 301 - UserDefinedErrorOccurred
ms.date: 03/30/2017
ms.assetid: a0285d1c-550f-4c14-9c36-a96e97f1c4e4
ms.openlocfilehash: 6eb80d6f0b20af9aae6e7de5248323088e352b26
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61596479"
---
# <a name="301---userdefinederroroccurred"></a><span data-ttu-id="2c7e4-102">301 - UserDefinedErrorOccurred</span><span class="sxs-lookup"><span data-stu-id="2c7e4-102">301 - UserDefinedErrorOccurred</span></span>
## <a name="properties"></a><span data-ttu-id="2c7e4-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="2c7e4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2c7e4-104">Id</span><span class="sxs-lookup"><span data-stu-id="2c7e4-104">ID</span></span>|<span data-ttu-id="2c7e4-105">301</span><span class="sxs-lookup"><span data-stu-id="2c7e4-105">301</span></span>|  
|<span data-ttu-id="2c7e4-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2c7e4-106">Keywords</span></span>|<span data-ttu-id="2c7e4-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="2c7e4-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="2c7e4-108">Livello</span><span class="sxs-lookup"><span data-stu-id="2c7e4-108">Level</span></span>|<span data-ttu-id="2c7e4-109">Error</span><span class="sxs-lookup"><span data-stu-id="2c7e4-109">Error</span></span>|  
|<span data-ttu-id="2c7e4-110">Canale</span><span class="sxs-lookup"><span data-stu-id="2c7e4-110">Channel</span></span>|<span data-ttu-id="2c7e4-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="2c7e4-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2c7e4-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c7e4-112">Description</span></span>  
 <span data-ttu-id="2c7e4-113">Questo evento viene generato dal codice utente.</span><span class="sxs-lookup"><span data-stu-id="2c7e4-113">This event is emitted from user code.</span></span> <span data-ttu-id="2c7e4-114">Gli sviluppatori possono generare questo evento nel caso in cui si verifichi un errore definito dal cliente nel servizio.</span><span class="sxs-lookup"><span data-stu-id="2c7e4-114">Developers can emit this event when a custom-defined error occurs in their service.</span></span> <span data-ttu-id="2c7e4-115">A tale scopo utilizzare le interfacce API <xref:System.Diagnostics.Eventing>.</span><span class="sxs-lookup"><span data-stu-id="2c7e4-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="2c7e4-116">È inoltre disponibile un esempio WCF che esegue il wrapping dell'interfaccia API e illustra come generare correttamente questo evento.</span><span class="sxs-lookup"><span data-stu-id="2c7e4-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2c7e4-117">Messaggio</span><span class="sxs-lookup"><span data-stu-id="2c7e4-117">Message</span></span>  
 <span data-ttu-id="2c7e4-118">Nome:'%1', riferimento:'%2', payload:%3</span><span class="sxs-lookup"><span data-stu-id="2c7e4-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="2c7e4-119">Dettagli</span><span class="sxs-lookup"><span data-stu-id="2c7e4-119">Details</span></span>  
  
|<span data-ttu-id="2c7e4-120">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="2c7e4-120">Data Item Name</span></span>|<span data-ttu-id="2c7e4-121">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="2c7e4-121">Data Item Type</span></span>|<span data-ttu-id="2c7e4-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c7e4-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2c7e4-123">Nome</span><span class="sxs-lookup"><span data-stu-id="2c7e4-123">Name</span></span>|`xs:string`|<span data-ttu-id="2c7e4-124">Nome dell'evento definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="2c7e4-124">The user-defined name of the event.</span></span>|  
|<span data-ttu-id="2c7e4-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="2c7e4-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="2c7e4-126">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="2c7e4-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="2c7e4-127">Il formato viene definito come ' percorso virtuale dell'applicazione nome sito Web&#124;percorso virtuale del servizio&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="2c7e4-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="2c7e4-128">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="2c7e4-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="2c7e4-129">Payload</span><span class="sxs-lookup"><span data-stu-id="2c7e4-129">Payload</span></span>|`xs:string`|<span data-ttu-id="2c7e4-130">Payload dell'evento definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="2c7e4-130">The user-defined payload of the event.</span></span>|
