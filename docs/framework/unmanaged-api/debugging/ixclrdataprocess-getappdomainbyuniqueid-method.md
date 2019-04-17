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
ms.openlocfilehash: 8b468d40ef8eb523ba8881627fae15cf9b7c7b80
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2019
ms.locfileid: "59614022"
---
# <a name="ixclrdataprocessgetappdomainbyuniqueid-method"></a><span data-ttu-id="44f8d-102">IXCLRDataProcess::GetAppDomainByUniqueId Method</span><span class="sxs-lookup"><span data-stu-id="44f8d-102">IXCLRDataProcess::GetAppDomainByUniqueId Method</span></span>

<span data-ttu-id="44f8d-103">Ottiene un `AppDomain` in un processo in base al relativo identificatore univoco.</span><span class="sxs-lookup"><span data-stu-id="44f8d-103">Gets an `AppDomain` in a process based on its unique identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="44f8d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="44f8d-104">Syntax</span></span>

```cpp
HRESULT GetAppDomainByUniqueID(
    [in] ULONG64               id,
    [out] IXCLRDataAppDomain **appDomain
);
```

## <a name="parameters"></a><span data-ttu-id="44f8d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="44f8d-105">Parameters</span></span>

`id`\
<span data-ttu-id="44f8d-106">[in] L'identificatore univoco del dominio applicazione</span><span class="sxs-lookup"><span data-stu-id="44f8d-106">[in] The unique identifier of the AppDomain</span></span>

`appDomain`\
<span data-ttu-id="44f8d-107">[out] Dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="44f8d-107">[out] The AppDomain</span></span>

## <a name="remarks"></a><span data-ttu-id="44f8d-108">Note</span><span class="sxs-lookup"><span data-stu-id="44f8d-108">Remarks</span></span>

<span data-ttu-id="44f8d-109">Il metodo specificato fa parte di `IXCLRDataProcess` interfaccia e corrisponde al 20 ° slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="44f8d-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="44f8d-110">Il `IXCLRDataAppDomain*` restituito viene usato per l'interazione con altre API.</span><span class="sxs-lookup"><span data-stu-id="44f8d-110">The `IXCLRDataAppDomain*` returned is used for interaction with other APIs.</span></span>

## <a name="requirements"></a><span data-ttu-id="44f8d-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="44f8d-111">Requirements</span></span>

<span data-ttu-id="44f8d-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44f8d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="44f8d-113">**Intestazione:** Nessuno **libreria:** Nessuno **versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="44f8d-113">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="44f8d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44f8d-114">See also</span></span>

- [<span data-ttu-id="44f8d-115">Debug</span><span class="sxs-lookup"><span data-stu-id="44f8d-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="44f8d-116">IXCLRDataProcess Interface</span><span class="sxs-lookup"><span data-stu-id="44f8d-116">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
