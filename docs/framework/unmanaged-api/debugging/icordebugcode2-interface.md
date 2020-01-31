---
title: Interfaccia ICorDebugCode2
ms.date: 03/30/2017
api_name:
- ICorDebugCode2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2
helpviewer_keywords:
- ICorDebugCode2 interface [.NET Framework debugging]
ms.assetid: 9321903b-7dea-40d8-ba32-99016c00cc46
topic_type:
- apiref
ms.openlocfilehash: a9ce778cfa1aed4dcf6117c4fe2eca23ccda37a3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777954"
---
# <a name="icordebugcode2-interface"></a><span data-ttu-id="23511-102">Interfaccia ICorDebugCode2</span><span class="sxs-lookup"><span data-stu-id="23511-102">ICorDebugCode2 Interface</span></span>

<span data-ttu-id="23511-103">Fornisce metodi che estendono le funzionalità di "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="23511-103">Provides methods that extend the capabilities of "ICorDebugCode".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="23511-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="23511-104">Methods</span></span>  
  
|<span data-ttu-id="23511-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="23511-105">Method</span></span>|<span data-ttu-id="23511-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23511-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="23511-107">Metodo GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="23511-107">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)|<span data-ttu-id="23511-108">Ottiene i blocchi di codice di cui questo oggetto di codice è composto.</span><span class="sxs-lookup"><span data-stu-id="23511-108">Gets the chunks of code that this code object is composed of.</span></span>|  
|[<span data-ttu-id="23511-109">Metodo GetCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="23511-109">GetCompilerFlags Method</span></span>](icordebugcode2-getcompilerflags-method.md)|<span data-ttu-id="23511-110">Ottiene i flag che specificano le condizioni in base alle quali l'oggetto di codice è stato compilato o generato JIT usando il generatore di immagini native (Ngen. exe).</span><span class="sxs-lookup"><span data-stu-id="23511-110">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23511-111">Note</span><span class="sxs-lookup"><span data-stu-id="23511-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="23511-112">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="23511-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23511-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="23511-113">Requirements</span></span>  
 <span data-ttu-id="23511-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23511-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23511-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23511-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23511-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23511-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23511-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23511-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23511-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23511-118">See also</span></span>

- [<span data-ttu-id="23511-119">Interfaccia ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="23511-119">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
- [<span data-ttu-id="23511-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="23511-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
