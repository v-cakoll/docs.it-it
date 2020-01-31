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
ms.openlocfilehash: cc54664ea8ad61005de3f3fae7407946d1c861b2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793841"
---
# <a name="dacpmethoddescdata-structure"></a><span data-ttu-id="b416c-102">Struttura DacpMethodDescData</span><span class="sxs-lookup"><span data-stu-id="b416c-102">DacpMethodDescData Structure</span></span>

<span data-ttu-id="b416c-103">Definisce un buffer di trasporto per le informazioni di runtime di un metodo.</span><span class="sxs-lookup"><span data-stu-id="b416c-103">Defines a transport buffer for a method's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b416c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b416c-104">Syntax</span></span>

```cpp
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

## <a name="members"></a><span data-ttu-id="b416c-105">Membri</span><span class="sxs-lookup"><span data-stu-id="b416c-105">Members</span></span>

| <span data-ttu-id="b416c-106">Member</span><span class="sxs-lookup"><span data-stu-id="b416c-106">Member</span></span>                       | <span data-ttu-id="b416c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b416c-107">Description</span></span>                                                                                     |
| ---------------------------- | ----------------------------------------------------------------------------------------------- |
| `bHasNativeCode`             | <span data-ttu-id="b416c-108">Indica se il runtime dispone di codice nativo disponibile per l'istanza specificata del metodo.</span><span class="sxs-lookup"><span data-stu-id="b416c-108">Indicates if the runtime has native code available for the given instantiation of the method.</span></span> |
| `bIsDynamic`                 | <span data-ttu-id="b416c-109">Indica se il metodo viene generato in modo dinamico tramite la generazione di codice Lightweight.</span><span class="sxs-lookup"><span data-stu-id="b416c-109">Indicates if the method is generated dynamically through lightweight code generation.</span></span>           |
| `wSlotNumber`                | <span data-ttu-id="b416c-110">Numero di slot del metodo nella tabella dei metodi.</span><span class="sxs-lookup"><span data-stu-id="b416c-110">The method's slot number in the method table.</span></span>                                                   |
| `NativeCodeAddr`             | <span data-ttu-id="b416c-111">Indirizzo nativo iniziale del metodo.</span><span class="sxs-lookup"><span data-stu-id="b416c-111">The method's initial native address.</span></span>                                                            |
| `data`                       | <span data-ttu-id="b416c-112">Puntatore a un buffer usato internamente dal runtime.</span><span class="sxs-lookup"><span data-stu-id="b416c-112">Pointer to a buffer used internally by the runtime.</span></span>                                             |
| `MethodDescPtr`              | <span data-ttu-id="b416c-113">Puntatore al `MethodDesc` nel Runtime.</span><span class="sxs-lookup"><span data-stu-id="b416c-113">Pointer to the `MethodDesc` in the runtime.</span></span>                                                     |
| `nativeCodeInfo`             | <span data-ttu-id="b416c-114">Puntatore a un buffer usato internamente dal runtime per tenere traccia dei metodi.</span><span class="sxs-lookup"><span data-stu-id="b416c-114">Pointer to a buffer used internally by the runtime to track methods.</span></span>                            |
| `moduleInfo`                 | <span data-ttu-id="b416c-115">Puntatore a un buffer usato internamente dal runtime per le informazioni sul modulo.</span><span class="sxs-lookup"><span data-stu-id="b416c-115">Pointer to a buffer used internally by the runtime for module information.</span></span>                      |
| `MDToken`                    | <span data-ttu-id="b416c-116">Token associato al metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="b416c-116">Token associated with the given method.</span></span>                                                         |
| `payloadGC`                  | <span data-ttu-id="b416c-117">Puntatore a un buffer di Garbage Collection usato internamente dal runtime.</span><span class="sxs-lookup"><span data-stu-id="b416c-117">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `payloadGC2`                 | <span data-ttu-id="b416c-118">Puntatore a un buffer di Garbage Collection usato internamente dal runtime.</span><span class="sxs-lookup"><span data-stu-id="b416c-118">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `managedDynamicMethodObject` | <span data-ttu-id="b416c-119">Se il metodo è dinamico, il runtime usa questo buffer internamente per il rilevamento delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="b416c-119">If the method is dynamic, the runtime uses this buffer internally for information tracking.</span></span>     |
| `requestedIP`                | <span data-ttu-id="b416c-120">Utilizzato per popolare la struttura per ogni richiesta quando viene fornito un indirizzo di codice nativo.</span><span class="sxs-lookup"><span data-stu-id="b416c-120">Used to populate the structure per request when given a native code address.</span></span>                    |
| `rejitDataCurrent`           | <span data-ttu-id="b416c-121">Informazioni sull'ultima versione instrumentata del metodo.</span><span class="sxs-lookup"><span data-stu-id="b416c-121">Information about the latest instrumented version of the method.</span></span>                                   |
| `rejitDataRequested`         | <span data-ttu-id="b416c-122">ReJIT informazioni per l'indirizzo nativo richiesto.</span><span class="sxs-lookup"><span data-stu-id="b416c-122">Rejit information for the requested native address.</span></span>                                             |
| `cJittedRejitVersions`       | <span data-ttu-id="b416c-123">Numero di volte in cui il metodo è stato rejitted attraverso la strumentazione.</span><span class="sxs-lookup"><span data-stu-id="b416c-123">Number of times the method has been rejitted through instrumentation.</span></span>                           |

## <a name="remarks"></a><span data-ttu-id="b416c-124">Note</span><span class="sxs-lookup"><span data-stu-id="b416c-124">Remarks</span></span>

<span data-ttu-id="b416c-125">Questa struttura si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="b416c-125">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="b416c-126">Per usarlo, definire la struttura come specificato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b416c-126">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="b416c-127">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="b416c-127">Requirements</span></span>
<span data-ttu-id="b416c-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b416c-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b416c-129">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="b416c-129">**Header:** None</span></span>  
<span data-ttu-id="b416c-130">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="b416c-130">**Library:** None</span></span>  
<span data-ttu-id="b416c-131">**Versioni .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b416c-131">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b416c-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b416c-132">See also</span></span>

- [<span data-ttu-id="b416c-133">Debug</span><span class="sxs-lookup"><span data-stu-id="b416c-133">Debugging</span></span>](index.md)
- [<span data-ttu-id="b416c-134">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="b416c-134">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="b416c-135">Tipi di dati comuni</span><span class="sxs-lookup"><span data-stu-id="b416c-135">Common Data Types</span></span>](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)
