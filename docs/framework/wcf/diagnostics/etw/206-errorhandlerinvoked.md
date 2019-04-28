---
title: 206 - ErrorHandlerInvoked
ms.date: 03/30/2017
ms.assetid: 97340f4d-4e09-4e42-a17a-982b3868dbcf
ms.openlocfilehash: 40a92d77c57728249569a854eab8767ff371bca2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781927"
---
# <a name="206---errorhandlerinvoked"></a><span data-ttu-id="3171d-102">206 - ErrorHandlerInvoked</span><span class="sxs-lookup"><span data-stu-id="3171d-102">206 - ErrorHandlerInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="3171d-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="3171d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3171d-104">Id</span><span class="sxs-lookup"><span data-stu-id="3171d-104">ID</span></span>|<span data-ttu-id="3171d-105">206</span><span class="sxs-lookup"><span data-stu-id="3171d-105">206</span></span>|  
|<span data-ttu-id="3171d-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="3171d-106">Keywords</span></span>|<span data-ttu-id="3171d-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3171d-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="3171d-108">Livello</span><span class="sxs-lookup"><span data-stu-id="3171d-108">Level</span></span>|<span data-ttu-id="3171d-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="3171d-109">Information</span></span>|  
|<span data-ttu-id="3171d-110">Canale</span><span class="sxs-lookup"><span data-stu-id="3171d-110">Channel</span></span>|<span data-ttu-id="3171d-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="3171d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3171d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3171d-112">Description</span></span>  
 <span data-ttu-id="3171d-113">Questo evento viene generato dopo che un `ErrorHandler` ha avuto la possibilità di gestire un'eccezione verificatasi in un'operazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="3171d-113">This event is emitted after an `ErrorHandler` has had an opportunity to handle an exception that occurred in a service operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3171d-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="3171d-114">Message</span></span>  
 <span data-ttu-id="3171d-115">ErrorHandler di tipo '%1' con un'eccezione di tipo '%3' richiamato dal Dispatcher.</span><span class="sxs-lookup"><span data-stu-id="3171d-115">The Dispatcher invoked an ErrorHandler of type '%1' with an exception of type '%3'.</span></span> <span data-ttu-id="3171d-116">ErrorHandled == '%2'.</span><span class="sxs-lookup"><span data-stu-id="3171d-116">ErrorHandled == '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3171d-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3171d-117">Details</span></span>  
  
|<span data-ttu-id="3171d-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="3171d-118">Data Item Name</span></span>|<span data-ttu-id="3171d-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="3171d-119">Data Item Type</span></span>|<span data-ttu-id="3171d-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3171d-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3171d-121">TypeName</span><span class="sxs-lookup"><span data-stu-id="3171d-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="3171d-122">Nome completo CLR del tipo dell'elemento `ErrorHandler` richiamato.</span><span class="sxs-lookup"><span data-stu-id="3171d-122">The CLR FullName of the type of the invoked `ErrorHandler`.</span></span>|  
|<span data-ttu-id="3171d-123">Handled</span><span class="sxs-lookup"><span data-stu-id="3171d-123">Handled</span></span>|`xs:unsignedByte`|<span data-ttu-id="3171d-124">`true` se l'errore è stato gestito. In caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="3171d-124">`true` if the error handler handled the error, otherwise `false`.</span></span>|  
|<span data-ttu-id="3171d-125">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="3171d-125">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="3171d-126">Nome completo CLR dell'eccezione gestita.</span><span class="sxs-lookup"><span data-stu-id="3171d-126">The CLR FullName of the exception that was being handled.</span></span>|  
|<span data-ttu-id="3171d-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="3171d-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="3171d-128">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="3171d-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="3171d-129">Il formato viene definito come ' percorso virtuale dell'applicazione nome sito Web&#124;percorso virtuale del servizio&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="3171d-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="3171d-130">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="3171d-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="3171d-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3171d-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="3171d-132">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3171d-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
