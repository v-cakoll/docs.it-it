---
title: Metodo IXCLRDataProcess::EndEnumMethodInstancesByAddress
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: a48a7fc9a141354666c50b1f6da8f1aaa180ff6c
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416621"
---
# <a name="ixclrdataprocessendenummethodinstancesbyaddress-method"></a><span data-ttu-id="b2728-102">Metodo IXCLRDataProcess::EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="b2728-102">IXCLRDataProcess::EndEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="b2728-103">Rilascia le risorse usate dagli iteratori interni utilizzati durante l'enumerazione di istanza.</span><span class="sxs-lookup"><span data-stu-id="b2728-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b2728-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b2728-104">Syntax</span></span>

```
HRESULT EndEnumMethodInstancesByAddress(
    [in] CLRDATA_ENUM handle
);
```

### <a name="parameters"></a><span data-ttu-id="b2728-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b2728-105">Parameters</span></span>

<span data-ttu-id="b2728-106">`handle` [out] Handle per l'enumerazione delle istanze di metodo.</span><span class="sxs-lookup"><span data-stu-id="b2728-106">`handle` [out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="b2728-107">Note</span><span class="sxs-lookup"><span data-stu-id="b2728-107">Remarks</span></span>

<span data-ttu-id="b2728-108">Il metodo specificato fa parte di `IXCLRDataProcess` interfaccia e corrisponde al 29 slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="b2728-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 29th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="b2728-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b2728-109">Requirements</span></span>

<span data-ttu-id="b2728-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2728-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b2728-111">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="b2728-111">**Header:** None</span></span>  
<span data-ttu-id="b2728-112">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="b2728-112">**Library:** None</span></span>  
<span data-ttu-id="b2728-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b2728-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b2728-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2728-114">See Also</span></span>

- [<span data-ttu-id="b2728-115">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="b2728-115">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="b2728-116">Debug</span><span class="sxs-lookup"><span data-stu-id="b2728-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="b2728-117">IXCLRDataProcess Interface</span><span class="sxs-lookup"><span data-stu-id="b2728-117">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
