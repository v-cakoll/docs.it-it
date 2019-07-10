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
ms.openlocfilehash: 79c4e0ed99a068d7d806d5c25580dc477aac6475
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752635"
---
# <a name="ixclrdataprocessstartenummodules-method"></a><span data-ttu-id="9e676-102">Metodo IXCLRDataProcess::StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="9e676-102">IXCLRDataProcess::StartEnumModules Method</span></span>

<span data-ttu-id="9e676-103">Fornisce un handle per enumerare i moduli di un processo.</span><span class="sxs-lookup"><span data-stu-id="9e676-103">Provides a handle to enumerate the modules of a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9e676-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9e676-104">Syntax</span></span>

```cpp
HRESULT StartEnumModules(
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="9e676-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9e676-105">Parameters</span></span>

`handle`\
<span data-ttu-id="9e676-106">[out] Handle per l'enumerazione dei moduli.</span><span class="sxs-lookup"><span data-stu-id="9e676-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="9e676-107">Note</span><span class="sxs-lookup"><span data-stu-id="9e676-107">Remarks</span></span>

<span data-ttu-id="9e676-108">Il metodo specificato fa parte di `IXCLRDataProcess` interfaccia e corrisponde al 24 slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="9e676-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 24th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="9e676-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9e676-109">Requirements</span></span>

<span data-ttu-id="9e676-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e676-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9e676-111">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="9e676-111">**Header:** None</span></span>  
<span data-ttu-id="9e676-112">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="9e676-112">**Library:** None</span></span>  
<span data-ttu-id="9e676-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9e676-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9e676-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e676-114">See also</span></span>

- [<span data-ttu-id="9e676-115">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="9e676-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="9e676-116">Debug</span><span class="sxs-lookup"><span data-stu-id="9e676-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="9e676-117">IXCLRDataProcess Interface</span><span class="sxs-lookup"><span data-stu-id="9e676-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
