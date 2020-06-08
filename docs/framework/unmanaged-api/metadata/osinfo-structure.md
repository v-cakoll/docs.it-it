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
ms.openlocfilehash: ab9d7eb6f5760b43fe805443bbe1ea4a95c72069
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501066"
---
# <a name="osinfo-structure"></a><span data-ttu-id="5de2e-102">Struttura OSINFO</span><span class="sxs-lookup"><span data-stu-id="5de2e-102">OSINFO Structure</span></span>
<span data-ttu-id="5de2e-103">Contiene informazioni dettagliate sul sistema operativo per un assembly o un modulo.</span><span class="sxs-lookup"><span data-stu-id="5de2e-103">Contains details about the operating system for an assembly or module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5de2e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5de2e-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;
    DWORD   dwOSMinorVersion;
} OSINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="5de2e-105">Membri</span><span class="sxs-lookup"><span data-stu-id="5de2e-105">Members</span></span>  
  
|<span data-ttu-id="5de2e-106">Membro</span><span class="sxs-lookup"><span data-stu-id="5de2e-106">Member</span></span>|<span data-ttu-id="5de2e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5de2e-107">Description</span></span>|  
|------------|-----------------|  
|`dwOSPlatformId`|<span data-ttu-id="5de2e-108">Uno dei valori dell'identificatore definito dalla funzione della piattaforma Microsoft Windows `GetVersionEx` .</span><span class="sxs-lookup"><span data-stu-id="5de2e-108">One of the identifier values defined by the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="5de2e-109">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="5de2e-109">The following values are supported:</span></span><br /><br /> <span data-ttu-id="5de2e-110">-VER_PLATFORM_WIN32s, o 0x0000, per specificare Microsoft Windows 3,1.</span><span class="sxs-lookup"><span data-stu-id="5de2e-110">-   VER_PLATFORM_WIN32s, or 0x0000, to specify Microsoft Windows 3.1.</span></span><br /><span data-ttu-id="5de2e-111">-VER_PLATFORM_WIN32_WINDOWS, o 0x0001, per specificare Windows 95, Windows 98 o i sistemi operativi discendenti da essi.</span><span class="sxs-lookup"><span data-stu-id="5de2e-111">-   VER_PLATFORM_WIN32_WINDOWS, or 0x0001, to specify Windows 95, Windows 98, or operating systems descended from them.</span></span><br /><span data-ttu-id="5de2e-112">-VER_PLATFORM_WIN32_NT, o 0x0002, per specificare Windows NT o i sistemi operativi derivati da esso.</span><span class="sxs-lookup"><span data-stu-id="5de2e-112">-   VER_PLATFORM_WIN32_NT, or 0x0002, to specify Windows NT or operating systems descended from it.</span></span>|  
|`dwOSMajorVersion`|<span data-ttu-id="5de2e-113">La versione principale del sistema operativo o un valore NULL per indicare qualsiasi versione.</span><span class="sxs-lookup"><span data-stu-id="5de2e-113">The operating system major version, or a NULL value to indicate any version.</span></span>|  
|`dwOSMinorVersion`|<span data-ttu-id="5de2e-114">La versione secondaria del sistema operativo o un valore NULL per indicare qualsiasi versione.</span><span class="sxs-lookup"><span data-stu-id="5de2e-114">The operating system minor version, or a NULL value to indicate any version.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5de2e-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5de2e-115">Remarks</span></span>  
 <span data-ttu-id="5de2e-116">`OSINFO`è basato sulla `OSVERSIONINFOEX` struttura utilizzata nelle chiamate alla funzione della piattaforma Microsoft Windows `GetVersionEx` .</span><span class="sxs-lookup"><span data-stu-id="5de2e-116">`OSINFO` is based on the `OSVERSIONINFOEX` structure that is used in calls to the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="5de2e-117">Questa struttura viene utilizzata dalla struttura ASSEMBLYMETADATA per indicare il relativo supporto del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5de2e-117">This structure is used by the ASSEMBLYMETADATA structure to indicate its operating system support.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5de2e-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5de2e-118">Requirements</span></span>  
 <span data-ttu-id="5de2e-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5de2e-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5de2e-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5de2e-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5de2e-121">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5de2e-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5de2e-122">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5de2e-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5de2e-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5de2e-123">See also</span></span>

- [<span data-ttu-id="5de2e-124">Strutture di metadati</span><span class="sxs-lookup"><span data-stu-id="5de2e-124">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="5de2e-125">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="5de2e-125">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
