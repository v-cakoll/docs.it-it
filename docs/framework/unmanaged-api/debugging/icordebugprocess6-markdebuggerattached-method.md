---
title: Metodo ICorDebugProcess6::MarkDebuggerAttached
ms.date: 03/30/2017
ms.assetid: bf94f090-5265-4112-8e57-5b4e20e070d0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c818b196f3252138f2a9c601b04f1d7a6727bc6b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912734"
---
# <a name="icordebugprocess6markdebuggerattached-method"></a><span data-ttu-id="22d4c-102">Metodo ICorDebugProcess6::MarkDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="22d4c-102">ICorDebugProcess6::MarkDebuggerAttached Method</span></span>
<span data-ttu-id="22d4c-103">Modifica lo stato interno dell'oggetto del debug in modo che il metodo <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> nella libreria di classi .NET Framework restituisca `true`.</span><span class="sxs-lookup"><span data-stu-id="22d4c-103">Changes the internal state of the debugee so that the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method in the .NET Framework Class Library returns `true`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22d4c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="22d4c-104">Syntax</span></span>  
  
```cpp  
HRESULT MarkDebuggerAttached(  
    BOOL fIsAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22d4c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="22d4c-105">Parameters</span></span>  
 `fIsAttached`  
 <span data-ttu-id="22d4c-106">`true` se il metodo <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> deve indicare che è collegato un debugger, altrimenti `false`.</span><span class="sxs-lookup"><span data-stu-id="22d4c-106">`true` if the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method should indicate that a debugger is attached; `false` otherwise.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22d4c-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="22d4c-107">Return Value</span></span>  
 <span data-ttu-id="22d4c-108">Il metodo può restituire i valori elencati nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="22d4c-108">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="22d4c-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="22d4c-109">Return value</span></span>|<span data-ttu-id="22d4c-110">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="22d4c-110">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="22d4c-111">L'oggetto del debug è stato aggiornato correttamente.</span><span class="sxs-lookup"><span data-stu-id="22d4c-111">The debuggee was successfully updated.</span></span>|  
|`CORDBG_E_MODULE_NOT_LOADED`|<span data-ttu-id="22d4c-112">L'assembly che contiene il metodo <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> non è caricato oppure altri errori, ad esempio metadati mancanti, ne stanno impedendo il riconoscimento.</span><span class="sxs-lookup"><span data-stu-id="22d4c-112">The assembly that contains the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method is not loaded, or some other error, such as missing metadata, is preventing it from being recognized.</span></span><br /><br /> <span data-ttu-id="22d4c-113">Questo errore è frequente e non grave.</span><span class="sxs-lookup"><span data-stu-id="22d4c-113">This error is common and benign.</span></span> <span data-ttu-id="22d4c-114">Chiamare di nuovo il metodo quando vengono caricati altri assembly.</span><span class="sxs-lookup"><span data-stu-id="22d4c-114">You should call the method again when additional assemblies load.</span></span>|  
|<span data-ttu-id="22d4c-115">Altri valori di `HRESULT` con errori.</span><span class="sxs-lookup"><span data-stu-id="22d4c-115">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="22d4c-116">Altri valori indicano probabilmente il comportamento errato di un debugger o dei componenti del compilatore.</span><span class="sxs-lookup"><span data-stu-id="22d4c-116">Other values likely indicate misbehaving debugger or compiler components.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22d4c-117">Note</span><span class="sxs-lookup"><span data-stu-id="22d4c-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="22d4c-118">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="22d4c-118">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22d4c-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="22d4c-119">Requirements</span></span>  
 <span data-ttu-id="22d4c-120">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22d4c-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22d4c-121">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="22d4c-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22d4c-122">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22d4c-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22d4c-123">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22d4c-123">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22d4c-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22d4c-124">See also</span></span>

- [<span data-ttu-id="22d4c-125">Interfaccia ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="22d4c-125">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="22d4c-126">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="22d4c-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
