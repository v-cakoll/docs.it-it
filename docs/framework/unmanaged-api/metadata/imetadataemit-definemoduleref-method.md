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
ms.openlocfilehash: 94261b7796166cf482a7de990551890e4722dd3b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177731"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="bf24e-102">Metodo IMetaDataEmit::DefineModuleRef</span><span class="sxs-lookup"><span data-stu-id="bf24e-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="bf24e-103">Crea la firma dei metadati per un modulo con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="bf24e-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf24e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bf24e-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineModuleRef (
    [in]  LPCWSTR           szName,
    [out] mdModuleRef       *pmur
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf24e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bf24e-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="bf24e-106">[in] Nome dell'altro file di metadati, in genere una DLL.</span><span class="sxs-lookup"><span data-stu-id="bf24e-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="bf24e-107">Questo è solo il nome del file.</span><span class="sxs-lookup"><span data-stu-id="bf24e-107">This is the file name only.</span></span> <span data-ttu-id="bf24e-108">Non utilizzare un nome di percorso completo.</span><span class="sxs-lookup"><span data-stu-id="bf24e-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="bf24e-109">[fuori] Token `mdModuleRef` assegnato.</span><span class="sxs-lookup"><span data-stu-id="bf24e-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf24e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bf24e-110">Requirements</span></span>  
 <span data-ttu-id="bf24e-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf24e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf24e-112">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bf24e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bf24e-113">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bf24e-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bf24e-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf24e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf24e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf24e-115">See also</span></span>

- [<span data-ttu-id="bf24e-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="bf24e-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="bf24e-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="bf24e-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
