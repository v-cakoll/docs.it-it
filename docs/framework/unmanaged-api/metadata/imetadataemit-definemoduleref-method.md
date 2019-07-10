---
title: Metodo IMetaDataEmit::DefineModuleRef
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineModuleRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineModuleRef
helpviewer_keywords:
- DefineModuleRef method [.NET Framework metadata]
- IMetaDataEmit::DefineModuleRef method [.NET Framework metadata]
ms.assetid: f2833594-d90b-4a71-9a53-34b12470c64a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 19f1839aa2c4ca810e76c1745103a00c6f5ea5a3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777571"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="0519d-102">Metodo IMetaDataEmit::DefineModuleRef</span><span class="sxs-lookup"><span data-stu-id="0519d-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="0519d-103">Crea la firma dei metadati per un modulo con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="0519d-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0519d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0519d-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineModuleRef (     
    [in]  LPCWSTR           szName,   
    [out] mdModuleRef       *pmur   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0519d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0519d-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="0519d-106">[in] Il nome degli altri file dei metadati, in genere una DLL.</span><span class="sxs-lookup"><span data-stu-id="0519d-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="0519d-107">Si tratta solo il nome del file.</span><span class="sxs-lookup"><span data-stu-id="0519d-107">This is the file name only.</span></span> <span data-ttu-id="0519d-108">Non utilizzare un nome e percorso completo.</span><span class="sxs-lookup"><span data-stu-id="0519d-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="0519d-109">[out] L'oggetto assegnato `mdModuleRef` token.</span><span class="sxs-lookup"><span data-stu-id="0519d-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0519d-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0519d-110">Requirements</span></span>  
 <span data-ttu-id="0519d-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0519d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0519d-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0519d-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0519d-113">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="0519d-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0519d-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0519d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0519d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0519d-115">See also</span></span>

- [<span data-ttu-id="0519d-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="0519d-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="0519d-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="0519d-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
