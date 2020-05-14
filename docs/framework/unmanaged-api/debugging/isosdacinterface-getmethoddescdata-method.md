---
title: 'Metodo ISOSDacInterface:: GetMethodDescData'
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
ms.openlocfilehash: e4c44379d9db0f5e98f3ca66ec0486961ec2df3a
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396940"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a><span data-ttu-id="11fb9-102">Metodo ISOSDacInterface:: GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="11fb9-102">ISOSDacInterface::GetMethodDescData Method</span></span>

<span data-ttu-id="11fb9-103">Ottiene i dati per il puntatore MethodDesc specificato.</span><span class="sxs-lookup"><span data-stu-id="11fb9-103">Gets the data for the given MethodDesc pointer.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="11fb9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="11fb9-104">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="11fb9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="11fb9-105">Parameters</span></span>

`methodDesc`\
<span data-ttu-id="11fb9-106">in Indirizzo di MethodDesc.</span><span class="sxs-lookup"><span data-stu-id="11fb9-106">[in] The address of the MethodDesc.</span></span>

`ip`\
<span data-ttu-id="11fb9-107">in Indirizzo IP del metodo.</span><span class="sxs-lookup"><span data-stu-id="11fb9-107">[in] The IP address of the method.</span></span>

`data`\
<span data-ttu-id="11fb9-108">out Dati associati a MethodDesc restituiti dalle API interne.</span><span class="sxs-lookup"><span data-stu-id="11fb9-108">[out] The data associated with the MethodDesc as returned from the internal APIs.</span></span>

`cRevertedRejitVersions`\
<span data-ttu-id="11fb9-109">out Numero di versioni di ReJIT ripristinate.</span><span class="sxs-lookup"><span data-stu-id="11fb9-109">[out] The number of reverted rejit versions.</span></span>

`rgRevertedRejitData`\
<span data-ttu-id="11fb9-110">out I dati associati alle versioni ReJIT ripristinate restituite dalle API interne.</span><span class="sxs-lookup"><span data-stu-id="11fb9-110">[out] The data associated with the reverted rejit versions as returned from the internal APIs.</span></span>

`pcNeededRevertedRejitData`\
<span data-ttu-id="11fb9-111">out Numero di byte necessari per archiviare i dati associati alle versioni di ReJit ripristinate.</span><span class="sxs-lookup"><span data-stu-id="11fb9-111">[out] The number of bytes required to store the data associated with the reverted ReJit versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="11fb9-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="11fb9-112">Remarks</span></span>

<span data-ttu-id="11fb9-113">Il metodo fornito fa parte dell' `ISOSDacInterface` interfaccia e corrisponde al ventunesimo slot della tabella del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="11fb9-113">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 21st slot of the virtual method table.</span></span> <span data-ttu-id="11fb9-114">Per poterli utilizzare, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) è necessario definire come Unsigned Integer a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="11fb9-114">To be able to use them, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) must be defined as a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="11fb9-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="11fb9-115">Requirements</span></span>

<span data-ttu-id="11fb9-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11fb9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="11fb9-117">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="11fb9-117">**Header:** None</span></span>  
<span data-ttu-id="11fb9-118">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="11fb9-118">**Library:** None</span></span>  
<span data-ttu-id="11fb9-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="11fb9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="11fb9-120">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="11fb9-120">See also</span></span>

- [<span data-ttu-id="11fb9-121">Debug</span><span class="sxs-lookup"><span data-stu-id="11fb9-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="11fb9-122">Interfaccia ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="11fb9-122">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
