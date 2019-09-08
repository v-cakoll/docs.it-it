---
title: Metodo IAssemblyCache::InstallAssembly
ms.date: 03/30/2017
api_name:
- IAssemblyCache.InstallAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::InstallAssembly
helpviewer_keywords:
- InstallAssembly method [.NET Framework fusion]
- IAssemblyCache::InstallAssembly method [.NET Framework fusion]
ms.assetid: 33c1d269-c85e-4cb1-b0e6-1c510c8fb5fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95c65e73c118b5358ac0a92dd0a1ca5545558e73
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796797"
---
# <a name="iassemblycacheinstallassembly-method"></a><span data-ttu-id="cc74c-102">Metodo IAssemblyCache::InstallAssembly</span><span class="sxs-lookup"><span data-stu-id="cc74c-102">IAssemblyCache::InstallAssembly Method</span></span>
<span data-ttu-id="cc74c-103">Installa l'assembly specificato nel Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="cc74c-103">Installs the specified assembly in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc74c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cc74c-104">Syntax</span></span>  
  
```cpp  
HRESULT InstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszManifestFilePath,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc74c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cc74c-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="cc74c-106">in Flag definiti in Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="cc74c-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="cc74c-107">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc74c-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="cc74c-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="cc74c-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
- <span data-ttu-id="cc74c-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="cc74c-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pszManifestFilePath`  
 <span data-ttu-id="cc74c-110">in Percorso del manifesto per l'assembly da installare.</span><span class="sxs-lookup"><span data-stu-id="cc74c-110">[in] The path to the manifest for the assembly to install.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="cc74c-111">in Struttura [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) che contiene i dati per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="cc74c-111">[in] A [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure that contains data for the installation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc74c-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cc74c-112">Requirements</span></span>  
 <span data-ttu-id="cc74c-113">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc74c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc74c-114">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="cc74c-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="cc74c-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc74c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc74c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc74c-116">See also</span></span>

- [<span data-ttu-id="cc74c-117">Interfaccia IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="cc74c-117">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
