---
title: Interfaccia ICorDebugModule2
ms.date: 03/30/2017
api_name:
- ICorDebugModule2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2
helpviewer_keywords:
- ICorDebugModule2 interface [.NET Framework debugging]
ms.assetid: 0847e64f-fdbe-4c96-8168-da20fdc84d80
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3fb1bf3f61c78f4eb157b93363b1c06b25bee04
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987948"
---
# <a name="icordebugmodule2-interface"></a><span data-ttu-id="c4ed3-102">Interfaccia ICorDebugModule2</span><span class="sxs-lookup"><span data-stu-id="c4ed3-102">ICorDebugModule2 Interface</span></span>

<span data-ttu-id="c4ed3-103">Funge da un'estensione logica dell'interfaccia ICorDebugModule.</span><span class="sxs-lookup"><span data-stu-id="c4ed3-103">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c4ed3-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c4ed3-104">Methods</span></span>  
  
|<span data-ttu-id="c4ed3-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c4ed3-105">Method</span></span>|<span data-ttu-id="c4ed3-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c4ed3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c4ed3-107">Metodo ApplyChanges</span><span class="sxs-lookup"><span data-stu-id="c4ed3-107">ApplyChanges Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|<span data-ttu-id="c4ed3-108">Applica le modifiche nei metadati e le modifiche nel codice Microsoft intermediate language (MSIL) per il processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c4ed3-108">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="c4ed3-109">Metodo GetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="c4ed3-109">GetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="c4ed3-110">Ottiene i flag che controllano la compilazione just-in-time (JIT) per questo `ICorDebugModule2`.</span><span class="sxs-lookup"><span data-stu-id="c4ed3-110">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="c4ed3-111">Metodo ResolveAssembly</span><span class="sxs-lookup"><span data-stu-id="c4ed3-111">ResolveAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="c4ed3-112">Risolve l'assembly fa riferimento il token di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="c4ed3-112">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="c4ed3-113">Metodo SetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="c4ed3-113">SetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="c4ed3-114">Imposta i flag che controllano la compilazione JIT per questo `ICorDebugModule2`.</span><span class="sxs-lookup"><span data-stu-id="c4ed3-114">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="c4ed3-115">Metodo SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="c4ed3-115">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="c4ed3-116">Imposta lo stato di Just My Code (JMC) di tutti i metodi di tutte le classi in questo `ICorDebugModule2` sul valore specificato, eccetto quelli presenti il `pTokens` matrice, che imposta il valore opposto.</span><span class="sxs-lookup"><span data-stu-id="c4ed3-116">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4ed3-117">Note</span><span class="sxs-lookup"><span data-stu-id="c4ed3-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4ed3-118">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="c4ed3-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4ed3-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c4ed3-119">Requirements</span></span>  
 <span data-ttu-id="c4ed3-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4ed3-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4ed3-121">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4ed3-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4ed3-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4ed3-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4ed3-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4ed3-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4ed3-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4ed3-124">See also</span></span>

- [<span data-ttu-id="c4ed3-125">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c4ed3-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
