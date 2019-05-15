---
title: Metodo IXCLRDataMethodDefinition::StartEnumInstances
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::StartEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 7f45a5b13e767fa6849f307ee96fb822447f1263
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65629960"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a><span data-ttu-id="1203e-102">Metodo IXCLRDataMethodDefinition::StartEnumInstances</span><span class="sxs-lookup"><span data-stu-id="1203e-102">IXCLRDataMethodDefinition::StartEnumInstances Method</span></span>

<span data-ttu-id="1203e-103">Fornisce un handle per l'enumerazione delle istanze di metodo per un determinato `IXCLRDataAppDomain`.</span><span class="sxs-lookup"><span data-stu-id="1203e-103">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="1203e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1203e-104">Syntax</span></span>

```
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="1203e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1203e-105">Parameters</span></span>

`appDomain`\
<span data-ttu-id="1203e-106">[in] Un dominio di applicazione per l'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="1203e-106">[in] An AppDomain for the enumeration.</span></span>

`handle`\
<span data-ttu-id="1203e-107">[out] Handle per l'enumerazione delle istanze.</span><span class="sxs-lookup"><span data-stu-id="1203e-107">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="1203e-108">Note</span><span class="sxs-lookup"><span data-stu-id="1203e-108">Remarks</span></span>

<span data-ttu-id="1203e-109">Il metodo specificato fa parte di `IXCLRDataMethodDefinition` interfaccia e corrisponde al terzo slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="1203e-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the third slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="1203e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1203e-110">Requirements</span></span>

<span data-ttu-id="1203e-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1203e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="1203e-112">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="1203e-112">**Header:** None</span></span>  
<span data-ttu-id="1203e-113">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="1203e-113">**Library:** None</span></span>  
<span data-ttu-id="1203e-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1203e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="1203e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1203e-115">See also</span></span>

- [<span data-ttu-id="1203e-116">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="1203e-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="1203e-117">Debug</span><span class="sxs-lookup"><span data-stu-id="1203e-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="1203e-118">Interfaccia IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="1203e-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
