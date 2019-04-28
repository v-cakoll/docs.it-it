---
title: 207 - FaultProviderInvoked
ms.date: 03/30/2017
ms.assetid: b730d903-01c2-4deb-85a4-da12f8a21fe4
ms.openlocfilehash: 9f97e74e7685d57b487f456625826ee9cd8e1760
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781914"
---
# <a name="207---faultproviderinvoked"></a><span data-ttu-id="db9cc-102">207 - FaultProviderInvoked</span><span class="sxs-lookup"><span data-stu-id="db9cc-102">207 - FaultProviderInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="db9cc-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="db9cc-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="db9cc-104">Id</span><span class="sxs-lookup"><span data-stu-id="db9cc-104">ID</span></span>|<span data-ttu-id="db9cc-105">207</span><span class="sxs-lookup"><span data-stu-id="db9cc-105">207</span></span>|  
|<span data-ttu-id="db9cc-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="db9cc-106">Keywords</span></span>|<span data-ttu-id="db9cc-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="db9cc-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="db9cc-108">Livello</span><span class="sxs-lookup"><span data-stu-id="db9cc-108">Level</span></span>|<span data-ttu-id="db9cc-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="db9cc-109">Information</span></span>|  
|<span data-ttu-id="db9cc-110">Canale</span><span class="sxs-lookup"><span data-stu-id="db9cc-110">Channel</span></span>|<span data-ttu-id="db9cc-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="db9cc-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="db9cc-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db9cc-112">Description</span></span>  
 <span data-ttu-id="db9cc-113">Questo evento viene generato dopo che è stato richiamato un elemento `FaultProvider`.</span><span class="sxs-lookup"><span data-stu-id="db9cc-113">This event is emitted after a `FaultProvider` has been invoked.</span></span>  
  
## <a name="message"></a><span data-ttu-id="db9cc-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="db9cc-114">Message</span></span>  
 <span data-ttu-id="db9cc-115">FaultProvider di tipo '%1' richiamato dal dispatcher con un'eccezione di tipo '%2'.</span><span class="sxs-lookup"><span data-stu-id="db9cc-115">The Dispatcher invoked a FaultProvider of type '%1' with an exception of type '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="db9cc-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="db9cc-116">Details</span></span>  
  
|<span data-ttu-id="db9cc-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="db9cc-117">Data Item Name</span></span>|<span data-ttu-id="db9cc-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="db9cc-118">Data Item Type</span></span>|<span data-ttu-id="db9cc-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db9cc-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="db9cc-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="db9cc-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="db9cc-121">Nome completo CLR del tipo dell'elemento `FaultProvider` richiamato.</span><span class="sxs-lookup"><span data-stu-id="db9cc-121">The CLR FullName of the type of the invoked `FaultProvider`.</span></span>|  
|<span data-ttu-id="db9cc-122">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="db9cc-122">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="db9cc-123">Nome completo CLR dell'eccezione usata da `FaultProvider`.</span><span class="sxs-lookup"><span data-stu-id="db9cc-123">The CLR FullName of the exception that the `FaultProvider` has operated on.</span></span>|  
|<span data-ttu-id="db9cc-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="db9cc-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="db9cc-125">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="db9cc-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="db9cc-126">Il formato viene definito come ' percorso virtuale dell'applicazione nome sito Web&#124;percorso virtuale del servizio&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="db9cc-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="db9cc-127">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="db9cc-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="db9cc-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="db9cc-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="db9cc-129">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="db9cc-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
