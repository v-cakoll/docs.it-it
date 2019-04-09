---
title: Enumerazione CorDebugPlatform
ms.date: 03/30/2017
api_name:
- CorDebugPlatformEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugPlatformEnum
helpviewer_keywords:
- CorDebugPlatformEnum enumeration [.NET Framework debugging]
ms.assetid: c5444816-7378-4521-afd3-bf5e4b5303d5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03b6f1b29157889d0e84e5dddc94d5e3ae27efce
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180940"
---
# <a name="cordebugplatform-enumeration"></a><span data-ttu-id="3aee1-102">Enumerazione CorDebugPlatform</span><span class="sxs-lookup"><span data-stu-id="3aee1-102">CorDebugPlatform Enumeration</span></span>
<span data-ttu-id="3aee1-103">Fornisce i valori di piattaforma di destinazione utilizzati per il [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="3aee1-103">Provides target platform values that are used by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3aee1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3aee1-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="3aee1-105">Membri</span><span class="sxs-lookup"><span data-stu-id="3aee1-105">Members</span></span>  
  
|<span data-ttu-id="3aee1-106">Member</span><span class="sxs-lookup"><span data-stu-id="3aee1-106">Member</span></span>|<span data-ttu-id="3aee1-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3aee1-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="3aee1-108">CORDB_PLATFORM_WINDOWS_X86</span><span class="sxs-lookup"><span data-stu-id="3aee1-108">CORDB_PLATFORM_WINDOWS_X86</span></span>|<span data-ttu-id="3aee1-109">La piattaforma di destinazione è Windows in esecuzione su hardware Intel x86.</span><span class="sxs-lookup"><span data-stu-id="3aee1-109">The target platform is Windows running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="3aee1-110">CORDB_PLATFORM_WINDOWS_AMD64</span><span class="sxs-lookup"><span data-stu-id="3aee1-110">CORDB_PLATFORM_WINDOWS_AMD64</span></span>|<span data-ttu-id="3aee1-111">La piattaforma di destinazione è Windows a 64 bit in esecuzione su hardware AMD64 o Intel EM64T.</span><span class="sxs-lookup"><span data-stu-id="3aee1-111">The target platform is 64 bit Windows running on AMD64 or Intel EM64T hardware.</span></span>|  
|<span data-ttu-id="3aee1-112">CORDB_PLATFORM_WINDOWS_IA64</span><span class="sxs-lookup"><span data-stu-id="3aee1-112">CORDB_PLATFORM_WINDOWS_IA64</span></span>|<span data-ttu-id="3aee1-113">La piattaforma di destinazione è Windows a 32 bit in esecuzione su hardware Intel IA64.</span><span class="sxs-lookup"><span data-stu-id="3aee1-113">The target platform is 32 bit Windows running on Intel IA-64 hardware.</span></span>|  
|<span data-ttu-id="3aee1-114">CORDB_PLATFORM_MAC_PPC</span><span class="sxs-lookup"><span data-stu-id="3aee1-114">CORDB_PLATFORM_MAC_PPC</span></span>|<span data-ttu-id="3aee1-115">La piattaforma di destinazione è il sistema operativo Macintosh in esecuzione su hardware PowerPC.</span><span class="sxs-lookup"><span data-stu-id="3aee1-115">The target platform is the Macintosh operating system running on PowerPC hardware.</span></span>|  
|<span data-ttu-id="3aee1-116">CORDB_PLATFORM_MAC_X86</span><span class="sxs-lookup"><span data-stu-id="3aee1-116">CORDB_PLATFORM_MAC_X86</span></span>|<span data-ttu-id="3aee1-117">La piattaforma di destinazione è il sistema operativo Macintosh in esecuzione su hardware Intel x86.</span><span class="sxs-lookup"><span data-stu-id="3aee1-117">The target platform is the Macintosh operating system running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="3aee1-118">CORDB_PLATFORM_WINDOWS_ARM</span><span class="sxs-lookup"><span data-stu-id="3aee1-118">CORDB_PLATFORM_WINDOWS_ARM</span></span>|<span data-ttu-id="3aee1-119">La piattaforma di destinazione è il sistema operativo Macintosh in esecuzione su hardware di Windows ARM.</span><span class="sxs-lookup"><span data-stu-id="3aee1-119">The target platform is the Macintosh operating system running on Windows ARM hardware.</span></span>|  
|<span data-ttu-id="3aee1-120">CORDB_PLATFORM_MAC_AMD64</span><span class="sxs-lookup"><span data-stu-id="3aee1-120">CORDB_PLATFORM_MAC_AMD64</span></span>|<span data-ttu-id="3aee1-121">La piattaforma di destinazione è il sistema operativo Macintosh in esecuzione su hardware AMD64.</span><span class="sxs-lookup"><span data-stu-id="3aee1-121">The target platform is the Macintosh operating system running on AMD64 hardware.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3aee1-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3aee1-122">Requirements</span></span>  
 <span data-ttu-id="3aee1-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3aee1-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3aee1-124">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3aee1-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3aee1-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3aee1-125">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3aee1-126">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3aee1-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
 <span data-ttu-id="3aee1-127">I membri `CORDB_PLATFORM_WINDOWS_ARM` e `CORDB_PLATFORM_MAC_AMD64` sono disponibili in .NET Framework 4.5.2 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="3aee1-127">The `CORDB_PLATFORM_WINDOWS_ARM` and `CORDB_PLATFORM_MAC_AMD64` members are available in the .NET Framework 4.5.2 and later versions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aee1-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3aee1-128">See also</span></span>

- [<span data-ttu-id="3aee1-129">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="3aee1-129">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
