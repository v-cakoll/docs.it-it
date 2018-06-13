---
title: 203 - ClientParameterInspectorAfterCallInvoked
ms.date: 03/30/2017
ms.assetid: b9592212-07e2-43e0-8b00-affd195cf55a
ms.openlocfilehash: 57192b44a0c3babc77fcca13ad4a1433b85bfdd7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458621"
---
# <a name="203---clientparameterinspectoraftercallinvoked"></a><span data-ttu-id="34023-102">203 - ClientParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="34023-102">203 - ClientParameterInspectorAfterCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="34023-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="34023-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="34023-104">ID</span><span class="sxs-lookup"><span data-stu-id="34023-104">ID</span></span>|<span data-ttu-id="34023-105">203</span><span class="sxs-lookup"><span data-stu-id="34023-105">203</span></span>|  
|<span data-ttu-id="34023-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="34023-106">Keywords</span></span>|<span data-ttu-id="34023-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="34023-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="34023-108">Livello</span><span class="sxs-lookup"><span data-stu-id="34023-108">Level</span></span>|<span data-ttu-id="34023-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="34023-109">Information</span></span>|  
|<span data-ttu-id="34023-110">Canale</span><span class="sxs-lookup"><span data-stu-id="34023-110">Channel</span></span>|<span data-ttu-id="34023-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="34023-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="34023-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34023-112">Description</span></span>  
 <span data-ttu-id="34023-113">Questo evento viene generato dopo che il modello di servizi ha richiamato il metodo `AfterCall` su un controllo dei parametri client.</span><span class="sxs-lookup"><span data-stu-id="34023-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="34023-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="34023-114">Message</span></span>  
 <span data-ttu-id="34023-115">'AfterCall' richiamato dal dispatcher in un elemento ClientParameterInspector di tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="34023-115">The Dispatcher invoked 'AfterCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="34023-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="34023-116">Details</span></span>  
  
|<span data-ttu-id="34023-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="34023-117">Data Item Name</span></span>|<span data-ttu-id="34023-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="34023-118">Data Item Type</span></span>|<span data-ttu-id="34023-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34023-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="34023-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="34023-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="34023-121">Nome completo CLR del tipo di controllo richiamato.</span><span class="sxs-lookup"><span data-stu-id="34023-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="34023-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="34023-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="34023-123">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="34023-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="34023-124">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso&#124;percorso virtuale servizio&#124;nomeservizio '.</span><span class="sxs-lookup"><span data-stu-id="34023-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="34023-125">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="34023-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="34023-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="34023-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="34023-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="34023-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
