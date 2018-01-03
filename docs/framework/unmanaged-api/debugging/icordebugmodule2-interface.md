---
title: ICorDebugModule2 Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule2
helpviewer_keywords: ICorDebugModule2 interface [.NET Framework debugging]
ms.assetid: 0847e64f-fdbe-4c96-8168-da20fdc84d80
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a3d62619fd83264bdc774cc1f09f4d98492d0a57
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodule2-interface1"></a><span data-ttu-id="49550-102">ICorDebugModule2 Interface1</span><span class="sxs-lookup"><span data-stu-id="49550-102">ICorDebugModule2 Interface1</span></span>
<span data-ttu-id="49550-103">Opera come estensione logica dell'interfaccia ICorDebugModule.</span><span class="sxs-lookup"><span data-stu-id="49550-103">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="49550-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="49550-104">Methods</span></span>  
  
|<span data-ttu-id="49550-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="49550-105">Method</span></span>|<span data-ttu-id="49550-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49550-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="49550-107">Metodo ApplyChanges</span><span class="sxs-lookup"><span data-stu-id="49550-107">ApplyChanges Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|<span data-ttu-id="49550-108">Applica le modifiche nei metadati e le modifiche nel codice Microsoft intermediate language (MSIL) per il processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="49550-108">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="49550-109">Metodo GetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="49550-109">GetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="49550-110">Ottiene i flag che controllano la compilazione just-in-time (JIT) per questo `ICorDebugModule2`.</span><span class="sxs-lookup"><span data-stu-id="49550-110">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="49550-111">Metodo ResolveAssembly</span><span class="sxs-lookup"><span data-stu-id="49550-111">ResolveAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="49550-112">Consente di risolvere l'assembly a cui fa riferimento il token di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="49550-112">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="49550-113">Metodo SetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="49550-113">SetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="49550-114">Imposta i flag che controllano la compilazione JIT per questa `ICorDebugModule2`.</span><span class="sxs-lookup"><span data-stu-id="49550-114">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="49550-115">Metodo SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="49550-115">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="49550-116">Imposta lo stato JMC Just My Code () di tutti i metodi di tutte le classi in questo `ICorDebugModule2` sul valore specificato, ad eccezione di quelli di `pTokens` matrice, che vengono impostati sul valore opposto.</span><span class="sxs-lookup"><span data-stu-id="49550-116">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49550-117">Note</span><span class="sxs-lookup"><span data-stu-id="49550-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49550-118">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="49550-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49550-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="49550-119">Requirements</span></span>  
 <span data-ttu-id="49550-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49550-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49550-121">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="49550-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49550-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49550-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49550-123">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49550-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49550-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49550-124">See Also</span></span>  
 [<span data-ttu-id="49550-125">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="49550-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
