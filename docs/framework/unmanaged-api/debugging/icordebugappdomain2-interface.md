---
title: ICorDebugAppDomain2 Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain2
helpviewer_keywords: ICorDebugAppDomain2 interface [.NET Framework debugging]
ms.assetid: 314d29f3-feb0-4a92-9530-b569c280cc31
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ebd1e504cbf2f74ad82e7fea6b6c3f355a1bda34
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomain2-interface1"></a><span data-ttu-id="418bd-102">ICorDebugAppDomain2 Interface1</span><span class="sxs-lookup"><span data-stu-id="418bd-102">ICorDebugAppDomain2 Interface1</span></span>
<span data-ttu-id="418bd-103">Fornisce metodi per lavorare con le matrici, puntatori, puntatori a funzione e tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="418bd-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="418bd-104">Questa interfaccia è un'estensione dell'interfaccia ICorDebugAppDomain.</span><span class="sxs-lookup"><span data-stu-id="418bd-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="418bd-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="418bd-105">Methods</span></span>  
  
|<span data-ttu-id="418bd-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="418bd-106">Method</span></span>|<span data-ttu-id="418bd-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="418bd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="418bd-108">GetArrayOrPointerType (metodo)</span><span class="sxs-lookup"><span data-stu-id="418bd-108">GetArrayOrPointerType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="418bd-109">Ottiene una matrice di tipo specificato, o un puntatore o un riferimento al tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="418bd-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="418bd-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="418bd-110">GetFunctionPointerType</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="418bd-111">Ottiene un puntatore a una funzione che dispone di una determinata firma.</span><span class="sxs-lookup"><span data-stu-id="418bd-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="418bd-112">Note</span><span class="sxs-lookup"><span data-stu-id="418bd-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="418bd-113">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="418bd-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="418bd-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="418bd-114">Requirements</span></span>  
 <span data-ttu-id="418bd-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="418bd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="418bd-116">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="418bd-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="418bd-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="418bd-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="418bd-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="418bd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="418bd-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="418bd-119">See Also</span></span>  
 [<span data-ttu-id="418bd-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="418bd-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
