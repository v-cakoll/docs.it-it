---
title: Metodo IXCLRDataProcess::EnumModule
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
ms.openlocfilehash: a0398d18f9568754231082d63b4c6a2c865d8c6f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363306"
---
# <a name="ixclrdataprocessenummodule-method"></a><span data-ttu-id="acf6a-102">Metodo IXCLRDataProcess::EnumModule</span><span class="sxs-lookup"><span data-stu-id="acf6a-102">IXCLRDataProcess::EnumModule Method</span></span>

<span data-ttu-id="acf6a-103">Enumera i moduli di questo processo.</span><span class="sxs-lookup"><span data-stu-id="acf6a-103">Enumerates the modules of this process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="acf6a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="acf6a-104">Syntax</span></span>

```
HRESULT EnumModule(
    [in, out] CLRDATA_ENUM  *handle,
    [out] IXCLRDataModule  **mod
);
```

## <a name="parameters"></a><span data-ttu-id="acf6a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="acf6a-105">Parameters</span></span>

`handle`\
<span data-ttu-id="acf6a-106">[in, out] Handle per l'enumerazione dei moduli.</span><span class="sxs-lookup"><span data-stu-id="acf6a-106">[in, out] A handle for enumerating the modules.</span></span>

`mod`\
<span data-ttu-id="acf6a-107">[out] Il modulo enumerato.</span><span class="sxs-lookup"><span data-stu-id="acf6a-107">[out] The enumerated module.</span></span>

## <a name="remarks"></a><span data-ttu-id="acf6a-108">Note</span><span class="sxs-lookup"><span data-stu-id="acf6a-108">Remarks</span></span>

<span data-ttu-id="acf6a-109">Il metodo specificato fa parte di `IXCLRDataProcess` interfaccia e corrisponde al 25 slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="acf6a-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="acf6a-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="acf6a-110">Requirements</span></span>

<span data-ttu-id="acf6a-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acf6a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="acf6a-112">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="acf6a-112">**Header:** None</span></span>  
<span data-ttu-id="acf6a-113">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="acf6a-113">**Library:** None</span></span>  
<span data-ttu-id="acf6a-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="acf6a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="acf6a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="acf6a-115">See also</span></span>

- [<span data-ttu-id="acf6a-116">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="acf6a-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="acf6a-117">Debug</span><span class="sxs-lookup"><span data-stu-id="acf6a-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="acf6a-118">Interfaccia IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="acf6a-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
- [<span data-ttu-id="acf6a-119">IXCLRDataProcess Interface</span><span class="sxs-lookup"><span data-stu-id="acf6a-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
