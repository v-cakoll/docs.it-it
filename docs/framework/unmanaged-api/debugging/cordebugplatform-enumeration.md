---
title: Enumerazione CorDebugPlatform
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugPlatformEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugPlatformEnum
helpviewer_keywords: CorDebugPlatformEnum enumeration [.NET Framework debugging]
ms.assetid: c5444816-7378-4521-afd3-bf5e4b5303d5
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 52842d40895a658ec9dbb1263f18c48ec999a0ef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugplatform-enumeration"></a><span data-ttu-id="f2902-102">Enumerazione CorDebugPlatform</span><span class="sxs-lookup"><span data-stu-id="f2902-102">CorDebugPlatform Enumeration</span></span>
<span data-ttu-id="f2902-103">Fornisce i valori di piattaforma di destinazione vengono utilizzati dal [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="f2902-103">Provides target platform values that are used by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2902-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f2902-104">Syntax</span></span>  
  
```  
typedef enum CorDebugPlatform  
{  
    CORDB_PLATFORM_WINDOWS_X86,    // Windows on Intel x86  
    CORDB_PLATFORM_WINDOWS_AMD64,  // Windows x64 (AMD64, Intel EM64T)  
    CORDB_PLATFORM_WINDOWS_IA64,   // Windows on Intel IA-64  
    CORDB_PLATFORM_MAC_PPC,        // Macintosh OS on PowerPC  
    CORDB_PLATFORM_MAC_X86,        // Macintosh OS on Intel x86  
    CORDB_PLATFORM_WINDOWS_ARM,    // Windows on ARM  
    CORDB_PLATFORM_MAC_AMD64       // MacOS on Intel x64  
} CorDebugPlatform;  
```  
  
## <a name="members"></a><span data-ttu-id="f2902-105">Membri</span><span class="sxs-lookup"><span data-stu-id="f2902-105">Members</span></span>  
  
|<span data-ttu-id="f2902-106">Membro</span><span class="sxs-lookup"><span data-stu-id="f2902-106">Member</span></span>|<span data-ttu-id="f2902-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2902-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="f2902-108">CORDB_PLATFORM_WINDOWS_X86</span><span class="sxs-lookup"><span data-stu-id="f2902-108">CORDB_PLATFORM_WINDOWS_X86</span></span>|<span data-ttu-id="f2902-109">La piattaforma di destinazione è Windows in esecuzione su hardware Intel x86.</span><span class="sxs-lookup"><span data-stu-id="f2902-109">The target platform is Windows running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="f2902-110">CORDB_PLATFORM_WINDOWS_AMD64</span><span class="sxs-lookup"><span data-stu-id="f2902-110">CORDB_PLATFORM_WINDOWS_AMD64</span></span>|<span data-ttu-id="f2902-111">La piattaforma di destinazione è Windows a 64 bit in esecuzione su hardware AMD64 o Intel EM64T.</span><span class="sxs-lookup"><span data-stu-id="f2902-111">The target platform is 64 bit Windows running on AMD64 or Intel EM64T hardware.</span></span>|  
|<span data-ttu-id="f2902-112">CORDB_PLATFORM_WINDOWS_IA64</span><span class="sxs-lookup"><span data-stu-id="f2902-112">CORDB_PLATFORM_WINDOWS_IA64</span></span>|<span data-ttu-id="f2902-113">La piattaforma di destinazione è Windows a 32 bit in esecuzione su hardware Intel IA64.</span><span class="sxs-lookup"><span data-stu-id="f2902-113">The target platform is 32 bit Windows running on Intel IA-64 hardware.</span></span>|  
|<span data-ttu-id="f2902-114">CORDB_PLATFORM_MAC_PPC</span><span class="sxs-lookup"><span data-stu-id="f2902-114">CORDB_PLATFORM_MAC_PPC</span></span>|<span data-ttu-id="f2902-115">La piattaforma di destinazione è il sistema operativo Macintosh in esecuzione su hardware PowerPC.</span><span class="sxs-lookup"><span data-stu-id="f2902-115">The target platform is the Macintosh operating system running on PowerPC hardware.</span></span>|  
|<span data-ttu-id="f2902-116">CORDB_PLATFORM_MAC_X86</span><span class="sxs-lookup"><span data-stu-id="f2902-116">CORDB_PLATFORM_MAC_X86</span></span>|<span data-ttu-id="f2902-117">La piattaforma di destinazione è il sistema operativo Macintosh in esecuzione su hardware Intel x86.</span><span class="sxs-lookup"><span data-stu-id="f2902-117">The target platform is the Macintosh operating system running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="f2902-118">CORDB_PLATFORM_WINDOWS_ARM</span><span class="sxs-lookup"><span data-stu-id="f2902-118">CORDB_PLATFORM_WINDOWS_ARM</span></span>|<span data-ttu-id="f2902-119">La piattaforma di destinazione è il sistema operativo Macintosh in esecuzione su hardware Windows ARM.</span><span class="sxs-lookup"><span data-stu-id="f2902-119">The target platform is the Macintosh operating system running on Windows ARM hardware.</span></span>|  
|<span data-ttu-id="f2902-120">CORDB_PLATFORM_MAC_AMD64</span><span class="sxs-lookup"><span data-stu-id="f2902-120">CORDB_PLATFORM_MAC_AMD64</span></span>|<span data-ttu-id="f2902-121">La piattaforma di destinazione è il sistema operativo Macintosh in esecuzione su hardware AMD64.</span><span class="sxs-lookup"><span data-stu-id="f2902-121">The target platform is the Macintosh operating system running on AMD64 hardware.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f2902-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f2902-122">Requirements</span></span>  
 <span data-ttu-id="f2902-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2902-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2902-124">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="f2902-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2902-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2902-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2902-126">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2902-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
 <span data-ttu-id="f2902-127">I membri `CORDB_PLATFORM_WINDOWS_ARM` e `CORDB_PLATFORM_MAC_AMD64` sono disponibili in .NET Framework 4.5.2 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="f2902-127">The `CORDB_PLATFORM_WINDOWS_ARM` and `CORDB_PLATFORM_MAC_AMD64` members are available in the .NET Framework 4.5.2 and later versions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2902-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2902-128">See Also</span></span>  
 [<span data-ttu-id="f2902-129">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="f2902-129">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
