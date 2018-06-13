---
title: 211 - ParameterInspectorAfterCallInvoked
ms.date: 03/30/2017
ms.assetid: c0e21297-10b8-4456-a0e1-e019145cd5ac
ms.openlocfilehash: ada3ced31def2bb821b975e09f50ad83f28d56bf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459717"
---
# <a name="211---parameterinspectoraftercallinvoked"></a><span data-ttu-id="575ba-102">211 - ParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="575ba-102">211 - ParameterInspectorAfterCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="575ba-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="575ba-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="575ba-104">ID</span><span class="sxs-lookup"><span data-stu-id="575ba-104">ID</span></span>|<span data-ttu-id="575ba-105">211</span><span class="sxs-lookup"><span data-stu-id="575ba-105">211</span></span>|  
|<span data-ttu-id="575ba-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="575ba-106">Keywords</span></span>|<span data-ttu-id="575ba-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="575ba-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="575ba-108">Livello</span><span class="sxs-lookup"><span data-stu-id="575ba-108">Level</span></span>|<span data-ttu-id="575ba-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="575ba-109">Information</span></span>|  
|<span data-ttu-id="575ba-110">Canale</span><span class="sxs-lookup"><span data-stu-id="575ba-110">Channel</span></span>|<span data-ttu-id="575ba-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="575ba-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="575ba-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="575ba-112">Description</span></span>  
 <span data-ttu-id="575ba-113">Questo evento viene generato dopo che il modello di servizi ha richiamato il metodo `AfterCall` su un `ParameterInspector`.</span><span class="sxs-lookup"><span data-stu-id="575ba-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="575ba-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="575ba-114">Message</span></span>  
 <span data-ttu-id="575ba-115">Il dispatcher ha richiamato 'AfterCall' in un ParameterInspector di tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="575ba-115">The Dispatcher invoked 'AfterCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="575ba-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="575ba-116">Details</span></span>  
  
|<span data-ttu-id="575ba-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="575ba-117">Data Item Name</span></span>|<span data-ttu-id="575ba-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="575ba-118">Data Item Type</span></span>|<span data-ttu-id="575ba-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="575ba-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="575ba-120">Nome tipo</span><span class="sxs-lookup"><span data-stu-id="575ba-120">Type Name</span></span>|`xs:string`|<span data-ttu-id="575ba-121">Nome completo CLR del tipo dell'elemento `ParameterInspector` richiamato.</span><span class="sxs-lookup"><span data-stu-id="575ba-121">The CLR FullName of the type of the invoked `ParameterInspector`.</span></span>|  
|<span data-ttu-id="575ba-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="575ba-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="575ba-123">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="575ba-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="575ba-124">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso&#124;percorso virtuale servizio&#124;nomeservizio '.</span><span class="sxs-lookup"><span data-stu-id="575ba-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="575ba-125">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="575ba-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="575ba-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="575ba-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="575ba-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="575ba-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
