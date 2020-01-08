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
ms.openlocfilehash: d66e9bc3a027610d917e15dc9769b92ea1c5fb71
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345594"
---
# <a name="osinfo-structure"></a><span data-ttu-id="981c5-102">Struttura OSINFO</span><span class="sxs-lookup"><span data-stu-id="981c5-102">OSINFO Structure</span></span>
<span data-ttu-id="981c5-103">Contiene informazioni dettagliate sul sistema operativo per un assembly o un modulo.</span><span class="sxs-lookup"><span data-stu-id="981c5-103">Contains details about the operating system for an assembly or module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="981c5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="981c5-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;   
    DWORD   dwOSMinorVersion;   
} OSINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="981c5-105">Membri</span><span class="sxs-lookup"><span data-stu-id="981c5-105">Members</span></span>  
  
|<span data-ttu-id="981c5-106">Member</span><span class="sxs-lookup"><span data-stu-id="981c5-106">Member</span></span>|<span data-ttu-id="981c5-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="981c5-107">Description</span></span>|  
|------------|-----------------|  
|`dwOSPlatformId`|<span data-ttu-id="981c5-108">Uno dei valori dell'identificatore definito dalla funzione della piattaforma Microsoft Windows `GetVersionEx`.</span><span class="sxs-lookup"><span data-stu-id="981c5-108">One of the identifier values defined by the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="981c5-109">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="981c5-109">The following values are supported:</span></span><br /><br /> <span data-ttu-id="981c5-110">-VER_PLATFORM_WIN32s, o 0x0000, per specificare Microsoft Windows 3,1.</span><span class="sxs-lookup"><span data-stu-id="981c5-110">-   VER_PLATFORM_WIN32s, or 0x0000, to specify Microsoft Windows 3.1.</span></span><br /><span data-ttu-id="981c5-111">-VER_PLATFORM_WIN32_WINDOWS, o 0x0001, per specificare Windows 95, Windows 98 o i sistemi operativi discendenti da essi.</span><span class="sxs-lookup"><span data-stu-id="981c5-111">-   VER_PLATFORM_WIN32_WINDOWS, or 0x0001, to specify Windows 95, Windows 98, or operating systems descended from them.</span></span><br /><span data-ttu-id="981c5-112">-VER_PLATFORM_WIN32_NT, o 0x0002, per specificare Windows NT o i sistemi operativi derivati da esso.</span><span class="sxs-lookup"><span data-stu-id="981c5-112">-   VER_PLATFORM_WIN32_NT, or 0x0002, to specify Windows NT or operating systems descended from it.</span></span>|  
|`dwOSMajorVersion`|<span data-ttu-id="981c5-113">La versione principale del sistema operativo o un valore NULL per indicare qualsiasi versione.</span><span class="sxs-lookup"><span data-stu-id="981c5-113">The operating system major version, or a NULL value to indicate any version.</span></span>|  
|`dwOSMinorVersion`|<span data-ttu-id="981c5-114">La versione secondaria del sistema operativo o un valore NULL per indicare qualsiasi versione.</span><span class="sxs-lookup"><span data-stu-id="981c5-114">The operating system minor version, or a NULL value to indicate any version.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="981c5-115">Note</span><span class="sxs-lookup"><span data-stu-id="981c5-115">Remarks</span></span>  
 <span data-ttu-id="981c5-116">`OSINFO` è basato sulla struttura di `OSVERSIONINFOEX` utilizzata nelle chiamate alla funzione della piattaforma Microsoft Windows `GetVersionEx`.</span><span class="sxs-lookup"><span data-stu-id="981c5-116">`OSINFO` is based on the `OSVERSIONINFOEX` structure that is used in calls to the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="981c5-117">Questa struttura viene utilizzata dalla struttura ASSEMBLYMETADATA per indicare il relativo supporto del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="981c5-117">This structure is used by the ASSEMBLYMETADATA structure to indicate its operating system support.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="981c5-118">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="981c5-118">Requirements</span></span>  
 <span data-ttu-id="981c5-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="981c5-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="981c5-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="981c5-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="981c5-121">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="981c5-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="981c5-122">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="981c5-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="981c5-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="981c5-123">See also</span></span>

- [<span data-ttu-id="981c5-124">Strutture di metadati</span><span class="sxs-lookup"><span data-stu-id="981c5-124">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="981c5-125">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="981c5-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
