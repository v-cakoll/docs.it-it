---
title: Metodo IMetaDataImport::GetModuleRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetModuleRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetModuleRefProps
helpviewer_keywords:
- GetModuleRefProps method [.NET Framework metadata]
- IMetaDataImport::GetModuleRefProps method [.NET Framework metadata]
ms.assetid: b558e766-4c11-4628-ae47-b4e0a1800168
topic_type:
- apiref
ms.openlocfilehash: f46033b9e643ef6b4a0063c4995b8c024b8c1f7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175356"
---
# <a name="imetadataimportgetmodulerefprops-method"></a><span data-ttu-id="cec0f-102">Metodo IMetaDataImport::GetModuleRefProps</span><span class="sxs-lookup"><span data-stu-id="cec0f-102">IMetaDataImport::GetModuleRefProps Method</span></span>
<span data-ttu-id="cec0f-103">Ottiene il nome del modulo a cui fa riferimento il token di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="cec0f-103">Gets the name of the module referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cec0f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cec0f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleRefProps (  
   [in]  mdModuleRef         mur,  
   [out] LPWSTR              szName,
   [in]  ULONG               cchName,
   [out] ULONG               *pchName
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cec0f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cec0f-105">Parameters</span></span>  
 `mur`  
 <span data-ttu-id="cec0f-106">[in] Token di metadati ModuleRef che fa riferimento al modulo per cui ottenere informazioni sui metadati.</span><span class="sxs-lookup"><span data-stu-id="cec0f-106">[in] The ModuleRef metadata token that references the module to get metadata information for.</span></span>  
  
 `szName`  
 <span data-ttu-id="cec0f-107">[fuori] Un buffer per contenere il nome del modulo.</span><span class="sxs-lookup"><span data-stu-id="cec0f-107">[out] A buffer to hold the module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="cec0f-108">[in] Dimensione richiesta `szName` di caratteri di tipo wide.</span><span class="sxs-lookup"><span data-stu-id="cec0f-108">[in] The requested size of `szName` in wide characters.</span></span>  
  
 `pchName`  
 <span data-ttu-id="cec0f-109">[fuori] Dimensione restituita `szName` di caratteri di tipo wide.</span><span class="sxs-lookup"><span data-stu-id="cec0f-109">[out] The returned size of `szName` in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cec0f-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cec0f-110">Requirements</span></span>  
 <span data-ttu-id="cec0f-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cec0f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cec0f-112">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cec0f-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cec0f-113">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cec0f-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cec0f-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cec0f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cec0f-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cec0f-115">See also</span></span>

- [<span data-ttu-id="cec0f-116">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="cec0f-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="cec0f-117">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="cec0f-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
