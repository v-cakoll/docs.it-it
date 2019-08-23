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
ms.openlocfilehash: d8fe1a25c4bc1f5e19f49f0d660d0aad5a180ea2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911894"
---
# <a name="icordebugmodule2-interface"></a><span data-ttu-id="4e79c-102">Interfaccia ICorDebugModule2</span><span class="sxs-lookup"><span data-stu-id="4e79c-102">ICorDebugModule2 Interface</span></span>

<span data-ttu-id="4e79c-103">Funge da estensione logica per l'interfaccia ICorDebugModule.</span><span class="sxs-lookup"><span data-stu-id="4e79c-103">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4e79c-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="4e79c-104">Methods</span></span>  
  
|<span data-ttu-id="4e79c-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="4e79c-105">Method</span></span>|<span data-ttu-id="4e79c-106">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="4e79c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4e79c-107">Metodo ApplyChanges</span><span class="sxs-lookup"><span data-stu-id="4e79c-107">ApplyChanges Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|<span data-ttu-id="4e79c-108">Applica le modifiche nei metadati e le modifiche nel codice MSIL (Microsoft Intermediate Language) al processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4e79c-108">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="4e79c-109">Metodo GetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="4e79c-109">GetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="4e79c-110">Ottiene i flag che controllano la compilazione JIT (just-in-Time) per `ICorDebugModule2`questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="4e79c-110">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="4e79c-111">Metodo ResolveAssembly</span><span class="sxs-lookup"><span data-stu-id="4e79c-111">ResolveAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="4e79c-112">Risolve l'assembly a cui fa riferimento il token di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="4e79c-112">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="4e79c-113">Metodo SetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="4e79c-113">SetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="4e79c-114">Imposta i flag che controllano la compilazione JIT per `ICorDebugModule2`questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="4e79c-114">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="4e79c-115">Metodo SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="4e79c-115">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="4e79c-116">Imposta lo stato del Just My Code (JMC) di tutti i metodi di tutte le classi `ICorDebugModule2` in questo oggetto sul valore specificato, ad eccezione `pTokens` di quelli nella matrice, che imposta sul valore opposto.</span><span class="sxs-lookup"><span data-stu-id="4e79c-116">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e79c-117">Note</span><span class="sxs-lookup"><span data-stu-id="4e79c-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4e79c-118">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="4e79c-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e79c-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4e79c-119">Requirements</span></span>  
 <span data-ttu-id="4e79c-120">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e79c-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e79c-121">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="4e79c-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4e79c-122">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e79c-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e79c-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e79c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e79c-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e79c-124">See also</span></span>

- [<span data-ttu-id="4e79c-125">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4e79c-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
