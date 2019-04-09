---
title: Struttura DacpMethodDescData
ms.date: 02/01/2019
api.name:
- DacpMethodDescData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpMethodDescData Structure
helpviewer.keywords:
- DacpMethodDescData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 567dc3942f79b6bfd29338b9103083aa64e66451
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203197"
---
# <a name="dacpmethoddescdata-structure"></a><span data-ttu-id="ba6d1-102">Struttura DacpMethodDescData</span><span class="sxs-lookup"><span data-stu-id="ba6d1-102">DacpMethodDescData Structure</span></span>

<span data-ttu-id="ba6d1-103">Definisce un buffer di trasporto per le informazioni di runtime del metodo.</span><span class="sxs-lookup"><span data-stu-id="ba6d1-103">Defines a transport buffer for a method's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="ba6d1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ba6d1-104">Syntax</span></span>

```
struct DacpMethodDescData
{
    int             bHasNativeCode;
    int             bIsDynamic;
    unsigned short  wSlotNumber;
    CLRDATA_ADDRESS NativeCodeAddr;
    CLRDATA_ADDRESS data;
    CLRDATA_ADDRESS MethodDescPtr;
    CLRDATA_ADDRESS nativeCodeInfo;
    CLRDATA_ADDRESS moduleInfo;
    mdToken         MDToken;
    CLRDATA_ADDRESS payloadGC;
    CLRDATA_ADDRESS payloadGC2;
    CLRDATA_ADDRESS managedDynamicMethodObject;
    CLRDATA_ADDRESS requestedIP;
    DacpReJitData   rejitDataCurrent;
    DacpReJitData   rejitDataRequested;
    unsigned long   cJittedRejitVersions;
};
```

## <a name="members"></a><span data-ttu-id="ba6d1-105">Membri</span><span class="sxs-lookup"><span data-stu-id="ba6d1-105">Members</span></span>

| <span data-ttu-id="ba6d1-106">Member</span><span class="sxs-lookup"><span data-stu-id="ba6d1-106">Member</span></span>                       | <span data-ttu-id="ba6d1-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba6d1-107">Description</span></span>                                                                                     |
| ---------------------------- | ----------------------------------------------------------------------------------------------- |
| `bHasNativeCode`             | <span data-ttu-id="ba6d1-108">Indica se il runtime dispone di codice nativo disponibile per la creazione dell'istanza specificata del metodo.</span><span class="sxs-lookup"><span data-stu-id="ba6d1-108">Indicates if the runtime has native code available for the given instantiation of the method.</span></span> |
| `bIsDynamic`                 | <span data-ttu-id="ba6d1-109">Indica se il metodo viene generato in modo dinamico tramite la generazione di codice leggero.</span><span class="sxs-lookup"><span data-stu-id="ba6d1-109">Indicates if the method is generated dynamically through lightweight code generation.</span></span>           |
| `wSlotNumber`                | <span data-ttu-id="ba6d1-110">Numero di slot del metodo nella tabella di metodo.</span><span class="sxs-lookup"><span data-stu-id="ba6d1-110">The method's slot number in the method table.</span></span>                                                   |
| `NativeCodeAddr`             | <span data-ttu-id="ba6d1-111">Indirizzo nativo iniziale del metodo.</span><span class="sxs-lookup"><span data-stu-id="ba6d1-111">The method's initial native address.</span></span>                                                            |
| `data`                       | <span data-ttu-id="ba6d1-112">Puntatore a un buffer utilizzato internamente dal runtime.</span><span class="sxs-lookup"><span data-stu-id="ba6d1-112">Pointer to a buffer used internally by the runtime.</span></span>                                             |
| `MethodDescPtr`              | <span data-ttu-id="ba6d1-113">Puntatore al `MethodDesc` in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ba6d1-113">Pointer to the `MethodDesc` in the runtime.</span></span>                                                     |
| `nativeCodeInfo`             | <span data-ttu-id="ba6d1-114">Puntatore a un buffer utilizzato internamente dal runtime per tenere traccia di metodi.</span><span class="sxs-lookup"><span data-stu-id="ba6d1-114">Pointer to a buffer used internally by the runtime to track methods.</span></span>                            |
| `moduleInfo`                 | <span data-ttu-id="ba6d1-115">Puntatore a un buffer utilizzato internamente dal runtime per informazioni sul modulo.</span><span class="sxs-lookup"><span data-stu-id="ba6d1-115">Pointer to a buffer used internally by the runtime for module information.</span></span>                      |
| `MDToken`                    | <span data-ttu-id="ba6d1-116">Token associato al metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="ba6d1-116">Token associated with the given method.</span></span>                                                         |
| `payloadGC`                  | <span data-ttu-id="ba6d1-117">Puntatore a un buffer di raccolta garbage utilizzato internamente dal runtime.</span><span class="sxs-lookup"><span data-stu-id="ba6d1-117">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `payloadGC2`                 | <span data-ttu-id="ba6d1-118">Puntatore a un buffer di raccolta garbage utilizzato internamente dal runtime.</span><span class="sxs-lookup"><span data-stu-id="ba6d1-118">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `managedDynamicMethodObject` | <span data-ttu-id="ba6d1-119">Se il metodo dinamico, il runtime Usa internamente il buffer per le informazioni di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="ba6d1-119">If the method is dynamic, the runtime uses this buffer internally for information tracking.</span></span>     |
| `requestedIP`                | <span data-ttu-id="ba6d1-120">Utilizzato per popolare la struttura per ogni richiesta quando viene specificato un indirizzo di codice nativo.</span><span class="sxs-lookup"><span data-stu-id="ba6d1-120">Used to populate the structure per request when given a native code address.</span></span>                    |
| `rejitDataCurrent`           | <span data-ttu-id="ba6d1-121">Informazioni sull'ultima versione instrumentata del metodo.</span><span class="sxs-lookup"><span data-stu-id="ba6d1-121">Information about the latest instrumented version of the method.</span></span>                                   |
| `rejitDataRequested`         | <span data-ttu-id="ba6d1-122">ReJIT informazioni per l'indirizzo native richiesto.</span><span class="sxs-lookup"><span data-stu-id="ba6d1-122">Rejit information for the requested native address.</span></span>                                             |
| `cJittedRejitVersions`       | <span data-ttu-id="ba6d1-123">Numero di volte in cui che il metodo è stato rejitted tramite la strumentazione.</span><span class="sxs-lookup"><span data-stu-id="ba6d1-123">Number of times the method has been rejitted through instrumentation.</span></span>                           |

## <a name="remarks"></a><span data-ttu-id="ba6d1-124">Note</span><span class="sxs-lookup"><span data-stu-id="ba6d1-124">Remarks</span></span>

<span data-ttu-id="ba6d1-125">Questa struttura si trova all'interno del runtime e non viene esposto tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="ba6d1-125">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="ba6d1-126">Per usarlo, definire la struttura come specificato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="ba6d1-126">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="ba6d1-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ba6d1-127">Requirements</span></span>
<span data-ttu-id="ba6d1-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba6d1-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="ba6d1-129">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="ba6d1-129">**Header:** None</span></span>  
<span data-ttu-id="ba6d1-130">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="ba6d1-130">**Library:** None</span></span>  
**<span data-ttu-id="ba6d1-131">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ba6d1-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a><span data-ttu-id="ba6d1-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba6d1-132">See also</span></span>

- [<span data-ttu-id="ba6d1-133">Debug</span><span class="sxs-lookup"><span data-stu-id="ba6d1-133">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="ba6d1-134">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="ba6d1-134">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="ba6d1-135">Tipi di dati comuni</span><span class="sxs-lookup"><span data-stu-id="ba6d1-135">Common Data Types</span></span>](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)
