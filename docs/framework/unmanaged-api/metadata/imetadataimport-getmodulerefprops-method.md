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
ms.openlocfilehash: f1784c9f3085ce188f9e540887dd02064f8448f3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503577"
---
# <a name="imetadataimportgetmodulerefprops-method"></a><span data-ttu-id="116b3-102">Metodo IMetaDataImport::GetModuleRefProps</span><span class="sxs-lookup"><span data-stu-id="116b3-102">IMetaDataImport::GetModuleRefProps Method</span></span>
<span data-ttu-id="116b3-103">Ottiene il nome del modulo a cui fa riferimento il token di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="116b3-103">Gets the name of the module referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="116b3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="116b3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleRefProps (  
   [in]  mdModuleRef         mur,  
   [out] LPWSTR              szName,
   [in]  ULONG               cchName,
   [out] ULONG               *pchName
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="116b3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="116b3-105">Parameters</span></span>  
 `mur`  
 <span data-ttu-id="116b3-106">in Token di metadati ModuleRef che fa riferimento al modulo per il quale ottenere informazioni sui metadati.</span><span class="sxs-lookup"><span data-stu-id="116b3-106">[in] The ModuleRef metadata token that references the module to get metadata information for.</span></span>  
  
 `szName`  
 <span data-ttu-id="116b3-107">out Un buffer in cui memorizzare il nome del modulo.</span><span class="sxs-lookup"><span data-stu-id="116b3-107">[out] A buffer to hold the module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="116b3-108">in Dimensioni richieste di `szName` in caratteri wide.</span><span class="sxs-lookup"><span data-stu-id="116b3-108">[in] The requested size of `szName` in wide characters.</span></span>  
  
 `pchName`  
 <span data-ttu-id="116b3-109">out Dimensioni restituite di `szName` in caratteri wide.</span><span class="sxs-lookup"><span data-stu-id="116b3-109">[out] The returned size of `szName` in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="116b3-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="116b3-110">Requirements</span></span>  
 <span data-ttu-id="116b3-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="116b3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="116b3-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="116b3-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="116b3-113">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="116b3-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="116b3-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="116b3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="116b3-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="116b3-115">See also</span></span>

- [<span data-ttu-id="116b3-116">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="116b3-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="116b3-117">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="116b3-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
