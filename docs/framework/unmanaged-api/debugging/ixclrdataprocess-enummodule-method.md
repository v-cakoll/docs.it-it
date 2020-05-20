---
title: 'Metodo IXCLRDataProcess:: EnumModule'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumModule Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumModule Method
helpviewer.keywords:
- IXCLRDataProcess::EnumModule Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 5caadcfe091393a8ff79106d57a50a532c349829
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420775"
---
# <a name="ixclrdataprocessenummodule-method"></a><span data-ttu-id="739cb-102">Metodo IXCLRDataProcess:: EnumModule</span><span class="sxs-lookup"><span data-stu-id="739cb-102">IXCLRDataProcess::EnumModule Method</span></span>

<span data-ttu-id="739cb-103">Enumera i moduli di questo processo.</span><span class="sxs-lookup"><span data-stu-id="739cb-103">Enumerates the modules of this process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="739cb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="739cb-104">Syntax</span></span>

```cpp
HRESULT EnumModule(
    [in, out] CLRDATA_ENUM  *handle,
    [out] IXCLRDataModule  **mod
);
```

## <a name="parameters"></a><span data-ttu-id="739cb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="739cb-105">Parameters</span></span>

`handle`\
<span data-ttu-id="739cb-106">[in, out] Handle per l'enumerazione dei moduli.</span><span class="sxs-lookup"><span data-stu-id="739cb-106">[in, out] A handle for enumerating the modules.</span></span>

`mod`\
<span data-ttu-id="739cb-107">out Il modulo enumerato.</span><span class="sxs-lookup"><span data-stu-id="739cb-107">[out] The enumerated module.</span></span>

## <a name="remarks"></a><span data-ttu-id="739cb-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="739cb-108">Remarks</span></span>

<span data-ttu-id="739cb-109">Il metodo fornito fa parte dell' `IXCLRDataProcess` interfaccia e corrisponde al venticinquesimo slot della tabella del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="739cb-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="739cb-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="739cb-110">Requirements</span></span>

<span data-ttu-id="739cb-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="739cb-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="739cb-112">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="739cb-112">**Header:** None</span></span>  
<span data-ttu-id="739cb-113">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="739cb-113">**Library:** None</span></span>  
<span data-ttu-id="739cb-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="739cb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="739cb-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="739cb-115">See also</span></span>

- [<span data-ttu-id="739cb-116">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="739cb-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="739cb-117">Debug</span><span class="sxs-lookup"><span data-stu-id="739cb-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="739cb-118">Interfaccia IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="739cb-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
- [<span data-ttu-id="739cb-119">Interfaccia IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="739cb-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
