---
title: 'Metodo IXCLRDataMethodDefinition:: EndEnumInstances'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EndEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: febe6766c7a35228820421eee975c777988efd1f
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396496"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a><span data-ttu-id="0e6cc-102">Metodo IXCLRDataMethodDefinition:: EndEnumInstances</span><span class="sxs-lookup"><span data-stu-id="0e6cc-102">IXCLRDataMethodDefinition::EndEnumInstances Method</span></span>

<span data-ttu-id="0e6cc-103">Rilascia le risorse utilizzate dagli iteratori interni utilizzati durante l'enumerazione dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="0e6cc-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="0e6cc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0e6cc-104">Syntax</span></span>

```cpp
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="0e6cc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0e6cc-105">Parameters</span></span>

`handle`\
<span data-ttu-id="0e6cc-106">out Handle per l'enumerazione delle istanze.</span><span class="sxs-lookup"><span data-stu-id="0e6cc-106">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="0e6cc-107">Commenti</span><span class="sxs-lookup"><span data-stu-id="0e6cc-107">Remarks</span></span>

<span data-ttu-id="0e6cc-108">Il metodo fornito fa parte dell' `IXCLRDataMethodDefinition` interfaccia e corrisponde al settimo slot della tabella del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="0e6cc-108">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 7th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="0e6cc-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0e6cc-109">Requirements</span></span>

<span data-ttu-id="0e6cc-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e6cc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="0e6cc-111">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="0e6cc-111">**Header:** None</span></span>  
<span data-ttu-id="0e6cc-112">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="0e6cc-112">**Library:** None</span></span>  
<span data-ttu-id="0e6cc-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0e6cc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="0e6cc-114">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="0e6cc-114">See also</span></span>

- [<span data-ttu-id="0e6cc-115">Debug</span><span class="sxs-lookup"><span data-stu-id="0e6cc-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="0e6cc-116">Interfaccia IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="0e6cc-116">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
