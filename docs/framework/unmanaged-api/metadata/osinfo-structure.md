---
title: Struttura OSINFO
ms.date: 03/30/2017
api_name:
- OSINFO
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OSINFO
helpviewer_keywords:
- OSINFO structure [.NET Framework metadata]
ms.assetid: fac7b480-7adb-4450-a5e9-690fed81ffae
topic_type:
- apiref
ms.openlocfilehash: 89111bf7eb03d20c2010c7a20c4cd055c2a021e3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430728"
---
# <a name="osinfo-structure"></a><span data-ttu-id="77c64-102">Struttura OSINFO</span><span class="sxs-lookup"><span data-stu-id="77c64-102">OSINFO Structure</span></span>
<span data-ttu-id="77c64-103">Contains details about the operating system for an assembly or module.</span><span class="sxs-lookup"><span data-stu-id="77c64-103">Contains details about the operating system for an assembly or module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77c64-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="77c64-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;   
    DWORD   dwOSMinorVersion;   
} OSINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="77c64-105">Members</span><span class="sxs-lookup"><span data-stu-id="77c64-105">Members</span></span>  
  
|<span data-ttu-id="77c64-106">Member</span><span class="sxs-lookup"><span data-stu-id="77c64-106">Member</span></span>|<span data-ttu-id="77c64-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77c64-107">Description</span></span>|  
|------------|-----------------|  
|`dwOSPlatformId`|<span data-ttu-id="77c64-108">One of the identifier values defined by the Microsoft Windows platform function `GetVersionEx`.</span><span class="sxs-lookup"><span data-stu-id="77c64-108">One of the identifier values defined by the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="77c64-109">The following values are supported:</span><span class="sxs-lookup"><span data-stu-id="77c64-109">The following values are supported:</span></span><br /><br /> <span data-ttu-id="77c64-110">-   VER_PLATFORM_WIN32s, or 0x0000, to specify Microsoft Windows 3.1.</span><span class="sxs-lookup"><span data-stu-id="77c64-110">-   VER_PLATFORM_WIN32s, or 0x0000, to specify Microsoft Windows 3.1.</span></span><br /><span data-ttu-id="77c64-111">-   VER_PLATFORM_WIN32_WINDOWS, or 0x0001, to specify Windows 95, Windows 98, or operating systems descended from them.</span><span class="sxs-lookup"><span data-stu-id="77c64-111">-   VER_PLATFORM_WIN32_WINDOWS, or 0x0001, to specify Windows 95, Windows 98, or operating systems descended from them.</span></span><br /><span data-ttu-id="77c64-112">-   VER_PLATFORM_WIN32_NT, or 0x0010, to specify Windows NT or operating systems descended from it.</span><span class="sxs-lookup"><span data-stu-id="77c64-112">-   VER_PLATFORM_WIN32_NT, or 0x0010, to specify Windows NT or operating systems descended from it.</span></span>|  
|`dwOSMajorVersion`|<span data-ttu-id="77c64-113">The operating system major version, or a NULL value to indicate any version.</span><span class="sxs-lookup"><span data-stu-id="77c64-113">The operating system major version, or a NULL value to indicate any version.</span></span>|  
|`dwOSMinorVersion`|<span data-ttu-id="77c64-114">The operating system minor version, or a NULL value to indicate any version.</span><span class="sxs-lookup"><span data-stu-id="77c64-114">The operating system minor version, or a NULL value to indicate any version.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77c64-115">Note</span><span class="sxs-lookup"><span data-stu-id="77c64-115">Remarks</span></span>  
 <span data-ttu-id="77c64-116">`OSINFO` is based on the `OSVERSIONINFOEX` structure that is used in calls to the Microsoft Windows platform function `GetVersionEx`.</span><span class="sxs-lookup"><span data-stu-id="77c64-116">`OSINFO` is based on the `OSVERSIONINFOEX` structure that is used in calls to the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="77c64-117">This structure is used by the ASSEMBLYMETADATA structure to indicate its operating system support.</span><span class="sxs-lookup"><span data-stu-id="77c64-117">This structure is used by the ASSEMBLYMETADATA structure to indicate its operating system support.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77c64-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="77c64-118">Requirements</span></span>  
 <span data-ttu-id="77c64-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77c64-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77c64-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="77c64-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="77c64-121">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="77c64-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="77c64-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77c64-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77c64-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77c64-123">See also</span></span>

- [<span data-ttu-id="77c64-124">Strutture di metadati</span><span class="sxs-lookup"><span data-stu-id="77c64-124">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="77c64-125">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="77c64-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
