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
ms.openlocfilehash: 32774aacecf3e56510bc6f0670538a44fde794c9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792981"
---
# <a name="icordebugmodule2-interface"></a><span data-ttu-id="9f341-102">Interfaccia ICorDebugModule2</span><span class="sxs-lookup"><span data-stu-id="9f341-102">ICorDebugModule2 Interface</span></span>

<span data-ttu-id="9f341-103">Funge da estensione logica per l'interfaccia ICorDebugModule.</span><span class="sxs-lookup"><span data-stu-id="9f341-103">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9f341-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="9f341-104">Methods</span></span>  
  
|<span data-ttu-id="9f341-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="9f341-105">Method</span></span>|<span data-ttu-id="9f341-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9f341-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9f341-107">Metodo ApplyChanges</span><span class="sxs-lookup"><span data-stu-id="9f341-107">ApplyChanges Method</span></span>](icordebugmodule2-applychanges-method.md)|<span data-ttu-id="9f341-108">Applica le modifiche nei metadati e le modifiche nel codice MSIL (Microsoft Intermediate Language) al processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9f341-108">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="9f341-109">Metodo GetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="9f341-109">GetJITCompilerFlags Method</span></span>](icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="9f341-110">Ottiene i flag che controllano la compilazione JIT (just-in-Time) per questo `ICorDebugModule2`.</span><span class="sxs-lookup"><span data-stu-id="9f341-110">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="9f341-111">Metodo ResolveAssembly</span><span class="sxs-lookup"><span data-stu-id="9f341-111">ResolveAssembly Method</span></span>](icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="9f341-112">Risolve l'assembly a cui fa riferimento il token di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="9f341-112">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="9f341-113">Metodo SetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="9f341-113">SetJITCompilerFlags Method</span></span>](icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="9f341-114">Imposta i flag che controllano la compilazione JIT per questo `ICorDebugModule2`.</span><span class="sxs-lookup"><span data-stu-id="9f341-114">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="9f341-115">Metodo SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="9f341-115">SetJMCStatus Method</span></span>](icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="9f341-116">Imposta lo stato del Just My Code (JMC) di tutti i metodi di tutte le classi di questo `ICorDebugModule2` sul valore specificato, ad eccezione di quelli nella matrice `pTokens`, che imposta sul valore opposto.</span><span class="sxs-lookup"><span data-stu-id="9f341-116">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f341-117">Note</span><span class="sxs-lookup"><span data-stu-id="9f341-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9f341-118">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="9f341-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f341-119">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="9f341-119">Requirements</span></span>  
 <span data-ttu-id="9f341-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f341-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f341-121">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f341-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f341-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f341-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f341-123">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f341-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f341-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f341-124">See also</span></span>

- [<span data-ttu-id="9f341-125">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="9f341-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
