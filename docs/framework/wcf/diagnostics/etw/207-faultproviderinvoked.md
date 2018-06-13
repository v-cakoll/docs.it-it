---
title: 207 - FaultProviderInvoked
ms.date: 03/30/2017
ms.assetid: b730d903-01c2-4deb-85a4-da12f8a21fe4
ms.openlocfilehash: 9f97e74e7685d57b487f456625826ee9cd8e1760
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457348"
---
# <a name="207---faultproviderinvoked"></a><span data-ttu-id="ecad8-102">207 - FaultProviderInvoked</span><span class="sxs-lookup"><span data-stu-id="ecad8-102">207 - FaultProviderInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="ecad8-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ecad8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ecad8-104">ID</span><span class="sxs-lookup"><span data-stu-id="ecad8-104">ID</span></span>|<span data-ttu-id="ecad8-105">207</span><span class="sxs-lookup"><span data-stu-id="ecad8-105">207</span></span>|  
|<span data-ttu-id="ecad8-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecad8-106">Keywords</span></span>|<span data-ttu-id="ecad8-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ecad8-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="ecad8-108">Livello</span><span class="sxs-lookup"><span data-stu-id="ecad8-108">Level</span></span>|<span data-ttu-id="ecad8-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="ecad8-109">Information</span></span>|  
|<span data-ttu-id="ecad8-110">Canale</span><span class="sxs-lookup"><span data-stu-id="ecad8-110">Channel</span></span>|<span data-ttu-id="ecad8-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="ecad8-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ecad8-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ecad8-112">Description</span></span>  
 <span data-ttu-id="ecad8-113">Questo evento viene generato dopo che è stato richiamato un elemento `FaultProvider`.</span><span class="sxs-lookup"><span data-stu-id="ecad8-113">This event is emitted after a `FaultProvider` has been invoked.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ecad8-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="ecad8-114">Message</span></span>  
 <span data-ttu-id="ecad8-115">FaultProvider di tipo '%1' richiamato dal dispatcher con un'eccezione di tipo '%2'.</span><span class="sxs-lookup"><span data-stu-id="ecad8-115">The Dispatcher invoked a FaultProvider of type '%1' with an exception of type '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ecad8-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ecad8-116">Details</span></span>  
  
|<span data-ttu-id="ecad8-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="ecad8-117">Data Item Name</span></span>|<span data-ttu-id="ecad8-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="ecad8-118">Data Item Type</span></span>|<span data-ttu-id="ecad8-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ecad8-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ecad8-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="ecad8-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="ecad8-121">Nome completo CLR del tipo dell'elemento `FaultProvider` richiamato.</span><span class="sxs-lookup"><span data-stu-id="ecad8-121">The CLR FullName of the type of the invoked `FaultProvider`.</span></span>|  
|<span data-ttu-id="ecad8-122">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="ecad8-122">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="ecad8-123">Nome completo CLR dell'eccezione usata da `FaultProvider`.</span><span class="sxs-lookup"><span data-stu-id="ecad8-123">The CLR FullName of the exception that the `FaultProvider` has operated on.</span></span>|  
|<span data-ttu-id="ecad8-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="ecad8-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="ecad8-125">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="ecad8-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="ecad8-126">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso&#124;percorso virtuale servizio&#124;nomeservizio '.</span><span class="sxs-lookup"><span data-stu-id="ecad8-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="ecad8-127">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="ecad8-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="ecad8-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ecad8-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="ecad8-129">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ecad8-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
