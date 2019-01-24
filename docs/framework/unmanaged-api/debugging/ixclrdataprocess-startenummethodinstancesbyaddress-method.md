---
title: Metodo IXCLRDataProcess::StartEnumMethodInstancesByAddress
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 9afbf0665b114169661a74b60c744203d160fed3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662621"
---
# <a name="ixclrdataprocessstartenummethodinstancesbyaddress-method"></a><span data-ttu-id="dfb4c-102">Metodo IXCLRDataProcess::StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="dfb4c-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="dfb4c-103">Fornisce un handle per enumerare le istanze di metodo di `AppDomain` iniziando in corrispondenza di un determinato indirizzo.</span><span class="sxs-lookup"><span data-stu-id="dfb4c-103">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="dfb4c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dfb4c-104">Syntax</span></span>

```
HRESULT StartEnumMethodInstancesByAddress(
    [in] CLRDATA_ADDRESS     address,
    [in] IXCLRDataAppDomain *appDomain,
    [out] CLRDATA_ENUM      *handle
);
```

### <a name="parameters"></a><span data-ttu-id="dfb4c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dfb4c-105">Parameters</span></span>

<span data-ttu-id="dfb4c-106">`address` [in] L'indirizzo dell'istanza del primo metodo.</span><span class="sxs-lookup"><span data-stu-id="dfb4c-106">`address` [in] The address of the first method instance.</span></span>

<span data-ttu-id="dfb4c-107">`appDomain` [in] Il dominio di applicazione delle istanze del metodo.</span><span class="sxs-lookup"><span data-stu-id="dfb4c-107">`appDomain` [in] The AppDomain of the method instances.</span></span>

<span data-ttu-id="dfb4c-108">`handle` [out] Handle per l'enumerazione delle istanze di metodo.</span><span class="sxs-lookup"><span data-stu-id="dfb4c-108">`handle` [out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="dfb4c-109">Note</span><span class="sxs-lookup"><span data-stu-id="dfb4c-109">Remarks</span></span>

<span data-ttu-id="dfb4c-110">Il metodo specificato fa parte di `IXCLRDataProcess` interfaccia e corrisponde al 27 slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="dfb4c-110">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 27th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="dfb4c-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dfb4c-111">Requirements</span></span>

<span data-ttu-id="dfb4c-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfb4c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="dfb4c-113">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="dfb4c-113">**Header:** None</span></span>  
<span data-ttu-id="dfb4c-114">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="dfb4c-114">**Library:** None</span></span>  
<span data-ttu-id="dfb4c-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="dfb4c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="dfb4c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dfb4c-116">See also</span></span>

- [<span data-ttu-id="dfb4c-117">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="dfb4c-117">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="dfb4c-118">Debug</span><span class="sxs-lookup"><span data-stu-id="dfb4c-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="dfb4c-119">IXCLRDataProcess Interface</span><span class="sxs-lookup"><span data-stu-id="dfb4c-119">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
