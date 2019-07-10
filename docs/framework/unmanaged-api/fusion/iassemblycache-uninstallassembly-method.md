---
title: Metodo IAssemblyCache::UninstallAssembly
ms.date: 03/30/2017
api_name:
- IAssemblyCache.UninstallAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::UninstallAssembly
helpviewer_keywords:
- UninstallAssembly method [.NET Framework fusion]
- IAssemblyCache::UninstallAssembly method [.NET Framework fusion]
ms.assetid: 973b2c44-8dfc-40c1-9035-10f4846627e9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 531f9167a931d6b972e47e120950197bed11c07e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778711"
---
# <a name="iassemblycacheuninstallassembly-method"></a><span data-ttu-id="d1a8f-102">Metodo IAssemblyCache::UninstallAssembly</span><span class="sxs-lookup"><span data-stu-id="d1a8f-102">IAssemblyCache::UninstallAssembly Method</span></span>
<span data-ttu-id="d1a8f-103">Disinstalla l'assembly specificato dalla global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="d1a8f-103">Uninstalls the specified assembly from the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1a8f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d1a8f-104">Syntax</span></span>  
  
```cpp  
HRESULT UninstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData,  
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1a8f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d1a8f-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="d1a8f-106">[in] Flag definiti in Fusion.</span><span class="sxs-lookup"><span data-stu-id="d1a8f-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="d1a8f-107">[in] Il nome dell'assembly da disinstallare.</span><span class="sxs-lookup"><span data-stu-id="d1a8f-107">[in] The name of the assembly to uninstall.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="d1a8f-108">[in] Oggetto [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) struttura che contiene i dati di installazione per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="d1a8f-108">[in] A [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure that contains the installation data for the assembly.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="d1a8f-109">[out, optional] Uno dei valori disposition definiti in Fusion.</span><span class="sxs-lookup"><span data-stu-id="d1a8f-109">[out, optional] One of the disposition values defined in Fusion.idl.</span></span> <span data-ttu-id="d1a8f-110">I valori possibili includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d1a8f-110">Possible values include the following:</span></span>  
  
- <span data-ttu-id="d1a8f-111">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span><span class="sxs-lookup"><span data-stu-id="d1a8f-111">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span></span>  
  
- <span data-ttu-id="d1a8f-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span><span class="sxs-lookup"><span data-stu-id="d1a8f-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span></span>  
  
- <span data-ttu-id="d1a8f-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span><span class="sxs-lookup"><span data-stu-id="d1a8f-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span></span>  
  
- <span data-ttu-id="d1a8f-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span><span class="sxs-lookup"><span data-stu-id="d1a8f-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span></span>  
  
- <span data-ttu-id="d1a8f-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span><span class="sxs-lookup"><span data-stu-id="d1a8f-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span></span>  
  
- <span data-ttu-id="d1a8f-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span><span class="sxs-lookup"><span data-stu-id="d1a8f-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1a8f-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d1a8f-117">Requirements</span></span>  
 <span data-ttu-id="d1a8f-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1a8f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1a8f-119">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="d1a8f-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d1a8f-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1a8f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1a8f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1a8f-121">See also</span></span>

- [<span data-ttu-id="d1a8f-122">Interfaccia IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="d1a8f-122">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
