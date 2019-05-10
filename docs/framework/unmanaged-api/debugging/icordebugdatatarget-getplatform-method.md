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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f0769f30b6ac166e065fb6299c61c1e71e402c49
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64607058"
---
# <a name="icordebugdatatargetgetplatform-method"></a><span data-ttu-id="0b802-102">Metodo ICorDebugDataTarget::GetPlatform</span><span class="sxs-lookup"><span data-stu-id="0b802-102">ICorDebugDataTarget::GetPlatform Method</span></span>
<span data-ttu-id="0b802-103">Fornisce informazioni sulla piattaforma, tra cui architettura del processore e del sistema operativo, in cui viene eseguito il processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0b802-103">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b802-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0b802-104">Syntax</span></span>  
  
```  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b802-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0b802-105">Parameters</span></span>  
 `pTargetPlatform`  
 <span data-ttu-id="0b802-106">[out] Un puntatore a un [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumerazione che descrive la piattaforma di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0b802-106">[out] A pointer to a [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumeration that describes the target platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b802-107">Note</span><span class="sxs-lookup"><span data-stu-id="0b802-107">Remarks</span></span>  
 <span data-ttu-id="0b802-108">Il `CorDebugPlatformEnum` valore restituito di enumerazione viene utilizzato per il [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interfaccia per determinare i dettagli del processo di destinazione, ad esempio le dimensioni del puntatore, layout dello spazio degli indirizzi, register set, formato dell'istruzione, layout di contesto, e convenzioni di chiamata.</span><span class="sxs-lookup"><span data-stu-id="0b802-108">The `CorDebugPlatformEnum` enumeration return value is used by the [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface to determine details of the target process such as its pointer size, address space layout, register set, instruction format, context layout, and calling conventions.</span></span>  
  
 <span data-ttu-id="0b802-109">Il `pTargetPlatform` valore può fare riferimento a una piattaforma che viene emulata per la destinazione anziché specificare l'hardware effettivamente in uso.</span><span class="sxs-lookup"><span data-stu-id="0b802-109">The `pTargetPlatform` value may refer to a platform that is being emulated for the target instead of specifying the actual hardware in use.</span></span> <span data-ttu-id="0b802-110">Ad esempio, un processo in esecuzione in di Windows nell'ambiente di Windows (WOW) in una versione a 64 bit del sistema operativo Windows deve usare la `CORDB_PLATFORM_WINDOWS_X86` pari al [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="0b802-110">For example, a process that is running in the Windows on Windows (WOW) environment on a 64-bit edition of the Windows operating system should use the `CORDB_PLATFORM_WINDOWS_X86` value of the [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="0b802-111">Questo metodo deve essere completata.</span><span class="sxs-lookup"><span data-stu-id="0b802-111">This method must succeed.</span></span> <span data-ttu-id="0b802-112">In caso contrario, la piattaforma di destinazione è inutilizzabile.</span><span class="sxs-lookup"><span data-stu-id="0b802-112">If it fails, the target platform is unusable.</span></span> <span data-ttu-id="0b802-113">Il metodo potrebbe non riuscire per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b802-113">The method may fail for the following reasons:</span></span>  
  
- <span data-ttu-id="0b802-114">La piattaforma che viene emulata per la destinazione è inutilizzabile.</span><span class="sxs-lookup"><span data-stu-id="0b802-114">The platform that is being emulated for the target is unusable.</span></span>  
  
- <span data-ttu-id="0b802-115">L'hardware effettivo nella piattaforma di destinazione è inutilizzabile.</span><span class="sxs-lookup"><span data-stu-id="0b802-115">The actual hardware on the target platform is unusable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b802-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0b802-116">Requirements</span></span>  
 <span data-ttu-id="0b802-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b802-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b802-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0b802-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0b802-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b802-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b802-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b802-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b802-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b802-121">See also</span></span>

- [<span data-ttu-id="0b802-122">Interfaccia ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="0b802-122">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="0b802-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="0b802-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="0b802-124">Debug</span><span class="sxs-lookup"><span data-stu-id="0b802-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
