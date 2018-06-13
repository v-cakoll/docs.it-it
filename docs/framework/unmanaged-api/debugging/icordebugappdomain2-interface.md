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
ms.openlocfilehash: ff6ffdd733cf6e7b923d88d057d7cd230c8d8541
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407115"
---
# <a name="icordebugappdomain2-interface1"></a><span data-ttu-id="06272-102">ICorDebugAppDomain2 Interface1</span><span class="sxs-lookup"><span data-stu-id="06272-102">ICorDebugAppDomain2 Interface1</span></span>
<span data-ttu-id="06272-103">Fornisce metodi per lavorare con le matrici, puntatori, puntatori a funzione e tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="06272-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="06272-104">Questa interfaccia è un'estensione dell'interfaccia ICorDebugAppDomain.</span><span class="sxs-lookup"><span data-stu-id="06272-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="06272-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="06272-105">Methods</span></span>  
  
|<span data-ttu-id="06272-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="06272-106">Method</span></span>|<span data-ttu-id="06272-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="06272-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="06272-108">Metodo GetArrayOrPointerType</span><span class="sxs-lookup"><span data-stu-id="06272-108">GetArrayOrPointerType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="06272-109">Ottiene una matrice di tipo specificato, o un puntatore o un riferimento al tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="06272-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="06272-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="06272-110">GetFunctionPointerType</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="06272-111">Ottiene un puntatore a una funzione che dispone di una determinata firma.</span><span class="sxs-lookup"><span data-stu-id="06272-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06272-112">Note</span><span class="sxs-lookup"><span data-stu-id="06272-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06272-113">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="06272-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06272-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="06272-114">Requirements</span></span>  
 <span data-ttu-id="06272-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06272-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06272-116">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="06272-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06272-117">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="06272-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06272-118">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06272-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06272-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06272-119">See Also</span></span>  
 [<span data-ttu-id="06272-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="06272-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
