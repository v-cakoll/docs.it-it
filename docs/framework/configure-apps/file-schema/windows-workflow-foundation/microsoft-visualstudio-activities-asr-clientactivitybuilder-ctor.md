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
ms.openlocfilehash: b63f8917d7af21c165a16bd45a83e774bcec6e1c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54551605"
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a><span data-ttu-id="ac2e2-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span><span class="sxs-lookup"><span data-stu-id="ac2e2-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span></span>
<span data-ttu-id="ac2e2-103">Crea un'istanza di [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) classe.</span><span class="sxs-lookup"><span data-stu-id="ac2e2-103">Creates an instance of the [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac2e2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ac2e2-104">Syntax</span></span>  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac2e2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ac2e2-105">Parameters</span></span>  
  
## <a name="parameter-values"></a><span data-ttu-id="ac2e2-106">Valori parametro</span><span class="sxs-lookup"><span data-stu-id="ac2e2-106">Parameter Values</span></span>  
 <span data-ttu-id="ac2e2-107">*operationDescription*</span><span class="sxs-lookup"><span data-stu-id="ac2e2-107">*operationDescription*</span></span>  
  
 <span data-ttu-id="ac2e2-108">Descrive l'operazione da eseguire nell'attività del flusso di lavoro che deve essere generata, includendo il nome dell'operazione, il tipo restituito e le informazioni sul parametro.</span><span class="sxs-lookup"><span data-stu-id="ac2e2-108">Describes the operation to be performed in the workflow activity that is to be generated, including the operation name, return type, and parameter information.</span></span> <span data-ttu-id="ac2e2-109">Il valore di questo parametro non deve essere **null**.</span><span class="sxs-lookup"><span data-stu-id="ac2e2-109">The value of this parameter must not be **null**.</span></span> <span data-ttu-id="ac2e2-110">Dovrebbe descrivere un'operazione sincrona che utilizza un contratto di messaggio e accetta un argomento con un messaggio.</span><span class="sxs-lookup"><span data-stu-id="ac2e2-110">It should describe a synchronous operation which uses a message contract and takes an argument with one message.</span></span> <span data-ttu-id="ac2e2-111">Se queste condizioni non vengono soddisfatte, il risultato runtime dell'utilizzo del costruttore e gli altri metodi di questa classe non vengono definiti.</span><span class="sxs-lookup"><span data-stu-id="ac2e2-111">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="ac2e2-112">*configurationName*</span><span class="sxs-lookup"><span data-stu-id="ac2e2-112">*configurationName*</span></span>  
  
 <span data-ttu-id="ac2e2-113">Specifica il nome della configurazione dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="ac2e2-113">Specifies the endpoint configuration name.</span></span> <span data-ttu-id="ac2e2-114">Il valore di questo parametro non deve essere uno **null** o vuoto.</span><span class="sxs-lookup"><span data-stu-id="ac2e2-114">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="ac2e2-115">Se queste condizioni non vengono soddisfatte, il risultato runtime dell'utilizzo del costruttore e gli altri metodi di questa classe non vengono definiti.</span><span class="sxs-lookup"><span data-stu-id="ac2e2-115">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="ac2e2-116">*proxyNamespace*</span><span class="sxs-lookup"><span data-stu-id="ac2e2-116">*proxyNamespace*</span></span>  
  
 <span data-ttu-id="ac2e2-117">Specifica lo spazio dei nomi del servizio per l'operazione.</span><span class="sxs-lookup"><span data-stu-id="ac2e2-117">Specifies the service namespace for the operation.</span></span> <span data-ttu-id="ac2e2-118">Il valore di questo parametro non deve essere uno **null** o vuoto.</span><span class="sxs-lookup"><span data-stu-id="ac2e2-118">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="ac2e2-119">Se queste condizioni non vengono soddisfatte, il risultato runtime dell'utilizzo del costruttore e gli altri metodi di questa classe non vengono definiti.</span><span class="sxs-lookup"><span data-stu-id="ac2e2-119">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac2e2-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac2e2-120">See also</span></span>
- [<span data-ttu-id="ac2e2-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span><span class="sxs-lookup"><span data-stu-id="ac2e2-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)
