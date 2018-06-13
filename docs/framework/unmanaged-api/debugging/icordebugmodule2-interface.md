---
title: ICorDebugModule2 Interface1
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
ms.openlocfilehash: 537023cf117477b54117799fc9ea62e894bb6591
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419140"
---
# <a name="icordebugmodule2-interface1"></a><span data-ttu-id="f391c-102">ICorDebugModule2 Interface1</span><span class="sxs-lookup"><span data-stu-id="f391c-102">ICorDebugModule2 Interface1</span></span>
<span data-ttu-id="f391c-103">Opera come estensione logica dell'interfaccia ICorDebugModule.</span><span class="sxs-lookup"><span data-stu-id="f391c-103">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f391c-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="f391c-104">Methods</span></span>  
  
|<span data-ttu-id="f391c-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="f391c-105">Method</span></span>|<span data-ttu-id="f391c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f391c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f391c-107">Metodo ApplyChanges</span><span class="sxs-lookup"><span data-stu-id="f391c-107">ApplyChanges Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|<span data-ttu-id="f391c-108">Applica le modifiche nei metadati e le modifiche nel codice Microsoft intermediate language (MSIL) per il processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f391c-108">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="f391c-109">Metodo GetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="f391c-109">GetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="f391c-110">Ottiene i flag che controllano la compilazione just-in-time (JIT) per questo `ICorDebugModule2`.</span><span class="sxs-lookup"><span data-stu-id="f391c-110">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="f391c-111">Metodo ResolveAssembly</span><span class="sxs-lookup"><span data-stu-id="f391c-111">ResolveAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="f391c-112">Consente di risolvere l'assembly a cui fa riferimento il token di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="f391c-112">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="f391c-113">Metodo SetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="f391c-113">SetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="f391c-114">Imposta i flag che controllano la compilazione JIT per questa `ICorDebugModule2`.</span><span class="sxs-lookup"><span data-stu-id="f391c-114">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="f391c-115">Metodo SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="f391c-115">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="f391c-116">Imposta lo stato JMC Just My Code () di tutti i metodi di tutte le classi in questo `ICorDebugModule2` sul valore specificato, ad eccezione di quelli di `pTokens` matrice, che vengono impostati sul valore opposto.</span><span class="sxs-lookup"><span data-stu-id="f391c-116">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f391c-117">Note</span><span class="sxs-lookup"><span data-stu-id="f391c-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f391c-118">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="f391c-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f391c-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f391c-119">Requirements</span></span>  
 <span data-ttu-id="f391c-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f391c-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f391c-121">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="f391c-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f391c-122">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="f391c-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f391c-123">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f391c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f391c-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f391c-124">See Also</span></span>  
 [<span data-ttu-id="f391c-125">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f391c-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
