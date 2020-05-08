---
title: Interfaccia ICorDebugAppDomain2
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
ms.openlocfilehash: 1643d91f373ff233540026440ee21aa4c146f3e3
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895139"
---
# <a name="icordebugappdomain2-interface"></a><span data-ttu-id="bacaa-102">Interfaccia ICorDebugAppDomain2</span><span class="sxs-lookup"><span data-stu-id="bacaa-102">ICorDebugAppDomain2 Interface</span></span>

<span data-ttu-id="bacaa-103">Fornisce metodi per lavorare con matrici, puntatori, puntatori a funzione e tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="bacaa-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="bacaa-104">Questa interfaccia è un'estensione dell'interfaccia ICorDebugAppDomain.</span><span class="sxs-lookup"><span data-stu-id="bacaa-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bacaa-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="bacaa-105">Methods</span></span>  
  
|<span data-ttu-id="bacaa-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="bacaa-106">Method</span></span>|<span data-ttu-id="bacaa-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bacaa-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bacaa-108">Metodo GetArrayOrPointerType</span><span class="sxs-lookup"><span data-stu-id="bacaa-108">GetArrayOrPointerType Method</span></span>](icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="bacaa-109">Ottiene una matrice del tipo specificato o un puntatore o un riferimento al tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="bacaa-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="bacaa-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="bacaa-110">GetFunctionPointerType</span></span>](icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="bacaa-111">Ottiene un puntatore a una funzione con una firma specificata.</span><span class="sxs-lookup"><span data-stu-id="bacaa-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bacaa-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="bacaa-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bacaa-113">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="bacaa-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bacaa-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bacaa-114">Requirements</span></span>  
 <span data-ttu-id="bacaa-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bacaa-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bacaa-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bacaa-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bacaa-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bacaa-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bacaa-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bacaa-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bacaa-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bacaa-119">See also</span></span>

- [<span data-ttu-id="bacaa-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="bacaa-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
