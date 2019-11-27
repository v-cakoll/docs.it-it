---
title: Metodo IMetaDataEmit::DeleteToken
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteToken
helpviewer_keywords:
- DeleteToken method [.NET Framework metadata]
- IMetaDataEmit::DeleteToken method [.NET Framework metadata]
ms.assetid: a4926d0a-261b-46b1-9994-82633661a64b
topic_type:
- apiref
ms.openlocfilehash: e8c145632911817e8e19d587bb8afead0a6c33af
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434342"
---
# <a name="imetadataemitdeletetoken-method"></a><span data-ttu-id="34dcd-102">Metodo IMetaDataEmit::DeleteToken</span><span class="sxs-lookup"><span data-stu-id="34dcd-102">IMetaDataEmit::DeleteToken Method</span></span>
<span data-ttu-id="34dcd-103">Elimina il token specificato dall'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="34dcd-103">Deletes the specified token from the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34dcd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="34dcd-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteToken (   
    [in]  mdToken     tkObj   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34dcd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="34dcd-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="34dcd-106">in Token da eliminare.</span><span class="sxs-lookup"><span data-stu-id="34dcd-106">[in] The token to be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34dcd-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="34dcd-107">Requirements</span></span>  
 <span data-ttu-id="34dcd-108">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34dcd-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34dcd-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="34dcd-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="34dcd-110">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="34dcd-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="34dcd-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34dcd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34dcd-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34dcd-112">See also</span></span>

- [<span data-ttu-id="34dcd-113">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="34dcd-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="34dcd-114">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="34dcd-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
