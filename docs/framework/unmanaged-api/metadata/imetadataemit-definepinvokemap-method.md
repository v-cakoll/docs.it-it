---
title: Metodo IMetaDataEmit::DefinePinvokeMap
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePinvokeMap
helpviewer_keywords:
- DefinePinvokeMap method [.NET Framework metadata]
- IMetaDataEmit::DefinePinvokeMap method [.NET Framework metadata]
ms.assetid: 03abf921-5154-4070-88fa-10b7092901fb
topic_type:
- apiref
ms.openlocfilehash: 447ec44ed3efc4eec84d1e4acd6f2ec1a730bf74
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008027"
---
# <a name="imetadataemitdefinepinvokemap-method"></a><span data-ttu-id="43934-102">Metodo IMetaDataEmit::DefinePinvokeMap</span><span class="sxs-lookup"><span data-stu-id="43934-102">IMetaDataEmit::DefinePinvokeMap Method</span></span>
<span data-ttu-id="43934-103">Imposta le funzionalità della firma PInvoke del metodo a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="43934-103">Sets features of the PInvoke signature of the method referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43934-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="43934-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePinvokeMap (
    [in]  mdToken            tk,
    [in]  DWORD              dwMappingFlags,
    [in]  LPCWSTR            szImportName,
    [in]  mdModuleRef        mrImportDLL
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43934-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="43934-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="43934-106">in Token per il metodo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="43934-106">[in] The token for the target method.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="43934-107">in Flag utilizzati da PInvoke per eseguire il mapping.</span><span class="sxs-lookup"><span data-stu-id="43934-107">[in] Flags used by PInvoke to do the mapping.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="43934-108">in Nome del metodo di esportazione di destinazione in una DLL non gestita.</span><span class="sxs-lookup"><span data-stu-id="43934-108">[in] The name of the target export method in an unmanaged DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="43934-109">in Token per la DLL nativa di destinazione.</span><span class="sxs-lookup"><span data-stu-id="43934-109">[in] The token for the target native DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43934-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="43934-110">Requirements</span></span>  
 <span data-ttu-id="43934-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43934-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43934-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="43934-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="43934-113">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="43934-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43934-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43934-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43934-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43934-115">See also</span></span>

- [<span data-ttu-id="43934-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="43934-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="43934-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="43934-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
