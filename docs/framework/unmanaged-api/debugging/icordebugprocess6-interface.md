---
title: Interfaccia ICorDebugProcess6
ms.date: 03/30/2017
ms.assetid: 34a10ac2-882c-4797-8369-f120e8e640c7
ms.openlocfilehash: 73ef1a64deaf5420246fc1ab3e9f88ba5bf049a5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792228"
---
# <a name="icordebugprocess6-interface"></a><span data-ttu-id="47304-102">Interfaccia ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="47304-102">ICorDebugProcess6 Interface</span></span>
<span data-ttu-id="47304-103">Estende logicamente l'interfaccia ICorDebugProcess per abilitare funzionalità come la decodifica degli eventi di debug gestiti, codificati negli eventi di debug per le eccezioni native, e la suddivisione dei moduli virtuali.</span><span class="sxs-lookup"><span data-stu-id="47304-103">Logically extends the ICorDebugProcess interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="47304-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="47304-104">Methods</span></span>  
  
|<span data-ttu-id="47304-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="47304-105">Method</span></span>|<span data-ttu-id="47304-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="47304-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="47304-107">Metodo DecodeEvent</span><span class="sxs-lookup"><span data-stu-id="47304-107">DecodeEvent Method</span></span>](icordebugprocess6-decodeevent-method.md)|<span data-ttu-id="47304-108">Decodifica gli eventi di debug gestiti incapsulati nel payload di eventi di debug per le eccezioni native appositamente predisposte.</span><span class="sxs-lookup"><span data-stu-id="47304-108">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>|  
|[<span data-ttu-id="47304-109">Metodo EnableVirtualModuleSplitting</span><span class="sxs-lookup"><span data-stu-id="47304-109">EnableVirtualModuleSplitting Method</span></span>](icordebugprocess6-enablevirtualmodulesplitting-method.md)|<span data-ttu-id="47304-110">Abilita o disabilita la suddivisione dei moduli virtuali.</span><span class="sxs-lookup"><span data-stu-id="47304-110">Enables or disables virtual module splitting.</span></span>|  
|[<span data-ttu-id="47304-111">Metodo GetCode</span><span class="sxs-lookup"><span data-stu-id="47304-111">GetCode Method</span></span>](icordebugprocess6-getcode-method.md)|<span data-ttu-id="47304-112">Ottiene informazioni sul codice gestito in un indirizzo di codice specifico.</span><span class="sxs-lookup"><span data-stu-id="47304-112">Gets information about the managed code at a particular code address.</span></span>|  
|[<span data-ttu-id="47304-113">Metodo GetExportStepInfo</span><span class="sxs-lookup"><span data-stu-id="47304-113">GetExportStepInfo Method</span></span>](icordebugprocess6-getexportstepinfo-method.md)|<span data-ttu-id="47304-114">Fornisce informazioni sulle funzioni di runtime esportate per consentire l'esecuzione di codice gestito seguendo un'istruzione alla volta.</span><span class="sxs-lookup"><span data-stu-id="47304-114">Provides information on runtime exported functions to help step through managed code.</span></span>|  
|[<span data-ttu-id="47304-115">Metodo MarkDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="47304-115">MarkDebuggerAttached Method</span></span>](icordebugprocess6-markdebuggerattached-method.md)|<span data-ttu-id="47304-116">Modifica lo stato interno dell'oggetto del debug in modo che il metodo <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> nella libreria di classi .NET Framework restituisca `true`.</span><span class="sxs-lookup"><span data-stu-id="47304-116">Changes the internal state of the debugee so that the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method in the .NET Framework Class Library returns `true`.</span></span>|  
|[<span data-ttu-id="47304-117">Metodo ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="47304-117">ProcessStateChanged Method</span></span>](icordebugprocess6-processstatechanged-method.md)|<span data-ttu-id="47304-118">Notifica a [ICorDebug](icordebug-interface.md) che il processo è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="47304-118">Notifies [ICorDebug](icordebug-interface.md) that the process is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47304-119">Note</span><span class="sxs-lookup"><span data-stu-id="47304-119">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="47304-120">L'interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="47304-120">The interface is available with .NET Native only.</span></span> <span data-ttu-id="47304-121">Il tentativo di chiamare `QueryInterface` per recuperare un puntatore a interfaccia restituisce `E_NOINTERFACE` per gli scenari ICorDebug al di fuori di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="47304-121">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47304-122">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="47304-122">Requirements</span></span>  
 <span data-ttu-id="47304-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47304-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47304-124">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="47304-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="47304-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47304-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47304-126">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47304-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47304-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47304-127">See also</span></span>

- [<span data-ttu-id="47304-128">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="47304-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="47304-129">Debug</span><span class="sxs-lookup"><span data-stu-id="47304-129">Debugging</span></span>](index.md)
