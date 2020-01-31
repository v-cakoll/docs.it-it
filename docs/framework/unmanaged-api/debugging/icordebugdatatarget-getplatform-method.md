---
title: Metodo ICorDebugDataTarget::GetPlatform
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetPlatform Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetPlatform
helpviewer_keywords:
- GetPlatform method [.NET Framework debugging]
- ICorDebugDataTarget::GetPlatform method [.NET Framework debugging]
ms.assetid: 9ee96c9d-7a3d-4129-a6cc-7675c7f2dda4
topic_type:
- apiref
ms.openlocfilehash: 3654c94975d16e35d5c3d8e762730d17509a2c6d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788884"
---
# <a name="icordebugdatatargetgetplatform-method"></a><span data-ttu-id="cd1d8-102">Metodo ICorDebugDataTarget::GetPlatform</span><span class="sxs-lookup"><span data-stu-id="cd1d8-102">ICorDebugDataTarget::GetPlatform Method</span></span>
<span data-ttu-id="cd1d8-103">Fornisce informazioni sulla piattaforma, tra cui l'architettura del processore e il sistema operativo in cui è in esecuzione il processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="cd1d8-103">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd1d8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cd1d8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd1d8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cd1d8-105">Parameters</span></span>  
 `pTargetPlatform`  
 <span data-ttu-id="cd1d8-106">out Puntatore a un'enumerazione [CorDebugPlatformEnum](cordebugplatform-enumeration.md) che descrive la piattaforma di destinazione.</span><span class="sxs-lookup"><span data-stu-id="cd1d8-106">[out] A pointer to a [CorDebugPlatformEnum](cordebugplatform-enumeration.md) enumeration that describes the target platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd1d8-107">Note</span><span class="sxs-lookup"><span data-stu-id="cd1d8-107">Remarks</span></span>  
 <span data-ttu-id="cd1d8-108">Il valore restituito dell'enumerazione `CorDebugPlatformEnum` viene utilizzato dall'interfaccia [ICorDebug](icordebug-interface.md) per determinare i dettagli del processo di destinazione, ad esempio le dimensioni del puntatore, il layout dello spazio degli indirizzi, il set di registri, il formato di istruzione, il layout del contesto e le convenzioni di chiamata.</span><span class="sxs-lookup"><span data-stu-id="cd1d8-108">The `CorDebugPlatformEnum` enumeration return value is used by the [ICorDebug](icordebug-interface.md) interface to determine details of the target process such as its pointer size, address space layout, register set, instruction format, context layout, and calling conventions.</span></span>  
  
 <span data-ttu-id="cd1d8-109">Il valore `pTargetPlatform` può fare riferimento a una piattaforma da emulare per la destinazione invece di specificare l'hardware effettivo in uso.</span><span class="sxs-lookup"><span data-stu-id="cd1d8-109">The `pTargetPlatform` value may refer to a platform that is being emulated for the target instead of specifying the actual hardware in use.</span></span> <span data-ttu-id="cd1d8-110">Ad esempio, un processo in esecuzione nell'ambiente Windows in Windows (WOW) in un'edizione a 64 bit del sistema operativo Windows deve usare il valore `CORDB_PLATFORM_WINDOWS_X86` dell'enumerazione [CorDebugPlatformEnum](cordebugplatform-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="cd1d8-110">For example, a process that is running in the Windows on Windows (WOW) environment on a 64-bit edition of the Windows operating system should use the `CORDB_PLATFORM_WINDOWS_X86` value of the [CorDebugPlatformEnum](cordebugplatform-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="cd1d8-111">Questo metodo deve avere esito positivo.</span><span class="sxs-lookup"><span data-stu-id="cd1d8-111">This method must succeed.</span></span> <span data-ttu-id="cd1d8-112">In caso di errore, la piattaforma di destinazione è inutilizzabile.</span><span class="sxs-lookup"><span data-stu-id="cd1d8-112">If it fails, the target platform is unusable.</span></span> <span data-ttu-id="cd1d8-113">Il metodo può non riuscire per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cd1d8-113">The method may fail for the following reasons:</span></span>  
  
- <span data-ttu-id="cd1d8-114">La piattaforma da emulare per la destinazione è inutilizzabile.</span><span class="sxs-lookup"><span data-stu-id="cd1d8-114">The platform that is being emulated for the target is unusable.</span></span>  
  
- <span data-ttu-id="cd1d8-115">L'hardware effettivo nella piattaforma di destinazione è inutilizzabile.</span><span class="sxs-lookup"><span data-stu-id="cd1d8-115">The actual hardware on the target platform is unusable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd1d8-116">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="cd1d8-116">Requirements</span></span>  
 <span data-ttu-id="cd1d8-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd1d8-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd1d8-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd1d8-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd1d8-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd1d8-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd1d8-120">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd1d8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd1d8-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd1d8-121">See also</span></span>

- [<span data-ttu-id="cd1d8-122">Interfaccia ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="cd1d8-122">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="cd1d8-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="cd1d8-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="cd1d8-124">Debug</span><span class="sxs-lookup"><span data-stu-id="cd1d8-124">Debugging</span></span>](index.md)
