---
title: ICorDebugAppDomain2 Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2
helpviewer_keywords:
- ICorDebugAppDomain2 interface [.NET Framework debugging]
ms.assetid: 314d29f3-feb0-4a92-9530-b569c280cc31
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4549b0fe6379979a7b9bd6344d65ff465f33f17
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506134"
---
# <a name="icordebugappdomain2-interface1"></a><span data-ttu-id="5512f-102">ICorDebugAppDomain2 Interface1</span><span class="sxs-lookup"><span data-stu-id="5512f-102">ICorDebugAppDomain2 Interface1</span></span>
<span data-ttu-id="5512f-103">Fornisce metodi per lavorare con matrici, puntatori, puntatori a funzione e i tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="5512f-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="5512f-104">Questa interfaccia è un'estensione dell'interfaccia ICorDebugAppDomain.</span><span class="sxs-lookup"><span data-stu-id="5512f-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5512f-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="5512f-105">Methods</span></span>  
  
|<span data-ttu-id="5512f-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="5512f-106">Method</span></span>|<span data-ttu-id="5512f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5512f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5512f-108">Metodo GetArrayOrPointerType</span><span class="sxs-lookup"><span data-stu-id="5512f-108">GetArrayOrPointerType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="5512f-109">Ottiene una matrice di tipo specificato, o un puntatore o riferimento al tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="5512f-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="5512f-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="5512f-110">GetFunctionPointerType</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="5512f-111">Ottiene un puntatore a una funzione che dispone di una determinata firma.</span><span class="sxs-lookup"><span data-stu-id="5512f-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5512f-112">Note</span><span class="sxs-lookup"><span data-stu-id="5512f-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5512f-113">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="5512f-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5512f-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5512f-114">Requirements</span></span>  
 <span data-ttu-id="5512f-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5512f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5512f-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5512f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5512f-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5512f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5512f-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5512f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5512f-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5512f-119">See also</span></span>
- [<span data-ttu-id="5512f-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="5512f-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
