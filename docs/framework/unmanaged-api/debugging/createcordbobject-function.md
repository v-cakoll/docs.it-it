---
title: Funzione CreateCordbObject
ms.date: 03/30/2017
api_name:
- CreateCoredbObject
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ab86277956469e558d20cea81174a7fdcc0020b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739331"
---
# <a name="createcordbobject-function"></a><span data-ttu-id="d08c8-102">Funzione CreateCordbObject</span><span class="sxs-lookup"><span data-stu-id="d08c8-102">CreateCordbObject Function</span></span>
<span data-ttu-id="d08c8-103">Crea un'interfaccia del debugger ([ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)) che fornisce la funzionalità per creare un'istanza di una sessione di debug gestita in un processo remoto.</span><span class="sxs-lookup"><span data-stu-id="d08c8-103">Creates a debugger interface ([ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)) that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d08c8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d08c8-104">Syntax</span></span>  
  
```cpp  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,   
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d08c8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d08c8-105">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="d08c8-106">[in] Versione del debugger del processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d08c8-106">[in] Debugger version of the target process.</span></span> <span data-ttu-id="d08c8-107">Questo parametro deve essere CorDebugVersion_2_0 per il debug remoto.</span><span class="sxs-lookup"><span data-stu-id="d08c8-107">This parameter must be CorDebugVersion_2_0 for remote debugging.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="d08c8-108">[out] Puntatore a un puntatore a un oggetto che sarà possibile eseguire il cast a un [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interfaccia e restituito.</span><span class="sxs-lookup"><span data-stu-id="d08c8-108">[out] Pointer to a pointer to an object that will be cast to an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface and returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d08c8-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d08c8-109">Return Value</span></span>  
 <span data-ttu-id="d08c8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d08c8-110">S_OK</span></span>  
 <span data-ttu-id="d08c8-111">Il numero di CLR nel processo è stato determinato correttamente e le matrici di percorsi e di handle corrispondenti sono state riempite correttamente.</span><span class="sxs-lookup"><span data-stu-id="d08c8-111">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="d08c8-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d08c8-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="d08c8-113">`ppCordb` è null o `iDebuggerVersion` non è CorDebugVersion_2_0.</span><span class="sxs-lookup"><span data-stu-id="d08c8-113">`ppCordb` is null, or `iDebuggerVersion` is not CorDebugVersion_2_0.</span></span>  
  
 <span data-ttu-id="d08c8-114">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d08c8-114">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="d08c8-115">Non è possibile allocare memoria sufficiente per `ppCordb`.</span><span class="sxs-lookup"><span data-stu-id="d08c8-115">Unable to allocate enough memory for `ppCordb`</span></span>  
  
 <span data-ttu-id="d08c8-116">E_FAIL (o altri codici E_ restituiti)</span><span class="sxs-lookup"><span data-stu-id="d08c8-116">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="d08c8-117">Altri errori.</span><span class="sxs-lookup"><span data-stu-id="d08c8-117">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d08c8-118">Note</span><span class="sxs-lookup"><span data-stu-id="d08c8-118">Remarks</span></span>  
 <span data-ttu-id="d08c8-119">Il [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interfaccia restituita in `ppCordb` è l'interfaccia di debug di livello superiore per tutti i servizi di debug gestito.</span><span class="sxs-lookup"><span data-stu-id="d08c8-119">The [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface that is returned in `ppCordb` is the top-level debugging interface for all managed debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d08c8-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d08c8-120">Requirements</span></span>  
 <span data-ttu-id="d08c8-121">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d08c8-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d08c8-122">**Intestazione:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="d08c8-122">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="d08c8-123">**Library:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="d08c8-123">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="d08c8-124">**Versioni di .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="d08c8-124">**.NET Framework Versions:** 3.5 SP1</span></span>
