---
title: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
ms.date: 03/30/2017
ms.topic: reference
api_name:
- Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
api_location:
- Microsoft.VisualStudio.Activities.dll
api_type:
- Assembly
ms.assetid: 6b44b13c-7a23-4df2-8f9f-45e2b1430002
ms.openlocfilehash: 99f2eb9447bdf43cb57cfe86f35d2c09044ed470
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "69947624"
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a><span data-ttu-id="e223d-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span><span class="sxs-lookup"><span data-stu-id="e223d-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span></span>
<span data-ttu-id="e223d-103">Crea un'istanza della classe [Microsoft. VisualStudio. Activities. ASR. ClientActivityBuilder](microsoft-visualstudio-activities-asr-clientactivitybuilder.md) .</span><span class="sxs-lookup"><span data-stu-id="e223d-103">Creates an instance of the [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](microsoft-visualstudio-activities-asr-clientactivitybuilder.md) class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e223d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e223d-104">Syntax</span></span>  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e223d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e223d-105">Parameters</span></span>  
  
## <a name="parameter-values"></a><span data-ttu-id="e223d-106">Valori di parametri</span><span class="sxs-lookup"><span data-stu-id="e223d-106">Parameter Values</span></span>  
 <span data-ttu-id="e223d-107">*operationDescription*</span><span class="sxs-lookup"><span data-stu-id="e223d-107">*operationDescription*</span></span>  
  
 <span data-ttu-id="e223d-108">Descrive l'operazione da eseguire nell'attività del flusso di lavoro che deve essere generata, includendo il nome dell'operazione, il tipo restituito e le informazioni sul parametro.</span><span class="sxs-lookup"><span data-stu-id="e223d-108">Describes the operation to be performed in the workflow activity that is to be generated, including the operation name, return type, and parameter information.</span></span> <span data-ttu-id="e223d-109">Il valore di questo parametro non deve essere **null**.</span><span class="sxs-lookup"><span data-stu-id="e223d-109">The value of this parameter must not be **null**.</span></span> <span data-ttu-id="e223d-110">Dovrebbe descrivere un'operazione sincrona che utilizza un contratto di messaggio e accetta un argomento con un messaggio.</span><span class="sxs-lookup"><span data-stu-id="e223d-110">It should describe a synchronous operation which uses a message contract and takes an argument with one message.</span></span> <span data-ttu-id="e223d-111">Se queste condizioni non vengono soddisfatte, il risultato runtime dell'utilizzo del costruttore e gli altri metodi di questa classe non vengono definiti.</span><span class="sxs-lookup"><span data-stu-id="e223d-111">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="e223d-112">*configurationName*</span><span class="sxs-lookup"><span data-stu-id="e223d-112">*configurationName*</span></span>  
  
 <span data-ttu-id="e223d-113">Specifica il nome della configurazione dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="e223d-113">Specifies the endpoint configuration name.</span></span> <span data-ttu-id="e223d-114">Il valore di questo parametro non deve essere **null** o vuoto.</span><span class="sxs-lookup"><span data-stu-id="e223d-114">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="e223d-115">Se queste condizioni non vengono soddisfatte, il risultato runtime dell'utilizzo del costruttore e gli altri metodi di questa classe non vengono definiti.</span><span class="sxs-lookup"><span data-stu-id="e223d-115">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="e223d-116">*proxyNamespace*</span><span class="sxs-lookup"><span data-stu-id="e223d-116">*proxyNamespace*</span></span>  
  
 <span data-ttu-id="e223d-117">Specifica lo spazio dei nomi del servizio per l'operazione.</span><span class="sxs-lookup"><span data-stu-id="e223d-117">Specifies the service namespace for the operation.</span></span> <span data-ttu-id="e223d-118">Il valore di questo parametro non deve essere **null** o vuoto.</span><span class="sxs-lookup"><span data-stu-id="e223d-118">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="e223d-119">Se queste condizioni non vengono soddisfatte, il risultato runtime dell'utilizzo del costruttore e gli altri metodi di questa classe non vengono definiti.</span><span class="sxs-lookup"><span data-stu-id="e223d-119">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e223d-120">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="e223d-120">See also</span></span>

- [<span data-ttu-id="e223d-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span><span class="sxs-lookup"><span data-stu-id="e223d-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span></span>](microsoft-visualstudio-activities-asr-clientactivitybuilder.md)
