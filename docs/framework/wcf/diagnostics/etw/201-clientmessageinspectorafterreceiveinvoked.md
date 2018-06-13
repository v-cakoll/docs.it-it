---
title: 201 - ClientMessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: 9ff637f1-cc26-4400-ab9b-546f70e5057d
ms.openlocfilehash: 96ca318c141d49e2ac5594d5ee101658a2aa8f21
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459024"
---
# <a name="201---clientmessageinspectorafterreceiveinvoked"></a><span data-ttu-id="0e5a3-102">201 - ClientMessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="0e5a3-102">201 - ClientMessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="0e5a3-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="0e5a3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0e5a3-104">Id</span><span class="sxs-lookup"><span data-stu-id="0e5a3-104">ID</span></span>|<span data-ttu-id="0e5a3-105">201</span><span class="sxs-lookup"><span data-stu-id="0e5a3-105">201</span></span>|  
|<span data-ttu-id="0e5a3-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0e5a3-106">Keywords</span></span>|<span data-ttu-id="0e5a3-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0e5a3-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="0e5a3-108">Livello</span><span class="sxs-lookup"><span data-stu-id="0e5a3-108">Level</span></span>|<span data-ttu-id="0e5a3-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="0e5a3-109">Information</span></span>|  
|<span data-ttu-id="0e5a3-110">Canale</span><span class="sxs-lookup"><span data-stu-id="0e5a3-110">Channel</span></span>|<span data-ttu-id="0e5a3-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="0e5a3-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0e5a3-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e5a3-112">Description</span></span>  
 <span data-ttu-id="0e5a3-113">Questo evento viene generato dopo che il modello di servizi ha richiamato il metodo `AfterReceiveReply` su un controllo dei messaggi client.</span><span class="sxs-lookup"><span data-stu-id="0e5a3-113">This event is emitted after the Service Model has invoked the `AfterReceiveReply` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0e5a3-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="0e5a3-114">Message</span></span>  
 <span data-ttu-id="0e5a3-115">'AfterReceiveReply' richiamato dal dispatcher in un elemento ClientMessageInspector di tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="0e5a3-115">The Dispatcher invoked 'AfterReceiveReply' on a ClientMessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0e5a3-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0e5a3-116">Details</span></span>  
  
|<span data-ttu-id="0e5a3-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="0e5a3-117">Data Item Name</span></span>|<span data-ttu-id="0e5a3-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="0e5a3-118">Data Item Type</span></span>|<span data-ttu-id="0e5a3-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e5a3-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0e5a3-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="0e5a3-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="0e5a3-121">Nome completo CLR del tipo di controllo richiamato.</span><span class="sxs-lookup"><span data-stu-id="0e5a3-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="0e5a3-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="0e5a3-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="0e5a3-123">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="0e5a3-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="0e5a3-124">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso&#124;percorso virtuale servizio&#124;nomeservizio '.</span><span class="sxs-lookup"><span data-stu-id="0e5a3-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="0e5a3-125">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="0e5a3-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="0e5a3-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0e5a3-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="0e5a3-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0e5a3-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
