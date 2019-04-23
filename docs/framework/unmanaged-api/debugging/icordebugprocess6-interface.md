---
title: Interfaccia ICorDebugProcess6
ms.date: 03/30/2017
ms.assetid: 34a10ac2-882c-4797-8369-f120e8e640c7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 518c6ec99e4062bf8432809d3472baa395017da3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59147264"
---
# <a name="icordebugprocess6-interface"></a><span data-ttu-id="572b7-102">Interfaccia ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="572b7-102">ICorDebugProcess6 Interface</span></span>
<span data-ttu-id="572b7-103">Estende logicamente l'interfaccia ICorDebugProcess per abilitare funzionalità come la decodifica degli eventi di debug gestito sono codificati in eventi di debug di eccezioni native e suddivisione dei moduli virtuali.</span><span class="sxs-lookup"><span data-stu-id="572b7-103">Logically extends the ICorDebugProcess interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="572b7-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="572b7-104">Methods</span></span>  
  
|<span data-ttu-id="572b7-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="572b7-105">Method</span></span>|<span data-ttu-id="572b7-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="572b7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="572b7-107">Metodo DecodeEvent</span><span class="sxs-lookup"><span data-stu-id="572b7-107">DecodeEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md)|<span data-ttu-id="572b7-108">Decodifica gli eventi di debug gestiti incapsulati nel payload di eventi di debug per le eccezioni native appositamente predisposte.</span><span class="sxs-lookup"><span data-stu-id="572b7-108">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>|  
|[<span data-ttu-id="572b7-109">Metodo EnableVirtualModuleSplitting</span><span class="sxs-lookup"><span data-stu-id="572b7-109">EnableVirtualModuleSplitting Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md)|<span data-ttu-id="572b7-110">Abilita o disabilita la suddivisione dei moduli virtuali.</span><span class="sxs-lookup"><span data-stu-id="572b7-110">Enables or disables virtual module splitting.</span></span>|  
|[<span data-ttu-id="572b7-111">Metodo GetCode</span><span class="sxs-lookup"><span data-stu-id="572b7-111">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getcode-method.md)|<span data-ttu-id="572b7-112">Ottiene informazioni sul codice gestito in un indirizzo di codice specifico.</span><span class="sxs-lookup"><span data-stu-id="572b7-112">Gets information about the managed code at a particular code address.</span></span>|  
|[<span data-ttu-id="572b7-113">Metodo GetExportStepInfo</span><span class="sxs-lookup"><span data-stu-id="572b7-113">GetExportStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md)|<span data-ttu-id="572b7-114">Fornisce informazioni sulle funzioni di runtime esportate per consentire l'esecuzione di codice gestito seguendo un'istruzione alla volta.</span><span class="sxs-lookup"><span data-stu-id="572b7-114">Provides information on runtime exported functions to help step through managed code.</span></span>|  
|[<span data-ttu-id="572b7-115">Metodo MarkDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="572b7-115">MarkDebuggerAttached Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-markdebuggerattached-method.md)|<span data-ttu-id="572b7-116">Modifica lo stato interno dell'oggetto del debug in modo che il metodo <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> nella libreria di classi .NET Framework restituisca `true`.</span><span class="sxs-lookup"><span data-stu-id="572b7-116">Changes the internal state of the debugee so that the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method in the .NET Framework Class Library returns `true`.</span></span>|  
|[<span data-ttu-id="572b7-117">Metodo ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="572b7-117">ProcessStateChanged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md)|<span data-ttu-id="572b7-118">Invia una notifica [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) che viene eseguito il processo.</span><span class="sxs-lookup"><span data-stu-id="572b7-118">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="572b7-119">Note</span><span class="sxs-lookup"><span data-stu-id="572b7-119">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="572b7-120">L'interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="572b7-120">The interface is available with .NET Native only.</span></span> <span data-ttu-id="572b7-121">Il tentativo di chiamare `QueryInterface` per recuperare un puntatore a interfaccia restituisce `E_NOINTERFACE` per gli scenari ICorDebug al di fuori di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="572b7-121">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="572b7-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="572b7-122">Requirements</span></span>  
 <span data-ttu-id="572b7-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="572b7-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="572b7-124">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="572b7-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="572b7-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="572b7-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="572b7-126">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="572b7-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="572b7-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="572b7-127">See also</span></span>

- [<span data-ttu-id="572b7-128">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="572b7-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="572b7-129">Debug</span><span class="sxs-lookup"><span data-stu-id="572b7-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
