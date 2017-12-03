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
ms.openlocfilehash: e8d9e9bfb0967b6c41a3df0015bdd6b4101e0c06
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a><span data-ttu-id="ef6b6-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span><span class="sxs-lookup"><span data-stu-id="ef6b6-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span></span>
<span data-ttu-id="ef6b6-103">Crea un'istanza di [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) classe.</span><span class="sxs-lookup"><span data-stu-id="ef6b6-103">Creates an instance of the [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef6b6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef6b6-104">Syntax</span></span>  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ef6b6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ef6b6-105">Parameters</span></span>  
  
## <a name="parameter-values"></a><span data-ttu-id="ef6b6-106">Valori parametro</span><span class="sxs-lookup"><span data-stu-id="ef6b6-106">Parameter Values</span></span>  
 <span data-ttu-id="ef6b6-107">*operationDescription*</span><span class="sxs-lookup"><span data-stu-id="ef6b6-107">*operationDescription*</span></span>  
  
 <span data-ttu-id="ef6b6-108">Descrive l'operazione da eseguire nell'attività del flusso di lavoro che deve essere generata, includendo il nome dell'operazione, il tipo restituito e le informazioni sul parametro.</span><span class="sxs-lookup"><span data-stu-id="ef6b6-108">Describes the operation to be performed in the workflow activity that is to be generated, including the operation name, return type, and parameter information.</span></span> <span data-ttu-id="ef6b6-109">Il valore di questo parametro non deve essere **null**.</span><span class="sxs-lookup"><span data-stu-id="ef6b6-109">The value of this parameter must not be **null**.</span></span> <span data-ttu-id="ef6b6-110">Dovrebbe descrivere un'operazione sincrona che utilizza un contratto di messaggio e accetta un argomento con un messaggio.</span><span class="sxs-lookup"><span data-stu-id="ef6b6-110">It should describe a synchronous operation which uses a message contract and takes an argument with one message.</span></span> <span data-ttu-id="ef6b6-111">Se queste condizioni non vengono soddisfatte, il risultato runtime dell'utilizzo del costruttore e gli altri metodi di questa classe non vengono definiti.</span><span class="sxs-lookup"><span data-stu-id="ef6b6-111">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="ef6b6-112">*configurationName*</span><span class="sxs-lookup"><span data-stu-id="ef6b6-112">*configurationName*</span></span>  
  
 <span data-ttu-id="ef6b6-113">Specifica il nome della configurazione dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="ef6b6-113">Specifies the endpoint configuration name.</span></span> <span data-ttu-id="ef6b6-114">Il valore di questo parametro non deve essere **null** o vuoto.</span><span class="sxs-lookup"><span data-stu-id="ef6b6-114">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="ef6b6-115">Se queste condizioni non vengono soddisfatte, il risultato runtime dell'utilizzo del costruttore e gli altri metodi di questa classe non vengono definiti.</span><span class="sxs-lookup"><span data-stu-id="ef6b6-115">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="ef6b6-116">*proxyNamespace*</span><span class="sxs-lookup"><span data-stu-id="ef6b6-116">*proxyNamespace*</span></span>  
  
 <span data-ttu-id="ef6b6-117">Specifica lo spazio dei nomi del servizio per l'operazione.</span><span class="sxs-lookup"><span data-stu-id="ef6b6-117">Specifies the service namespace for the operation.</span></span> <span data-ttu-id="ef6b6-118">Il valore di questo parametro non deve essere **null** o vuoto.</span><span class="sxs-lookup"><span data-stu-id="ef6b6-118">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="ef6b6-119">Se queste condizioni non vengono soddisfatte, il risultato runtime dell'utilizzo del costruttore e gli altri metodi di questa classe non vengono definiti.</span><span class="sxs-lookup"><span data-stu-id="ef6b6-119">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef6b6-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef6b6-120">See Also</span></span>  
 [<span data-ttu-id="ef6b6-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span><span class="sxs-lookup"><span data-stu-id="ef6b6-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)
