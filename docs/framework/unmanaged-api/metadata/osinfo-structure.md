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
ms.openlocfilehash: 0aba49fb4a60b2e471c541a8d8531a1cbc8627f9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096199"
---
# <a name="osinfo-structure"></a><span data-ttu-id="62f22-102">Struttura OSINFO</span><span class="sxs-lookup"><span data-stu-id="62f22-102">OSINFO Structure</span></span>
<span data-ttu-id="62f22-103">Contiene i dettagli sul sistema operativo per un assembly o un modulo.</span><span class="sxs-lookup"><span data-stu-id="62f22-103">Contains details about the operating system for an assembly or module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62f22-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="62f22-104">Syntax</span></span>  
  
```  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;   
    DWORD   dwOSMinorVersion;   
} OSINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="62f22-105">Membri</span><span class="sxs-lookup"><span data-stu-id="62f22-105">Members</span></span>  
  
|<span data-ttu-id="62f22-106">Member</span><span class="sxs-lookup"><span data-stu-id="62f22-106">Member</span></span>|<span data-ttu-id="62f22-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="62f22-107">Description</span></span>|  
|------------|-----------------|  
|`dwOSPlatformId`|<span data-ttu-id="62f22-108">Uno dei valori identificatore definiti dalla funzione della piattaforma Microsoft Windows `GetVersionEx`.</span><span class="sxs-lookup"><span data-stu-id="62f22-108">One of the identifier values defined by the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="62f22-109">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="62f22-109">The following values are supported:</span></span><br /><br /> <span data-ttu-id="62f22-110">-VER_PLATFORM_WIN32s, o a 0x0000, specificare Microsoft Windows 3.1.</span><span class="sxs-lookup"><span data-stu-id="62f22-110">-   VER_PLATFORM_WIN32s, or 0x0000, to specify Microsoft Windows 3.1.</span></span><br /><span data-ttu-id="62f22-111">-VER_PLATFORM_WIN32_WINDOWS, o 0x0001, per specificare Windows 95, Windows 98 o discendenti da essi i sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="62f22-111">-   VER_PLATFORM_WIN32_WINDOWS, or 0x0001, to specify Windows 95, Windows 98, or operating systems descended from them.</span></span><br /><span data-ttu-id="62f22-112">-VER_PLATFORM_WIN32_NT, o 0x0010, per specificare i sistemi operativi o Windows NT che derivano da essa.</span><span class="sxs-lookup"><span data-stu-id="62f22-112">-   VER_PLATFORM_WIN32_NT, or 0x0010, to specify Windows NT or operating systems descended from it.</span></span>|  
|`dwOSMajorVersion`|<span data-ttu-id="62f22-113">La versione principale del sistema operativo o un valore NULL per indicare tutte le versioni.</span><span class="sxs-lookup"><span data-stu-id="62f22-113">The operating system major version, or a NULL value to indicate any version.</span></span>|  
|`dwOSMinorVersion`|<span data-ttu-id="62f22-114">La versione secondaria del sistema operativo o un valore NULL per indicare tutte le versioni.</span><span class="sxs-lookup"><span data-stu-id="62f22-114">The operating system minor version, or a NULL value to indicate any version.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62f22-115">Note</span><span class="sxs-lookup"><span data-stu-id="62f22-115">Remarks</span></span>  
 `OSINFO` <span data-ttu-id="62f22-116">basa il `OSVERSIONINFOEX` struttura usati nelle chiamate alla funzione della piattaforma Microsoft Windows `GetVersionEx`.</span><span class="sxs-lookup"><span data-stu-id="62f22-116">is based on the `OSVERSIONINFOEX` structure that is used in calls to the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="62f22-117">Questa struttura viene utilizzata dalla struttura ASSEMBLYMETADATA per indicare il supporto del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="62f22-117">This structure is used by the ASSEMBLYMETADATA structure to indicate its operating system support.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62f22-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="62f22-118">Requirements</span></span>  
 <span data-ttu-id="62f22-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62f22-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62f22-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="62f22-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="62f22-121">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="62f22-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="62f22-122">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="62f22-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="62f22-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62f22-123">See also</span></span>

- [<span data-ttu-id="62f22-124">Strutture di metadati</span><span class="sxs-lookup"><span data-stu-id="62f22-124">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="62f22-125">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="62f22-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
