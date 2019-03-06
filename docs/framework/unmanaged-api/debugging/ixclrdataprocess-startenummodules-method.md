---
title: Metodo IXCLRDataProcess::StartEnumModules
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumModules Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumModules Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumModules Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: d871ca5dfd62dbca309f4ccc3dcedf959033a41e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474163"
---
# <a name="ixclrdataprocessstartenummodules-method"></a><span data-ttu-id="f48a4-102">Metodo IXCLRDataProcess::StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="f48a4-102">IXCLRDataProcess::StartEnumModules Method</span></span>

<span data-ttu-id="f48a4-103">Fornisce un handle per enumerare i moduli di un processo.</span><span class="sxs-lookup"><span data-stu-id="f48a4-103">Provides a handle to enumerate the modules of a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="f48a4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f48a4-104">Syntax</span></span>

```
HRESULT StartEnumModules(
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="f48a4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f48a4-105">Parameters</span></span>

`handle`\
<span data-ttu-id="f48a4-106">[out] Handle per l'enumerazione dei moduli.</span><span class="sxs-lookup"><span data-stu-id="f48a4-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="f48a4-107">Note</span><span class="sxs-lookup"><span data-stu-id="f48a4-107">Remarks</span></span>

<span data-ttu-id="f48a4-108">Il metodo specificato fa parte di `IXCLRDataProcess` interfaccia e corrisponde al 24 slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="f48a4-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 24th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="f48a4-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f48a4-109">Requirements</span></span>

<span data-ttu-id="f48a4-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f48a4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="f48a4-111">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="f48a4-111">**Header:** None</span></span>  
<span data-ttu-id="f48a4-112">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="f48a4-112">**Library:** None</span></span>  
<span data-ttu-id="f48a4-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f48a4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="f48a4-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f48a4-114">See also</span></span>

- [<span data-ttu-id="f48a4-115">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="f48a4-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="f48a4-116">Debug</span><span class="sxs-lookup"><span data-stu-id="f48a4-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="f48a4-117">IXCLRDataProcess Interface</span><span class="sxs-lookup"><span data-stu-id="f48a4-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
