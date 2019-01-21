---
title: Interfaccia IXCLRDataMethodDefinition
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition Interface
helpviewer.keywords:
- IXCLRDataMethodDefinition Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 4265db62b11453d9fc087928adb0cc0c05c052ca
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416610"
---
# <a name="ixclrdatamethoddefinition-interface"></a><span data-ttu-id="53025-102">Interfaccia IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="53025-102">IXCLRDataMethodDefinition Interface</span></span>

<span data-ttu-id="53025-103">Fornisce metodi per l'esecuzione di query informazioni sulla definizione di un metodo.</span><span class="sxs-lookup"><span data-stu-id="53025-103">Provides methods for querying information about a method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="53025-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="53025-104">Methods</span></span>

<span data-ttu-id="53025-105">I metodi seguenti sono alcuni dei metodi disponibili nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="53025-105">The following methods are some of the methods available in the interface.</span></span>

| <span data-ttu-id="53025-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="53025-106">Method</span></span>                                                                                                                          | <span data-ttu-id="53025-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53025-107">Description</span></span>                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="53025-108">StartEnumInstances</span><span class="sxs-lookup"><span data-stu-id="53025-108">StartEnumInstances</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-startenuminstances-method.md) | <span data-ttu-id="53025-109">Fornisce un handle per l'enumerazione delle istanze di metodo per un determinato `IXCLRDataAppDomain`.</span><span class="sxs-lookup"><span data-stu-id="53025-109">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span> |
| [<span data-ttu-id="53025-110">EnumInstance</span><span class="sxs-lookup"><span data-stu-id="53025-110">EnumInstance</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-enuminstance-method.md)             | <span data-ttu-id="53025-111">Enumera le istanze di questa definizione di metodo.</span><span class="sxs-lookup"><span data-stu-id="53025-111">Enumerates the instances of this method definition.</span></span>                                         |
| [<span data-ttu-id="53025-112">EndEnumInstances</span><span class="sxs-lookup"><span data-stu-id="53025-112">EndEnumInstances</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-endenuminstances-method.md)     | <span data-ttu-id="53025-113">Rilascia le risorse usate dagli iteratori interni utilizzati durante l'enumerazione di istanza.</span><span class="sxs-lookup"><span data-stu-id="53025-113">Releases the resources used by internal iterators used during instance enumeration.</span></span>         |

## <a name="remarks"></a><span data-ttu-id="53025-114">Note</span><span class="sxs-lookup"><span data-stu-id="53025-114">Remarks</span></span>

<span data-ttu-id="53025-115">Questa interfaccia si trova all'interno del runtime e non viene esposto tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="53025-115">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="53025-116">Tuttavia, è un'interfaccia COM che deriva da `IUnknown` con GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` che può essere ottenuto tramite i normali meccanismi di COM.</span><span class="sxs-lookup"><span data-stu-id="53025-116">However, it's a COM interface that derives from `IUnknown` with GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="53025-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="53025-117">Requirements</span></span>

<span data-ttu-id="53025-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53025-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="53025-119">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="53025-119">**Header:** None</span></span>  
<span data-ttu-id="53025-120">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="53025-120">**Library:** None</span></span>  
<span data-ttu-id="53025-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="53025-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="53025-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53025-122">See Also</span></span>

- [<span data-ttu-id="53025-123">Debug</span><span class="sxs-lookup"><span data-stu-id="53025-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="53025-124">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="53025-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
