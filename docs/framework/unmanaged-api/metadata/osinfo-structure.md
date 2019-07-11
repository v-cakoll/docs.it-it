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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a36cd3c5fb638799a735e4b4a1a98959500300b5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761592"
---
# <a name="osinfo-structure"></a><span data-ttu-id="5d5f5-102">Struttura OSINFO</span><span class="sxs-lookup"><span data-stu-id="5d5f5-102">OSINFO Structure</span></span>
<span data-ttu-id="5d5f5-103">Contiene i dettagli sul sistema operativo per un assembly o un modulo.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-103">Contains details about the operating system for an assembly or module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d5f5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5d5f5-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;   
    DWORD   dwOSMinorVersion;   
} OSINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="5d5f5-105">Members</span><span class="sxs-lookup"><span data-stu-id="5d5f5-105">Members</span></span>  
  
|<span data-ttu-id="5d5f5-106">Member</span><span class="sxs-lookup"><span data-stu-id="5d5f5-106">Member</span></span>|<span data-ttu-id="5d5f5-107">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="5d5f5-107">Description</span></span>|  
|------------|-----------------|  
|`dwOSPlatformId`|<span data-ttu-id="5d5f5-108">Uno dei valori identificatore definiti dalla funzione della piattaforma Microsoft Windows `GetVersionEx`.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-108">One of the identifier values defined by the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="5d5f5-109">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="5d5f5-109">The following values are supported:</span></span><br /><br /> <span data-ttu-id="5d5f5-110">-VER_PLATFORM_WIN32s, o a 0x0000, specificare Microsoft Windows 3.1.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-110">-   VER_PLATFORM_WIN32s, or 0x0000, to specify Microsoft Windows 3.1.</span></span><br /><span data-ttu-id="5d5f5-111">-VER_PLATFORM_WIN32_WINDOWS, o 0x0001, per specificare Windows 95, Windows 98 o discendenti da essi i sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-111">-   VER_PLATFORM_WIN32_WINDOWS, or 0x0001, to specify Windows 95, Windows 98, or operating systems descended from them.</span></span><br /><span data-ttu-id="5d5f5-112">-VER_PLATFORM_WIN32_NT, o 0x0010, per specificare i sistemi operativi o Windows NT che derivano da essa.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-112">-   VER_PLATFORM_WIN32_NT, or 0x0010, to specify Windows NT or operating systems descended from it.</span></span>|  
|`dwOSMajorVersion`|<span data-ttu-id="5d5f5-113">La versione principale del sistema operativo o un valore NULL per indicare tutte le versioni.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-113">The operating system major version, or a NULL value to indicate any version.</span></span>|  
|`dwOSMinorVersion`|<span data-ttu-id="5d5f5-114">La versione secondaria del sistema operativo o un valore NULL per indicare tutte le versioni.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-114">The operating system minor version, or a NULL value to indicate any version.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d5f5-115">Note</span><span class="sxs-lookup"><span data-stu-id="5d5f5-115">Remarks</span></span>  
 <span data-ttu-id="5d5f5-116">`OSINFO` basa il `OSVERSIONINFOEX` struttura usati nelle chiamate alla funzione della piattaforma Microsoft Windows `GetVersionEx`.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-116">`OSINFO` is based on the `OSVERSIONINFOEX` structure that is used in calls to the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="5d5f5-117">Questa struttura viene utilizzata dalla struttura ASSEMBLYMETADATA per indicare il supporto del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5d5f5-117">This structure is used by the ASSEMBLYMETADATA structure to indicate its operating system support.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d5f5-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5d5f5-118">Requirements</span></span>  
 <span data-ttu-id="5d5f5-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d5f5-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d5f5-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5d5f5-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5d5f5-121">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="5d5f5-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5d5f5-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d5f5-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d5f5-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d5f5-123">See also</span></span>

- [<span data-ttu-id="5d5f5-124">Strutture di metadati</span><span class="sxs-lookup"><span data-stu-id="5d5f5-124">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="5d5f5-125">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="5d5f5-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
