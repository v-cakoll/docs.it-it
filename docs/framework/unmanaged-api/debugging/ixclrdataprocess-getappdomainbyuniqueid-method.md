---
title: IXCLRDataProcess::GetAppDomainByUniqueId Method
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::GetAppDomainByUniqueId Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::GetAppDomainByUniqueId Method
helpviewer.keywords:
- IXCLRDataProcess::GetAppDomainByUniqueId Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 83e7d4e1a4ff3c2e6f573d6c097c7cdb9c5f3c54
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416700"
---
# <a name="ixclrdataprocessgetappdomainbyuniqueid-method"></a><span data-ttu-id="64962-102">IXCLRDataProcess::GetAppDomainByUniqueId Method</span><span class="sxs-lookup"><span data-stu-id="64962-102">IXCLRDataProcess::GetAppDomainByUniqueId Method</span></span>

<span data-ttu-id="64962-103">Ottiene un `AppDomain` in un processo in base al relativo identificatore univoco.</span><span class="sxs-lookup"><span data-stu-id="64962-103">Gets an `AppDomain` in a process based on its unique identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="64962-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="64962-104">Syntax</span></span>
```
HRESULT GetAppDomainByUniqueID(
    [in] ULONG64               id,
    [out] IXCLRDataAppDomain **appDomain
);
```

### <a name="parameters"></a><span data-ttu-id="64962-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="64962-105">Parameters</span></span>
<span data-ttu-id="64962-106">`id` [in] L'identificatore univoco del dominio applicazione</span><span class="sxs-lookup"><span data-stu-id="64962-106">`id` [in] The unique identifier of the AppDomain</span></span>

<span data-ttu-id="64962-107">`appDomain` [out] Dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="64962-107">`appDomain` [out] The AppDomain</span></span>

## <a name="remarks"></a><span data-ttu-id="64962-108">Note</span><span class="sxs-lookup"><span data-stu-id="64962-108">Remarks</span></span>

<span data-ttu-id="64962-109">Il metodo specificato fa parte di `IXCLRDataProcess` interfaccia e corrisponde al 20 ° slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="64962-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="64962-110">Il `IXCLRDataAppDomain*` restituito viene usato per l'interazione con altre API.</span><span class="sxs-lookup"><span data-stu-id="64962-110">The `IXCLRDataAppDomain*` returned is used for interaction with other APIs.</span></span>

## <a name="requirements"></a><span data-ttu-id="64962-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="64962-111">Requirements</span></span>
<span data-ttu-id="64962-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64962-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="64962-113">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="64962-113">**Header:** None</span></span>  
<span data-ttu-id="64962-114">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="64962-114">**Library:** None</span></span>  
<span data-ttu-id="64962-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="64962-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="64962-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64962-116">See Also</span></span>
- [<span data-ttu-id="64962-117">Debug</span><span class="sxs-lookup"><span data-stu-id="64962-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="64962-118">IXCLRDataProcess Interface</span><span class="sxs-lookup"><span data-stu-id="64962-118">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
