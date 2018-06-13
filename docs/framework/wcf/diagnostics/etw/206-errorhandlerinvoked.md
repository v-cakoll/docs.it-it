---
title: 206 - ErrorHandlerInvoked
ms.date: 03/30/2017
ms.assetid: 97340f4d-4e09-4e42-a17a-982b3868dbcf
ms.openlocfilehash: 40a92d77c57728249569a854eab8767ff371bca2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458819"
---
# <a name="206---errorhandlerinvoked"></a><span data-ttu-id="e00da-102">206 - ErrorHandlerInvoked</span><span class="sxs-lookup"><span data-stu-id="e00da-102">206 - ErrorHandlerInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="e00da-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="e00da-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e00da-104">Id</span><span class="sxs-lookup"><span data-stu-id="e00da-104">ID</span></span>|<span data-ttu-id="e00da-105">206</span><span class="sxs-lookup"><span data-stu-id="e00da-105">206</span></span>|  
|<span data-ttu-id="e00da-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="e00da-106">Keywords</span></span>|<span data-ttu-id="e00da-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e00da-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="e00da-108">Livello</span><span class="sxs-lookup"><span data-stu-id="e00da-108">Level</span></span>|<span data-ttu-id="e00da-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="e00da-109">Information</span></span>|  
|<span data-ttu-id="e00da-110">Canale</span><span class="sxs-lookup"><span data-stu-id="e00da-110">Channel</span></span>|<span data-ttu-id="e00da-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="e00da-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e00da-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e00da-112">Description</span></span>  
 <span data-ttu-id="e00da-113">Questo evento viene generato dopo che un `ErrorHandler` ha avuto la possibilità di gestire un'eccezione verificatasi in un'operazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="e00da-113">This event is emitted after an `ErrorHandler` has had an opportunity to handle an exception that occurred in a service operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e00da-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="e00da-114">Message</span></span>  
 <span data-ttu-id="e00da-115">Il Dispatcher ha richiamato ErrorHandler di tipo '%1' con un'eccezione di tipo '%3'.</span><span class="sxs-lookup"><span data-stu-id="e00da-115">The Dispatcher invoked an ErrorHandler of type '%1' with an exception of type '%3'.</span></span> <span data-ttu-id="e00da-116">ErrorHandled == '%2'.</span><span class="sxs-lookup"><span data-stu-id="e00da-116">ErrorHandled == '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e00da-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e00da-117">Details</span></span>  
  
|<span data-ttu-id="e00da-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="e00da-118">Data Item Name</span></span>|<span data-ttu-id="e00da-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="e00da-119">Data Item Type</span></span>|<span data-ttu-id="e00da-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e00da-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e00da-121">TypeName</span><span class="sxs-lookup"><span data-stu-id="e00da-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="e00da-122">Nome completo CLR del tipo dell'elemento `ErrorHandler` richiamato.</span><span class="sxs-lookup"><span data-stu-id="e00da-122">The CLR FullName of the type of the invoked `ErrorHandler`.</span></span>|  
|<span data-ttu-id="e00da-123">Handled</span><span class="sxs-lookup"><span data-stu-id="e00da-123">Handled</span></span>|`xs:unsignedByte`|<span data-ttu-id="e00da-124">`true` se l'errore è stato gestito. In caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="e00da-124">`true` if the error handler handled the error, otherwise `false`.</span></span>|  
|<span data-ttu-id="e00da-125">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="e00da-125">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="e00da-126">Nome completo CLR dell'eccezione gestita.</span><span class="sxs-lookup"><span data-stu-id="e00da-126">The CLR FullName of the exception that was being handled.</span></span>|  
|<span data-ttu-id="e00da-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="e00da-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="e00da-128">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="e00da-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="e00da-129">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso&#124;percorso virtuale servizio&#124;nomeservizio '.</span><span class="sxs-lookup"><span data-stu-id="e00da-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="e00da-130">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="e00da-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="e00da-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e00da-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="e00da-132">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e00da-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
