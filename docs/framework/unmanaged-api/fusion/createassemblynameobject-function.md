---
title: Funzione CreateAssemblyNameObject
ms.date: 03/30/2017
api_name:
- CreateAssemblyNameObject
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyNameObject
helpviewer_keywords:
- CreateAssemblyNameObject function [.NET Framework fusion]
ms.assetid: 55c8b41e-fbe4-4ae0-aa29-68fbb2311691
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd8609bedcea28c1cb8559d378b5e171f3ad568e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59225001"
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="e8f67-102">Funzione CreateAssemblyNameObject</span><span class="sxs-lookup"><span data-stu-id="e8f67-102">CreateAssemblyNameObject Function</span></span>
<span data-ttu-id="e8f67-103">Ottiene un puntatore a interfaccia a un [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) istanza che rappresenta l'identità univoca dell'assembly con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="e8f67-103">Gets an interface pointer to an [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8f67-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8f67-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8f67-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e8f67-105">Parameters</span></span>  
 `ppAssemblyNameObj`  
 <span data-ttu-id="e8f67-106">[out] L'oggetto restituito `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="e8f67-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="e8f67-107">[in] Il nome dell'assembly per cui si desidera creare il nuovo `IAssemblyName` istanza.</span><span class="sxs-lookup"><span data-stu-id="e8f67-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e8f67-108">[in] Flag da passare al costruttore dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="e8f67-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="e8f67-109">[in] Riservato per un'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="e8f67-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="e8f67-110">`pvReserved` deve essere un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="e8f67-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8f67-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e8f67-111">Requirements</span></span>  
 <span data-ttu-id="e8f67-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8f67-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8f67-113">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="e8f67-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e8f67-114">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e8f67-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e8f67-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8f67-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8f67-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8f67-116">See also</span></span>

- [<span data-ttu-id="e8f67-117">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="e8f67-117">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="e8f67-118">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="e8f67-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
