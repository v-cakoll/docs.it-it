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
ms.openlocfilehash: e92eea9677731756bdbfcbdcfac1531861fb5dce
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361343"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a><span data-ttu-id="6971c-102">Metodo IXCLRDataMethodDefinition::StartEnumInstances</span><span class="sxs-lookup"><span data-stu-id="6971c-102">IXCLRDataMethodDefinition::StartEnumInstances Method</span></span>

<span data-ttu-id="6971c-103">Fornisce un handle per l'enumerazione delle istanze di metodo per un determinato `IXCLRDataAppDomain`.</span><span class="sxs-lookup"><span data-stu-id="6971c-103">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6971c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6971c-104">Syntax</span></span>

```
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="6971c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6971c-105">Parameters</span></span>

`appDomain`\
<span data-ttu-id="6971c-106">[in] Un dominio di applicazione per l'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="6971c-106">[in] An AppDomain for the enumeration.</span></span>

`handle`\
<span data-ttu-id="6971c-107">[out] Handle per l'enumerazione delle istanze.</span><span class="sxs-lookup"><span data-stu-id="6971c-107">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="6971c-108">Note</span><span class="sxs-lookup"><span data-stu-id="6971c-108">Remarks</span></span>

<span data-ttu-id="6971c-109">Il metodo specificato fa parte di `IXCLRDataMethodDefinition` interfaccia e corrisponde al terzo slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="6971c-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the third slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="6971c-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6971c-110">Requirements</span></span>

<span data-ttu-id="6971c-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6971c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6971c-112">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="6971c-112">**Header:** None</span></span>  
<span data-ttu-id="6971c-113">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="6971c-113">**Library:** None</span></span>  
<span data-ttu-id="6971c-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6971c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6971c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6971c-115">See also</span></span>

- [<span data-ttu-id="6971c-116">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="6971c-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="6971c-117">Debug</span><span class="sxs-lookup"><span data-stu-id="6971c-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="6971c-118">Interfaccia IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="6971c-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)