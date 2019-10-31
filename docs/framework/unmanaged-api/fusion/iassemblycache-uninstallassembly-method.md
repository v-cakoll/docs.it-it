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
ms.openlocfilehash: 539a8edf6d7248235a6e672edc9464679a2eab82
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134503"
---
# <a name="iassemblycacheuninstallassembly-method"></a><span data-ttu-id="7bc3d-102">Metodo IAssemblyCache::UninstallAssembly</span><span class="sxs-lookup"><span data-stu-id="7bc3d-102">IAssemblyCache::UninstallAssembly Method</span></span>
<span data-ttu-id="7bc3d-103">Disinstalla l'assembly specificato dal Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="7bc3d-103">Uninstalls the specified assembly from the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bc3d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7bc3d-104">Syntax</span></span>  
  
```cpp  
HRESULT UninstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData,  
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bc3d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7bc3d-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="7bc3d-106">in Flag definiti in Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="7bc3d-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="7bc3d-107">in Nome dell'assembly da disinstallare.</span><span class="sxs-lookup"><span data-stu-id="7bc3d-107">[in] The name of the assembly to uninstall.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="7bc3d-108">in Struttura [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) che contiene i dati di installazione per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="7bc3d-108">[in] A [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure that contains the installation data for the assembly.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="7bc3d-109">[out, facoltativo] Uno dei valori di disposizione definiti in Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="7bc3d-109">[out, optional] One of the disposition values defined in Fusion.idl.</span></span> <span data-ttu-id="7bc3d-110">I valori possibili sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="7bc3d-110">Possible values include the following:</span></span>  
  
- <span data-ttu-id="7bc3d-111">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span><span class="sxs-lookup"><span data-stu-id="7bc3d-111">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span></span>  
  
- <span data-ttu-id="7bc3d-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span><span class="sxs-lookup"><span data-stu-id="7bc3d-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span></span>  
  
- <span data-ttu-id="7bc3d-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span><span class="sxs-lookup"><span data-stu-id="7bc3d-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span></span>  
  
- <span data-ttu-id="7bc3d-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span><span class="sxs-lookup"><span data-stu-id="7bc3d-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span></span>  
  
- <span data-ttu-id="7bc3d-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span><span class="sxs-lookup"><span data-stu-id="7bc3d-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span></span>  
  
- <span data-ttu-id="7bc3d-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span><span class="sxs-lookup"><span data-stu-id="7bc3d-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bc3d-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7bc3d-117">Requirements</span></span>  
 <span data-ttu-id="7bc3d-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7bc3d-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bc3d-119">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="7bc3d-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7bc3d-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bc3d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bc3d-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bc3d-121">See also</span></span>

- [<span data-ttu-id="7bc3d-122">Interfaccia IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="7bc3d-122">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
