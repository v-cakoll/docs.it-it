---
title: 204 - ClientParameterInspectorBeforeCallInvoked
ms.date: 03/30/2017
ms.assetid: 8253555a-9002-4565-8ede-33d7a33a895f
ms.openlocfilehash: eb060cfa79b75452deae67705126a24b7ca9ffef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458585"
---
# <a name="204---clientparameterinspectorbeforecallinvoked"></a><span data-ttu-id="a469a-102">204 - ClientParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="a469a-102">204 - ClientParameterInspectorBeforeCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="a469a-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="a469a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a469a-104">Id</span><span class="sxs-lookup"><span data-stu-id="a469a-104">ID</span></span>|<span data-ttu-id="a469a-105">204</span><span class="sxs-lookup"><span data-stu-id="a469a-105">204</span></span>|  
|<span data-ttu-id="a469a-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a469a-106">Keywords</span></span>|<span data-ttu-id="a469a-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a469a-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="a469a-108">Livello</span><span class="sxs-lookup"><span data-stu-id="a469a-108">Level</span></span>|<span data-ttu-id="a469a-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="a469a-109">Information</span></span>|  
|<span data-ttu-id="a469a-110">Canale</span><span class="sxs-lookup"><span data-stu-id="a469a-110">Channel</span></span>|<span data-ttu-id="a469a-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="a469a-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a469a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a469a-112">Description</span></span>  
 <span data-ttu-id="a469a-113">Questo evento viene generato dopo che il modello di servizi ha richiamato il metodo `BeforeCall` su un controllo dei parametri client.</span><span class="sxs-lookup"><span data-stu-id="a469a-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a469a-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="a469a-114">Message</span></span>  
 <span data-ttu-id="a469a-115">'BeforeCall' richiamato dal dispatcher in un elemento ClientParameterInspector di tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="a469a-115">The Dispatcher invoked 'BeforeCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a469a-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a469a-116">Details</span></span>  
  
|<span data-ttu-id="a469a-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="a469a-117">Data Item Name</span></span>|<span data-ttu-id="a469a-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="a469a-118">Data Item Type</span></span>|<span data-ttu-id="a469a-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a469a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a469a-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="a469a-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="a469a-121">Nome completo CLR del tipo di controllo richiamato.</span><span class="sxs-lookup"><span data-stu-id="a469a-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="a469a-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="a469a-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="a469a-123">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="a469a-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="a469a-124">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso&#124;percorso virtuale servizio&#124;nomeservizio '.</span><span class="sxs-lookup"><span data-stu-id="a469a-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="a469a-125">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="a469a-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="a469a-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a469a-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a469a-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a469a-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
