---
title: Struttura OSINFO
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: OSINFO
api_location: mscoree.dll
api_type: COM
f1_keywords: OSINFO
helpviewer_keywords: OSINFO structure [.NET Framework metadata]
ms.assetid: fac7b480-7adb-4450-a5e9-690fed81ffae
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 700e9bcfe33e5be3725bd24b212b3a77ad139b2c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="osinfo-structure"></a><span data-ttu-id="4f281-102">Struttura OSINFO</span><span class="sxs-lookup"><span data-stu-id="4f281-102">OSINFO Structure</span></span>
<span data-ttu-id="4f281-103">Contiene i dettagli sul sistema operativo per un assembly o un modulo.</span><span class="sxs-lookup"><span data-stu-id="4f281-103">Contains details about the operating system for an assembly or module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f281-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f281-104">Syntax</span></span>  
  
```  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;   
    DWORD   dwOSMinorVersion;   
} OSINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="4f281-105">Membri</span><span class="sxs-lookup"><span data-stu-id="4f281-105">Members</span></span>  
  
|<span data-ttu-id="4f281-106">Membro</span><span class="sxs-lookup"><span data-stu-id="4f281-106">Member</span></span>|<span data-ttu-id="4f281-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f281-107">Description</span></span>|  
|------------|-----------------|  
|`dwOSPlatformId`|<span data-ttu-id="4f281-108">Uno dei valori di identificatore definiti dalla funzione piattaforma Microsoft Windows `GetVersionEx`.</span><span class="sxs-lookup"><span data-stu-id="4f281-108">One of the identifier values defined by the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="4f281-109">Sono supportati i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="4f281-109">The following values are supported:</span></span><br /><br /> <span data-ttu-id="4f281-110">-VER_PLATFORM_WIN32s, o 0x0000 per specificare Microsoft Windows 3.1.</span><span class="sxs-lookup"><span data-stu-id="4f281-110">-   VER_PLATFORM_WIN32s, or 0x0000, to specify Microsoft Windows 3.1.</span></span><br /><span data-ttu-id="4f281-111">-VER_PLATFORM_WIN32_WINDOWS, o 0x0001 per specificare Windows 95, Windows 98 o sistemi operativi discendenti.</span><span class="sxs-lookup"><span data-stu-id="4f281-111">-   VER_PLATFORM_WIN32_WINDOWS, or 0x0001, to specify Windows 95, Windows 98, or operating systems descended from them.</span></span><br /><span data-ttu-id="4f281-112">-VER_PLATFORM_WIN32_NT, o 0x0010 per specificare i sistemi operativi o Windows NT discendenti.</span><span class="sxs-lookup"><span data-stu-id="4f281-112">-   VER_PLATFORM_WIN32_NT, or 0x0010, to specify Windows NT or operating systems descended from it.</span></span>|  
|`dwOSMajorVersion`|<span data-ttu-id="4f281-113">La versione principale sistema operativo, o un valore NULL per indicare qualsiasi versione.</span><span class="sxs-lookup"><span data-stu-id="4f281-113">The operating system major version, or a NULL value to indicate any version.</span></span>|  
|`dwOSMinorVersion`|<span data-ttu-id="4f281-114">La versione secondaria del sistema operativo, o un valore NULL per indicare qualsiasi versione.</span><span class="sxs-lookup"><span data-stu-id="4f281-114">The operating system minor version, or a NULL value to indicate any version.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f281-115">Note</span><span class="sxs-lookup"><span data-stu-id="4f281-115">Remarks</span></span>  
 <span data-ttu-id="4f281-116">`OSINFO`si basa sul `OSVERSIONINFOEX` struttura utilizzati nelle chiamate alla funzione piattaforma Microsoft Windows `GetVersionEx`.</span><span class="sxs-lookup"><span data-stu-id="4f281-116">`OSINFO` is based on the `OSVERSIONINFOEX` structure that is used in calls to the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="4f281-117">Questa struttura è utilizzata dalla struttura ASSEMBLYMETADATA per indicare il supporto del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="4f281-117">This structure is used by the ASSEMBLYMETADATA structure to indicate its operating system support.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f281-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4f281-118">Requirements</span></span>  
 <span data-ttu-id="4f281-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f281-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f281-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4f281-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4f281-121">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4f281-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4f281-122">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f281-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f281-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f281-123">See Also</span></span>  
 [<span data-ttu-id="4f281-124">Strutture di metadati</span><span class="sxs-lookup"><span data-stu-id="4f281-124">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [<span data-ttu-id="4f281-125">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="4f281-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
