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
ms.openlocfilehash: 4503c3c745fde148c77ff30c9ece008dd9d54829
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445796"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="0cad0-102">Metodo IMetaDataEmit::DefineModuleRef</span><span class="sxs-lookup"><span data-stu-id="0cad0-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="0cad0-103">Crea la firma dei metadati per un modulo con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="0cad0-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cad0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0cad0-104">Syntax</span></span>  
  
```  
HRESULT DefineModuleRef (     
    [in]  LPCWSTR           szName,   
    [out] mdModuleRef       *pmur   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0cad0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0cad0-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="0cad0-106">[in] Il nome di altri file di metadati, in genere una DLL.</span><span class="sxs-lookup"><span data-stu-id="0cad0-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="0cad0-107">Questo è solo il nome del file.</span><span class="sxs-lookup"><span data-stu-id="0cad0-107">This is the file name only.</span></span> <span data-ttu-id="0cad0-108">Non utilizzare un nome e percorso completo.</span><span class="sxs-lookup"><span data-stu-id="0cad0-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="0cad0-109">[out] L'oggetto assegnato `mdModuleRef` token.</span><span class="sxs-lookup"><span data-stu-id="0cad0-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cad0-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0cad0-110">Requirements</span></span>  
 <span data-ttu-id="0cad0-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cad0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cad0-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0cad0-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0cad0-113">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="0cad0-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0cad0-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cad0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cad0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0cad0-115">See Also</span></span>  
 [<span data-ttu-id="0cad0-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="0cad0-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="0cad0-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="0cad0-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
