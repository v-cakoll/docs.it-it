---
title: Metodo IXCLRDataProcess::EndEnumModules
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EndEnumModules Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EndEnumModules Method
helpviewer.keywords:
- IXCLRDataProcess::EndEnumModules Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 50ad55674360d7b880af3ddf701cf17005f30ce7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722738"
---
# <a name="ixclrdataprocessendenummodules-method"></a><span data-ttu-id="67a35-102">Metodo IXCLRDataProcess::EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="67a35-102">IXCLRDataProcess::EndEnumModules Method</span></span>

<span data-ttu-id="67a35-103">Rilascia le risorse usate dagli iteratori interni utilizzati durante l'enumerazione di modulo.</span><span class="sxs-lookup"><span data-stu-id="67a35-103">Releases the resources used by internal iterators used during module enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="67a35-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="67a35-104">Syntax</span></span>
```
HRESULT EndEnumModules(
    [in] CLRDATA_ENUM handle
);
```

### <a name="parameters"></a><span data-ttu-id="67a35-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="67a35-105">Parameters</span></span>
<span data-ttu-id="67a35-106">`handle` [out] Handle per l'enumerazione dei moduli.</span><span class="sxs-lookup"><span data-stu-id="67a35-106">`handle` [out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="67a35-107">Note</span><span class="sxs-lookup"><span data-stu-id="67a35-107">Remarks</span></span>

<span data-ttu-id="67a35-108">Il metodo specificato fa parte di `IXCLRDataProcess` interfaccia e corrisponde al 26 slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="67a35-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="67a35-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="67a35-109">Requirements</span></span>

<span data-ttu-id="67a35-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67a35-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="67a35-111">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="67a35-111">**Header:** None</span></span>   
<span data-ttu-id="67a35-112">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="67a35-112">**Library:** None</span></span>   
<span data-ttu-id="67a35-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="67a35-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>   

## <a name="see-also"></a><span data-ttu-id="67a35-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67a35-114">See also</span></span>

- [<span data-ttu-id="67a35-115">Debug</span><span class="sxs-lookup"><span data-stu-id="67a35-115">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="67a35-116">IXCLRDataProcess Interface</span><span class="sxs-lookup"><span data-stu-id="67a35-116">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
