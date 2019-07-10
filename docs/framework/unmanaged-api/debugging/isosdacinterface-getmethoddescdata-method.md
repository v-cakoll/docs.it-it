---
title: Metodo ISOSDacInterface::GetMethodDescData
ms.date: 01/16/2019
api.name:
- ISOSDacInterface::GetMethodDescData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescData Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescData Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: ea54fdd83b9470db4a08daceaa695e450f5ca1af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764817"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a><span data-ttu-id="5a494-102">Metodo ISOSDacInterface::GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="5a494-102">ISOSDacInterface::GetMethodDescData Method</span></span>

<span data-ttu-id="5a494-103">Ottiene i dati per il puntatore MethodDesc specificato.</span><span class="sxs-lookup"><span data-stu-id="5a494-103">Gets the data for the given MethodDesc pointer.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="5a494-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5a494-104">Syntax</span></span>

```cpp
HRESULT GetMethodDescData(
    CLRDATA_ADDRESS            methodDesc,
    CLRDATA_ADDRESS            ip,
    DacpMethodDescData *data,
    ULONG                      cRevertedRejitVersions,
    DacpReJitData      *rgRevertedRejitData,
    void                      *pcNeededRevertedRejitData
);
```

## <a name="parameters"></a><span data-ttu-id="5a494-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5a494-105">Parameters</span></span>

`methodDesc`\
<span data-ttu-id="5a494-106">[in] L'indirizzo del MethodDesc.</span><span class="sxs-lookup"><span data-stu-id="5a494-106">[in] The address of the MethodDesc.</span></span>

`ip`\
<span data-ttu-id="5a494-107">[in] L'indirizzo IP del metodo.</span><span class="sxs-lookup"><span data-stu-id="5a494-107">[in] The IP address of the method.</span></span>

`data`\
<span data-ttu-id="5a494-108">[out] I dati associati con la MethodDesc come restituito dall'API interne.</span><span class="sxs-lookup"><span data-stu-id="5a494-108">[out] The data associated with the MethodDesc as returned from the internal APIs.</span></span>

`cRevertedRejitVersions`\
<span data-ttu-id="5a494-109">[out] Il numero di versioni rejit ripristinato.</span><span class="sxs-lookup"><span data-stu-id="5a494-109">[out] The number of reverted rejit versions.</span></span>

`rgRevertedRejitData`\
<span data-ttu-id="5a494-110">[out] I dati associati con le versioni rejit ripristinato come restituito dall'API interne.</span><span class="sxs-lookup"><span data-stu-id="5a494-110">[out] The data associated with the reverted rejit versions as returned from the internal APIs.</span></span>

`pcNeededRevertedRejitData`\
<span data-ttu-id="5a494-111">[out] Il numero di byte necessari per archiviare i dati associati con le versioni ReJit ripristinate.</span><span class="sxs-lookup"><span data-stu-id="5a494-111">[out] The number of bytes required to store the data associated with the reverted ReJit versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="5a494-112">Note</span><span class="sxs-lookup"><span data-stu-id="5a494-112">Remarks</span></span>

<span data-ttu-id="5a494-113">Il metodo specificato fa parte di `ISOSDacInterface` interfaccia e corrisponde al 20 ° slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="5a494-113">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="5a494-114">Per poter utilizzarli [ `CLRDATA_ADDRESS` ](../common-data-types-unmanaged-api-reference.md) deve essere definito come un intero senza segno a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="5a494-114">To be able to use them, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) must be defined as a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="5a494-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5a494-115">Requirements</span></span>

<span data-ttu-id="5a494-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a494-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="5a494-117">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="5a494-117">**Header:** None</span></span>  
<span data-ttu-id="5a494-118">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="5a494-118">**Library:** None</span></span>  
<span data-ttu-id="5a494-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5a494-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="5a494-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a494-120">See also</span></span>

- [<span data-ttu-id="5a494-121">Debug</span><span class="sxs-lookup"><span data-stu-id="5a494-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="5a494-122">Interfaccia ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="5a494-122">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
