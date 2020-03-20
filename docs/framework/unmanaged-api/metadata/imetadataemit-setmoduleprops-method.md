---
title: Metodo IMetaDataEmit::SetModuleProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetModuleProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetModuleProps
helpviewer_keywords:
- SetModuleProps method [.NET Framework metadata]
- IMetaDataEmit::SetModuleProps method [.NET Framework metadata]
ms.assetid: b74d7629-5f46-458f-8d67-2456a1e7030c
topic_type:
- apiref
ms.openlocfilehash: 69c3ee366dbb8505e0df744037c480da996bb836
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175616"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="d64d1-102">Metodo IMetaDataEmit::SetModuleProps</span><span class="sxs-lookup"><span data-stu-id="d64d1-102">IMetaDataEmit::SetModuleProps Method</span></span>
<span data-ttu-id="d64d1-103">Aggiorna i riferimenti a un modulo definito da una precedente chiamata a [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span><span class="sxs-lookup"><span data-stu-id="d64d1-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d64d1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d64d1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetModuleProps (
    [in]  LPCWSTR     szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d64d1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d64d1-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="d64d1-106">[in] Nome del modulo in Unicode.</span><span class="sxs-lookup"><span data-stu-id="d64d1-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="d64d1-107">Questo è solo il nome del file e non il nome del percorso completo.</span><span class="sxs-lookup"><span data-stu-id="d64d1-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d64d1-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d64d1-108">Requirements</span></span>  
 <span data-ttu-id="d64d1-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d64d1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d64d1-110">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d64d1-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d64d1-111">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d64d1-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d64d1-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d64d1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d64d1-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d64d1-113">See also</span></span>

- [<span data-ttu-id="d64d1-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="d64d1-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d64d1-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="d64d1-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
