---
title: 'Metodo IXCLRDataProcess:: GetAppDomainByUniqueId'
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
ms.openlocfilehash: bb02ffed09cbcc31e653bfd3165050c247908c5d
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420784"
---
# <a name="ixclrdataprocessgetappdomainbyuniqueid-method"></a><span data-ttu-id="dd55c-102">Metodo IXCLRDataProcess:: GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="dd55c-102">IXCLRDataProcess::GetAppDomainByUniqueId Method</span></span>

<span data-ttu-id="dd55c-103">Ottiene un oggetto `AppDomain` in un processo in base al relativo identificatore univoco.</span><span class="sxs-lookup"><span data-stu-id="dd55c-103">Gets an `AppDomain` in a process based on its unique identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="dd55c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd55c-104">Syntax</span></span>

```cpp
HRESULT GetAppDomainByUniqueID(
    [in] ULONG64               id,
    [out] IXCLRDataAppDomain **appDomain
);
```

## <a name="parameters"></a><span data-ttu-id="dd55c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dd55c-105">Parameters</span></span>

`id`\
<span data-ttu-id="dd55c-106">in Identificatore univoco di AppDomain</span><span class="sxs-lookup"><span data-stu-id="dd55c-106">[in] The unique identifier of the AppDomain</span></span>

`appDomain`\
<span data-ttu-id="dd55c-107">out AppDomain</span><span class="sxs-lookup"><span data-stu-id="dd55c-107">[out] The AppDomain</span></span>

## <a name="remarks"></a><span data-ttu-id="dd55c-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="dd55c-108">Remarks</span></span>

<span data-ttu-id="dd55c-109">Il metodo fornito fa parte dell' `IXCLRDataProcess` interfaccia e corrisponde al ventesimo slot della tabella del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="dd55c-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="dd55c-110">L'oggetto `IXCLRDataAppDomain*` restituito viene usato per l'interazione con altre API.</span><span class="sxs-lookup"><span data-stu-id="dd55c-110">The `IXCLRDataAppDomain*` returned is used for interaction with other APIs.</span></span>

## <a name="requirements"></a><span data-ttu-id="dd55c-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dd55c-111">Requirements</span></span>

<span data-ttu-id="dd55c-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd55c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="dd55c-113">**Intestazione:** Nessuna **libreria:** nessuna **.NET Framework versioni:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="dd55c-113">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="dd55c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd55c-114">See also</span></span>

- [<span data-ttu-id="dd55c-115">Debug</span><span class="sxs-lookup"><span data-stu-id="dd55c-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="dd55c-116">Interfaccia IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="dd55c-116">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
