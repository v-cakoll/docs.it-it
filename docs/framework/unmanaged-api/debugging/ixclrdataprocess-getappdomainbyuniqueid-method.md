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
ms.openlocfilehash: 257fa2cf03a62ea888b76519aa5c9f9e84038045
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59126503"
---
# <a name="ixclrdataprocessgetappdomainbyuniqueid-method"></a><span data-ttu-id="681c1-102">IXCLRDataProcess::GetAppDomainByUniqueId Method</span><span class="sxs-lookup"><span data-stu-id="681c1-102">IXCLRDataProcess::GetAppDomainByUniqueId Method</span></span>

<span data-ttu-id="681c1-103">Ottiene un `AppDomain` in un processo in base al relativo identificatore univoco.</span><span class="sxs-lookup"><span data-stu-id="681c1-103">Gets an `AppDomain` in a process based on its unique identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="681c1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="681c1-104">Syntax</span></span>
```
HRESULT GetAppDomainByUniqueID(
    [in] ULONG64               id,
    [out] IXCLRDataAppDomain **appDomain
);
```

## <a name="parameters"></a><span data-ttu-id="681c1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="681c1-105">Parameters</span></span>

`id`\
<span data-ttu-id="681c1-106">[in] L'identificatore univoco del dominio applicazione</span><span class="sxs-lookup"><span data-stu-id="681c1-106">[in] The unique identifier of the AppDomain</span></span>

`appDomain`\
<span data-ttu-id="681c1-107">[out] Dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="681c1-107">[out] The AppDomain</span></span>

## <a name="remarks"></a><span data-ttu-id="681c1-108">Note</span><span class="sxs-lookup"><span data-stu-id="681c1-108">Remarks</span></span>

<span data-ttu-id="681c1-109">Il metodo specificato fa parte di `IXCLRDataProcess` interfaccia e corrisponde al 20 ° slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="681c1-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="681c1-110">Il `IXCLRDataAppDomain*` restituito viene usato per l'interazione con altre API.</span><span class="sxs-lookup"><span data-stu-id="681c1-110">The `IXCLRDataAppDomain*` returned is used for interaction with other APIs.</span></span>

## <a name="requirements"></a><span data-ttu-id="681c1-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="681c1-111">Requirements</span></span>
<span data-ttu-id="681c1-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="681c1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="681c1-113">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="681c1-113">**Header:** None</span></span>  
<span data-ttu-id="681c1-114">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="681c1-114">**Library:** None</span></span>  
**<span data-ttu-id="681c1-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="681c1-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a><span data-ttu-id="681c1-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="681c1-116">See also</span></span>

- [<span data-ttu-id="681c1-117">Debug</span><span class="sxs-lookup"><span data-stu-id="681c1-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="681c1-118">Interfaccia IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="681c1-118">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
