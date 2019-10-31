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
ms.openlocfilehash: a3a1b658f4ab05c7029de907882fe5ab2513ccd8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127878"
---
# <a name="icordebugmodule2-interface"></a><span data-ttu-id="4a443-102">Interfaccia ICorDebugModule2</span><span class="sxs-lookup"><span data-stu-id="4a443-102">ICorDebugModule2 Interface</span></span>

<span data-ttu-id="4a443-103">Funge da estensione logica per l'interfaccia ICorDebugModule.</span><span class="sxs-lookup"><span data-stu-id="4a443-103">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4a443-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="4a443-104">Methods</span></span>  
  
|<span data-ttu-id="4a443-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="4a443-105">Method</span></span>|<span data-ttu-id="4a443-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a443-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4a443-107">Metodo ApplyChanges</span><span class="sxs-lookup"><span data-stu-id="4a443-107">ApplyChanges Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|<span data-ttu-id="4a443-108">Applica le modifiche nei metadati e le modifiche nel codice MSIL (Microsoft Intermediate Language) al processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4a443-108">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="4a443-109">Metodo GetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="4a443-109">GetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="4a443-110">Ottiene i flag che controllano la compilazione JIT (just-in-Time) per questo `ICorDebugModule2`.</span><span class="sxs-lookup"><span data-stu-id="4a443-110">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="4a443-111">Metodo ResolveAssembly</span><span class="sxs-lookup"><span data-stu-id="4a443-111">ResolveAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="4a443-112">Risolve l'assembly a cui fa riferimento il token di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="4a443-112">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="4a443-113">Metodo SetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="4a443-113">SetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="4a443-114">Imposta i flag che controllano la compilazione JIT per questo `ICorDebugModule2`.</span><span class="sxs-lookup"><span data-stu-id="4a443-114">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="4a443-115">Metodo SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="4a443-115">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="4a443-116">Imposta lo stato del Just My Code (JMC) di tutti i metodi di tutte le classi di questo `ICorDebugModule2` sul valore specificato, ad eccezione di quelli nella matrice `pTokens`, che imposta sul valore opposto.</span><span class="sxs-lookup"><span data-stu-id="4a443-116">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a443-117">Note</span><span class="sxs-lookup"><span data-stu-id="4a443-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4a443-118">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="4a443-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a443-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4a443-119">Requirements</span></span>  
 <span data-ttu-id="4a443-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a443-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a443-121">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a443-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a443-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a443-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a443-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a443-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a443-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a443-124">See also</span></span>

- [<span data-ttu-id="4a443-125">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4a443-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
