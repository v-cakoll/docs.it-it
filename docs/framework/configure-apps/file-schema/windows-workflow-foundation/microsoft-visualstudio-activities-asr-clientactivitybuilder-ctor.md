---
title: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
api_name: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
api_location: Microsoft.VisualStudio.Activities.dll
api_type: Assembly
ms.assetid: 6b44b13c-7a23-4df2-8f9f-45e2b1430002
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4c50d9754b71386e6809d46cd9666987a704fbf7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a><span data-ttu-id="f53fb-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span><span class="sxs-lookup"><span data-stu-id="f53fb-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span></span>
<span data-ttu-id="f53fb-103">Crea un'istanza di [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) classe.</span><span class="sxs-lookup"><span data-stu-id="f53fb-103">Creates an instance of the [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f53fb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f53fb-104">Syntax</span></span>  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f53fb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f53fb-105">Parameters</span></span>  
  
## <a name="parameter-values"></a><span data-ttu-id="f53fb-106">Valori parametro</span><span class="sxs-lookup"><span data-stu-id="f53fb-106">Parameter Values</span></span>  
 <span data-ttu-id="f53fb-107">*operationDescription*</span><span class="sxs-lookup"><span data-stu-id="f53fb-107">*operationDescription*</span></span>  
  
 <span data-ttu-id="f53fb-108">Descrive l'operazione da eseguire nell'attività del flusso di lavoro che deve essere generata, includendo il nome dell'operazione, il tipo restituito e le informazioni sul parametro.</span><span class="sxs-lookup"><span data-stu-id="f53fb-108">Describes the operation to be performed in the workflow activity that is to be generated, including the operation name, return type, and parameter information.</span></span> <span data-ttu-id="f53fb-109">Il valore di questo parametro non deve essere **null**.</span><span class="sxs-lookup"><span data-stu-id="f53fb-109">The value of this parameter must not be **null**.</span></span> <span data-ttu-id="f53fb-110">Dovrebbe descrivere un'operazione sincrona che utilizza un contratto di messaggio e accetta un argomento con un messaggio.</span><span class="sxs-lookup"><span data-stu-id="f53fb-110">It should describe a synchronous operation which uses a message contract and takes an argument with one message.</span></span> <span data-ttu-id="f53fb-111">Se queste condizioni non vengono soddisfatte, il risultato runtime dell'utilizzo del costruttore e gli altri metodi di questa classe non vengono definiti.</span><span class="sxs-lookup"><span data-stu-id="f53fb-111">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="f53fb-112">*configurationName*</span><span class="sxs-lookup"><span data-stu-id="f53fb-112">*configurationName*</span></span>  
  
 <span data-ttu-id="f53fb-113">Specifica il nome della configurazione dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="f53fb-113">Specifies the endpoint configuration name.</span></span> <span data-ttu-id="f53fb-114">Il valore di questo parametro non deve essere **null** o vuoto.</span><span class="sxs-lookup"><span data-stu-id="f53fb-114">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="f53fb-115">Se queste condizioni non vengono soddisfatte, il risultato runtime dell'utilizzo del costruttore e gli altri metodi di questa classe non vengono definiti.</span><span class="sxs-lookup"><span data-stu-id="f53fb-115">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="f53fb-116">*proxyNamespace*</span><span class="sxs-lookup"><span data-stu-id="f53fb-116">*proxyNamespace*</span></span>  
  
 <span data-ttu-id="f53fb-117">Specifica lo spazio dei nomi del servizio per l'operazione.</span><span class="sxs-lookup"><span data-stu-id="f53fb-117">Specifies the service namespace for the operation.</span></span> <span data-ttu-id="f53fb-118">Il valore di questo parametro non deve essere **null** o vuoto.</span><span class="sxs-lookup"><span data-stu-id="f53fb-118">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="f53fb-119">Se queste condizioni non vengono soddisfatte, il risultato runtime dell'utilizzo del costruttore e gli altri metodi di questa classe non vengono definiti.</span><span class="sxs-lookup"><span data-stu-id="f53fb-119">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f53fb-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f53fb-120">See Also</span></span>  
 [<span data-ttu-id="f53fb-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span><span class="sxs-lookup"><span data-stu-id="f53fb-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)
