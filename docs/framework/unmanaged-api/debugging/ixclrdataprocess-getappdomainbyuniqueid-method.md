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
ms.openlocfilehash: cf610e3af26c60dd9bf738bff8785890394d0f34
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710274"
---
# <a name="ixclrdataprocessgetappdomainbyuniqueid-method"></a><span data-ttu-id="9ed3f-102">IXCLRDataProcess::GetAppDomainByUniqueId Method</span><span class="sxs-lookup"><span data-stu-id="9ed3f-102">IXCLRDataProcess::GetAppDomainByUniqueId Method</span></span>

<span data-ttu-id="9ed3f-103">Ottiene un `AppDomain` in un processo in base al relativo identificatore univoco.</span><span class="sxs-lookup"><span data-stu-id="9ed3f-103">Gets an `AppDomain` in a process based on its unique identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9ed3f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9ed3f-104">Syntax</span></span>
```
HRESULT GetAppDomainByUniqueID(
    [in] ULONG64               id,
    [out] IXCLRDataAppDomain **appDomain
);
```

### <a name="parameters"></a><span data-ttu-id="9ed3f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9ed3f-105">Parameters</span></span>
<span data-ttu-id="9ed3f-106">`id` [in] L'identificatore univoco del dominio applicazione</span><span class="sxs-lookup"><span data-stu-id="9ed3f-106">`id` [in] The unique identifier of the AppDomain</span></span>

<span data-ttu-id="9ed3f-107">`appDomain` [out] Dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="9ed3f-107">`appDomain` [out] The AppDomain</span></span>

## <a name="remarks"></a><span data-ttu-id="9ed3f-108">Note</span><span class="sxs-lookup"><span data-stu-id="9ed3f-108">Remarks</span></span>

<span data-ttu-id="9ed3f-109">Il metodo specificato fa parte di `IXCLRDataProcess` interfaccia e corrisponde al 20 ° slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="9ed3f-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="9ed3f-110">Il `IXCLRDataAppDomain*` restituito viene usato per l'interazione con altre API.</span><span class="sxs-lookup"><span data-stu-id="9ed3f-110">The `IXCLRDataAppDomain*` returned is used for interaction with other APIs.</span></span>

## <a name="requirements"></a><span data-ttu-id="9ed3f-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9ed3f-111">Requirements</span></span>
<span data-ttu-id="9ed3f-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ed3f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9ed3f-113">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="9ed3f-113">**Header:** None</span></span>  
<span data-ttu-id="9ed3f-114">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="9ed3f-114">**Library:** None</span></span>  
<span data-ttu-id="9ed3f-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9ed3f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9ed3f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ed3f-116">See also</span></span>
- [<span data-ttu-id="9ed3f-117">Debug</span><span class="sxs-lookup"><span data-stu-id="9ed3f-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="9ed3f-118">IXCLRDataProcess Interface</span><span class="sxs-lookup"><span data-stu-id="9ed3f-118">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
