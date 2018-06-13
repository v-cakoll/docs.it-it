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
ms.openlocfilehash: 6c5bc63da7ebe86b653c9bef7caeb1cf28d3a7f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450050"
---
# <a name="osinfo-structure"></a><span data-ttu-id="e4683-102">Struttura OSINFO</span><span class="sxs-lookup"><span data-stu-id="e4683-102">OSINFO Structure</span></span>
<span data-ttu-id="e4683-103">Contiene i dettagli sul sistema operativo per un assembly o un modulo.</span><span class="sxs-lookup"><span data-stu-id="e4683-103">Contains details about the operating system for an assembly or module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4683-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e4683-104">Syntax</span></span>  
  
```  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;   
    DWORD   dwOSMinorVersion;   
} OSINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="e4683-105">Membri</span><span class="sxs-lookup"><span data-stu-id="e4683-105">Members</span></span>  
  
|<span data-ttu-id="e4683-106">Membro</span><span class="sxs-lookup"><span data-stu-id="e4683-106">Member</span></span>|<span data-ttu-id="e4683-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e4683-107">Description</span></span>|  
|------------|-----------------|  
|`dwOSPlatformId`|<span data-ttu-id="e4683-108">Uno dei valori di identificatore definiti dalla funzione piattaforma Microsoft Windows `GetVersionEx`.</span><span class="sxs-lookup"><span data-stu-id="e4683-108">One of the identifier values defined by the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="e4683-109">Sono supportati i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="e4683-109">The following values are supported:</span></span><br /><br /> <span data-ttu-id="e4683-110">-VER_PLATFORM_WIN32s, o 0x0000 per specificare Microsoft Windows 3.1.</span><span class="sxs-lookup"><span data-stu-id="e4683-110">-   VER_PLATFORM_WIN32s, or 0x0000, to specify Microsoft Windows 3.1.</span></span><br /><span data-ttu-id="e4683-111">-VER_PLATFORM_WIN32_WINDOWS, o 0x0001 per specificare Windows 95, Windows 98 o sistemi operativi discendenti.</span><span class="sxs-lookup"><span data-stu-id="e4683-111">-   VER_PLATFORM_WIN32_WINDOWS, or 0x0001, to specify Windows 95, Windows 98, or operating systems descended from them.</span></span><br /><span data-ttu-id="e4683-112">-VER_PLATFORM_WIN32_NT, o 0x0010 per specificare i sistemi operativi o Windows NT discendenti.</span><span class="sxs-lookup"><span data-stu-id="e4683-112">-   VER_PLATFORM_WIN32_NT, or 0x0010, to specify Windows NT or operating systems descended from it.</span></span>|  
|`dwOSMajorVersion`|<span data-ttu-id="e4683-113">La versione principale sistema operativo, o un valore NULL per indicare qualsiasi versione.</span><span class="sxs-lookup"><span data-stu-id="e4683-113">The operating system major version, or a NULL value to indicate any version.</span></span>|  
|`dwOSMinorVersion`|<span data-ttu-id="e4683-114">La versione secondaria del sistema operativo, o un valore NULL per indicare qualsiasi versione.</span><span class="sxs-lookup"><span data-stu-id="e4683-114">The operating system minor version, or a NULL value to indicate any version.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4683-115">Note</span><span class="sxs-lookup"><span data-stu-id="e4683-115">Remarks</span></span>  
 <span data-ttu-id="e4683-116">`OSINFO` basa il `OSVERSIONINFOEX` struttura usati nelle chiamate alla funzione della piattaforma Microsoft Windows `GetVersionEx`.</span><span class="sxs-lookup"><span data-stu-id="e4683-116">`OSINFO` is based on the `OSVERSIONINFOEX` structure that is used in calls to the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="e4683-117">Questa struttura è utilizzata dalla struttura ASSEMBLYMETADATA per indicare il supporto del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e4683-117">This structure is used by the ASSEMBLYMETADATA structure to indicate its operating system support.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4683-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e4683-118">Requirements</span></span>  
 <span data-ttu-id="e4683-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4683-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4683-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e4683-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e4683-121">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e4683-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e4683-122">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4683-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4683-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4683-123">See Also</span></span>  
 [<span data-ttu-id="e4683-124">Strutture di metadati</span><span class="sxs-lookup"><span data-stu-id="e4683-124">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [<span data-ttu-id="e4683-125">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="e4683-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
