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
ms.openlocfilehash: d623fe862eaf5902fd89d0e512dd07f73a03246f
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860813"
---
# <a name="dacpmethoddescdata-structure"></a><span data-ttu-id="7b763-102">Struttura DacpMethodDescData</span><span class="sxs-lookup"><span data-stu-id="7b763-102">DacpMethodDescData Structure</span></span>

<span data-ttu-id="7b763-103">Definisce un buffer di trasporto per le informazioni di runtime di un metodo.</span><span class="sxs-lookup"><span data-stu-id="7b763-103">Defines a transport buffer for a method's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="7b763-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7b763-104">Syntax</span></span>

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

## <a name="members"></a><span data-ttu-id="7b763-105">Members</span><span class="sxs-lookup"><span data-stu-id="7b763-105">Members</span></span>

| <span data-ttu-id="7b763-106">Membro</span><span class="sxs-lookup"><span data-stu-id="7b763-106">Member</span></span>                       | <span data-ttu-id="7b763-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7b763-107">Description</span></span>                                                                                     |
| ---------------------------- | ----------------------------------------------------------------------------------------------- |
| `bHasNativeCode`             | <span data-ttu-id="7b763-108">Indica se il runtime dispone di codice nativo disponibile per l'istanza specificata del metodo.</span><span class="sxs-lookup"><span data-stu-id="7b763-108">Indicates if the runtime has native code available for the given instantiation of the method.</span></span> |
| `bIsDynamic`                 | <span data-ttu-id="7b763-109">Indica se il metodo viene generato in modo dinamico tramite la generazione di codice Lightweight.</span><span class="sxs-lookup"><span data-stu-id="7b763-109">Indicates if the method is generated dynamically through lightweight code generation.</span></span>           |
| `wSlotNumber`                | <span data-ttu-id="7b763-110">Numero di slot del metodo nella tabella dei metodi.</span><span class="sxs-lookup"><span data-stu-id="7b763-110">The method's slot number in the method table.</span></span>                                                   |
| `NativeCodeAddr`             | <span data-ttu-id="7b763-111">Indirizzo nativo iniziale del metodo.</span><span class="sxs-lookup"><span data-stu-id="7b763-111">The method's initial native address.</span></span>                                                            |
| `data`                       | <span data-ttu-id="7b763-112">Puntatore a un buffer usato internamente dal runtime.</span><span class="sxs-lookup"><span data-stu-id="7b763-112">Pointer to a buffer used internally by the runtime.</span></span>                                             |
| `MethodDescPtr`              | <span data-ttu-id="7b763-113">Puntatore a `MethodDesc` in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7b763-113">Pointer to the `MethodDesc` in the runtime.</span></span>                                                     |
| `nativeCodeInfo`             | <span data-ttu-id="7b763-114">Puntatore a un buffer usato internamente dal runtime per tenere traccia dei metodi.</span><span class="sxs-lookup"><span data-stu-id="7b763-114">Pointer to a buffer used internally by the runtime to track methods.</span></span>                            |
| `moduleInfo`                 | <span data-ttu-id="7b763-115">Puntatore a un buffer usato internamente dal runtime per le informazioni sul modulo.</span><span class="sxs-lookup"><span data-stu-id="7b763-115">Pointer to a buffer used internally by the runtime for module information.</span></span>                      |
| `MDToken`                    | <span data-ttu-id="7b763-116">Token associato al metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="7b763-116">Token associated with the given method.</span></span>                                                         |
| `payloadGC`                  | <span data-ttu-id="7b763-117">Puntatore a un buffer di Garbage Collection usato internamente dal runtime.</span><span class="sxs-lookup"><span data-stu-id="7b763-117">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `payloadGC2`                 | <span data-ttu-id="7b763-118">Puntatore a un buffer di Garbage Collection usato internamente dal runtime.</span><span class="sxs-lookup"><span data-stu-id="7b763-118">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `managedDynamicMethodObject` | <span data-ttu-id="7b763-119">Se il metodo è dinamico, il runtime usa questo buffer internamente per il rilevamento delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="7b763-119">If the method is dynamic, the runtime uses this buffer internally for information tracking.</span></span>     |
| `requestedIP`                | <span data-ttu-id="7b763-120">Utilizzato per popolare la struttura per ogni richiesta quando viene fornito un indirizzo di codice nativo.</span><span class="sxs-lookup"><span data-stu-id="7b763-120">Used to populate the structure per request when given a native code address.</span></span>                    |
| `rejitDataCurrent`           | <span data-ttu-id="7b763-121">Informazioni sull'ultima versione instrumentata del metodo.</span><span class="sxs-lookup"><span data-stu-id="7b763-121">Information about the latest instrumented version of the method.</span></span>                                   |
| `rejitDataRequested`         | <span data-ttu-id="7b763-122">ReJIT informazioni per l'indirizzo nativo richiesto.</span><span class="sxs-lookup"><span data-stu-id="7b763-122">Rejit information for the requested native address.</span></span>                                             |
| `cJittedRejitVersions`       | <span data-ttu-id="7b763-123">Numero di volte in cui il metodo è stato rejitted attraverso la strumentazione.</span><span class="sxs-lookup"><span data-stu-id="7b763-123">Number of times the method has been rejitted through instrumentation.</span></span>                           |

## <a name="remarks"></a><span data-ttu-id="7b763-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7b763-124">Remarks</span></span>

<span data-ttu-id="7b763-125">Questa struttura si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="7b763-125">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="7b763-126">Per usarlo, definire la struttura come specificato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="7b763-126">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="7b763-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7b763-127">Requirements</span></span>
<span data-ttu-id="7b763-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b763-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="7b763-129">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="7b763-129">**Header:** None</span></span>  
<span data-ttu-id="7b763-130">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="7b763-130">**Library:** None</span></span>  
<span data-ttu-id="7b763-131">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7b763-131">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="7b763-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b763-132">See also</span></span>

- [<span data-ttu-id="7b763-133">Debug</span><span class="sxs-lookup"><span data-stu-id="7b763-133">Debugging</span></span>](index.md)
- [<span data-ttu-id="7b763-134">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="7b763-134">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="7b763-135">Tipi di dati comuni</span><span class="sxs-lookup"><span data-stu-id="7b763-135">Common Data Types</span></span>](../common-data-types-unmanaged-api-reference.md)
