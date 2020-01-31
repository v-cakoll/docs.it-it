---
title: Metodo ICorDebugProcess6::MarkDebuggerAttached
ms.date: 03/30/2017
ms.assetid: bf94f090-5265-4112-8e57-5b4e20e070d0
ms.openlocfilehash: b2ecd6da11bffb156826fa0c31b5f32abb54ff4a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792213"
---
# <a name="icordebugprocess6markdebuggerattached-method"></a><span data-ttu-id="caead-102">Metodo ICorDebugProcess6::MarkDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="caead-102">ICorDebugProcess6::MarkDebuggerAttached Method</span></span>
<span data-ttu-id="caead-103">Modifica lo stato interno dell'oggetto del debug in modo che il metodo <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> nella libreria di classi .NET Framework restituisca `true`.</span><span class="sxs-lookup"><span data-stu-id="caead-103">Changes the internal state of the debugee so that the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method in the .NET Framework Class Library returns `true`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caead-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="caead-104">Syntax</span></span>  
  
```cpp  
HRESULT MarkDebuggerAttached(  
    BOOL fIsAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="caead-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="caead-105">Parameters</span></span>  
 `fIsAttached`  
 <span data-ttu-id="caead-106">`true` se il metodo <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> deve indicare che è collegato un debugger, altrimenti `false`.</span><span class="sxs-lookup"><span data-stu-id="caead-106">`true` if the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method should indicate that a debugger is attached; `false` otherwise.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="caead-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="caead-107">Return Value</span></span>  
 <span data-ttu-id="caead-108">Il metodo può restituire i valori elencati nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="caead-108">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="caead-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="caead-109">Return value</span></span>|<span data-ttu-id="caead-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="caead-110">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="caead-111">L'oggetto del debug è stato aggiornato correttamente.</span><span class="sxs-lookup"><span data-stu-id="caead-111">The debuggee was successfully updated.</span></span>|  
|`CORDBG_E_MODULE_NOT_LOADED`|<span data-ttu-id="caead-112">L'assembly che contiene il metodo <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> non è caricato oppure altri errori, ad esempio metadati mancanti, ne stanno impedendo il riconoscimento.</span><span class="sxs-lookup"><span data-stu-id="caead-112">The assembly that contains the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method is not loaded, or some other error, such as missing metadata, is preventing it from being recognized.</span></span><br /><br /> <span data-ttu-id="caead-113">Questo errore è frequente e non grave.</span><span class="sxs-lookup"><span data-stu-id="caead-113">This error is common and benign.</span></span> <span data-ttu-id="caead-114">Chiamare di nuovo il metodo quando vengono caricati altri assembly.</span><span class="sxs-lookup"><span data-stu-id="caead-114">You should call the method again when additional assemblies load.</span></span>|  
|<span data-ttu-id="caead-115">Altri valori di `HRESULT` con errori.</span><span class="sxs-lookup"><span data-stu-id="caead-115">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="caead-116">Altri valori indicano probabilmente il comportamento errato di un debugger o dei componenti del compilatore.</span><span class="sxs-lookup"><span data-stu-id="caead-116">Other values likely indicate misbehaving debugger or compiler components.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="caead-117">Note</span><span class="sxs-lookup"><span data-stu-id="caead-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="caead-118">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="caead-118">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="caead-119">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="caead-119">Requirements</span></span>  
 <span data-ttu-id="caead-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="caead-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="caead-121">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="caead-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="caead-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="caead-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="caead-123">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="caead-123">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caead-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="caead-124">See also</span></span>

- [<span data-ttu-id="caead-125">Interfaccia ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="caead-125">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="caead-126">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="caead-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
