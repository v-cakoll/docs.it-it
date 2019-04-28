---
title: 208 - MessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: dfb5f7b0-4346-4949-8104-351726b1f502
ms.openlocfilehash: 3499131fcb52f0a0ab6d0e78e165522b7092612f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781901"
---
# <a name="208---messageinspectorafterreceiveinvoked"></a><span data-ttu-id="ddf40-102">208 - MessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="ddf40-102">208 - MessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="ddf40-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ddf40-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ddf40-104">Id</span><span class="sxs-lookup"><span data-stu-id="ddf40-104">ID</span></span>|<span data-ttu-id="ddf40-105">208</span><span class="sxs-lookup"><span data-stu-id="ddf40-105">208</span></span>|  
|<span data-ttu-id="ddf40-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ddf40-106">Keywords</span></span>|<span data-ttu-id="ddf40-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ddf40-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="ddf40-108">Livello</span><span class="sxs-lookup"><span data-stu-id="ddf40-108">Level</span></span>|<span data-ttu-id="ddf40-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="ddf40-109">Information</span></span>|  
|<span data-ttu-id="ddf40-110">Canale</span><span class="sxs-lookup"><span data-stu-id="ddf40-110">Channel</span></span>|<span data-ttu-id="ddf40-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="ddf40-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ddf40-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ddf40-112">Description</span></span>  
 <span data-ttu-id="ddf40-113">Questo evento viene generato dopo che il modello di servizi ha richiamato il metodo `AfterReceive` su un controllo dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="ddf40-113">This event is emitted after the Service Model has invoked the `AfterReceive` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ddf40-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="ddf40-114">Message</span></span>  
 <span data-ttu-id="ddf40-115">'AfterReceiveReply' richiamato dal dispatcher in un elemento MessageInspector di tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="ddf40-115">The Dispatcher invoked 'AfterReceiveReply' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ddf40-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ddf40-116">Details</span></span>  
  
|<span data-ttu-id="ddf40-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="ddf40-117">Data Item Name</span></span>|<span data-ttu-id="ddf40-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="ddf40-118">Data Item Type</span></span>|<span data-ttu-id="ddf40-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ddf40-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ddf40-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="ddf40-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="ddf40-121">Nome completo CLR del tipo dell'elemento `MessageInspector` richiamato.</span><span class="sxs-lookup"><span data-stu-id="ddf40-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="ddf40-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="ddf40-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="ddf40-123">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="ddf40-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="ddf40-124">Il formato viene definito come ' percorso virtuale dell'applicazione nome sito Web&#124;percorso virtuale del servizio&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="ddf40-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="ddf40-125">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="ddf40-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="ddf40-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ddf40-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="ddf40-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ddf40-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
