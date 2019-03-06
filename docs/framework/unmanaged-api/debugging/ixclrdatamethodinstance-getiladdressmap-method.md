---
title: Metodo IXCLRDataMethodInstance::GetILAddressMap
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodInstance::GetILAddressMap Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetILAddressMap Method
helpviewer.keywords:
- IXCLRDataMethodInstance::GetILAddressMap Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 5e6fde6e4e5bf006da00b62b035cee112efae1d7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373491"
---
# <a name="ixclrdatamethodinstancegetiladdressmap-method"></a><span data-ttu-id="35e7a-102">Metodo IXCLRDataMethodInstance::GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="35e7a-102">IXCLRDataMethodInstance::GetILAddressMap Method</span></span>

<span data-ttu-id="35e7a-103">Ottiene il livello di integrità per le informazioni di mapping di indirizzi.</span><span class="sxs-lookup"><span data-stu-id="35e7a-103">Gets the IL to address mapping information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="35e7a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="35e7a-104">Syntax</span></span>

```
HRESULT GetILAddressMap(
    [in] ULONG32                                   mapLen,
    [out] ULONG32                                 *mapNeeded,
    [out, size_is(mapLen)] CLRDATA_IL_ADDRESS_MAP  maps[]
);
```

### <a name="parameters"></a><span data-ttu-id="35e7a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="35e7a-105">Parameters</span></span>

`mapLen`\
<span data-ttu-id="35e7a-106">[in] La lunghezza della matrice di mappe fornito.</span><span class="sxs-lookup"><span data-stu-id="35e7a-106">[in] The length of the provided maps array.</span></span>

`mapNeeded`\
<span data-ttu-id="35e7a-107">[out] Il numero di voci della mappa che desideri nel metodo.</span><span class="sxs-lookup"><span data-stu-id="35e7a-107">[out] The number of map entries that the method needs.</span></span>

`maps`\
<span data-ttu-id="35e7a-108">[out, size_is(mapLen)] La matrice per archiviare le voci della mappa.</span><span class="sxs-lookup"><span data-stu-id="35e7a-108">[out, size_is(mapLen)] The array for storing the map entries.</span></span>

## <a name="remarks"></a><span data-ttu-id="35e7a-109">Note</span><span class="sxs-lookup"><span data-stu-id="35e7a-109">Remarks</span></span>

<span data-ttu-id="35e7a-110">Il metodo specificato fa parte di `IXCLRDataMethodInstance` interfaccia e corrisponde al 14 slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="35e7a-110">The provided method is part of the `IXCLRDataMethodInstance` interface and corresponds to the 14th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="35e7a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="35e7a-111">Requirements</span></span>

<span data-ttu-id="35e7a-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35e7a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="35e7a-113">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="35e7a-113">**Header:** None</span></span>  
<span data-ttu-id="35e7a-114">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="35e7a-114">**Library:** None</span></span>  
<span data-ttu-id="35e7a-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="35e7a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="35e7a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35e7a-116">See also</span></span>

- [<span data-ttu-id="35e7a-117">Debug</span><span class="sxs-lookup"><span data-stu-id="35e7a-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="35e7a-118">Interfaccia IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="35e7a-118">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
