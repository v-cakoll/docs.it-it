---
title: Metodo IMetaDataEmit::DeleteClassLayout
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteClassLayout
helpviewer_keywords:
- DeleteClassLayout method [.NET Framework metadata]
- IMetaDataEmit::DeleteClassLayout method [.NET Framework metadata]
ms.assetid: 65a4ad49-fa49-4b36-8ed1-76dd6a185ab4
topic_type:
- apiref
ms.openlocfilehash: 3ef6b89ed6578d77f30d5e53657b962b200b0ed6
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009321"
---
# <a name="imetadataemitdeleteclasslayout-method"></a><span data-ttu-id="b8551-102">Metodo IMetaDataEmit::DeleteClassLayout</span><span class="sxs-lookup"><span data-stu-id="b8551-102">IMetaDataEmit::DeleteClassLayout Method</span></span>
<span data-ttu-id="b8551-103">Elimina definitivamente la firma dei metadati del layout della classe per il tipo rappresentato dal token specificato.</span><span class="sxs-lookup"><span data-stu-id="b8551-103">Destroys the class layout metadata signature for the type represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8551-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b8551-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteClassLayout (  
    [in]  mdTypeDef   td  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8551-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b8551-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="b8551-106">in `mdTypeDef`Token di metadati che rappresenta il tipo per il quale verrà eliminato il layout della classe.</span><span class="sxs-lookup"><span data-stu-id="b8551-106">[in] An `mdTypeDef` metadata token that represents the type for which the class layout will be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8551-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b8551-107">Requirements</span></span>  
 <span data-ttu-id="b8551-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8551-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8551-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b8551-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b8551-110">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b8551-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b8551-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8551-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8551-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8551-112">See also</span></span>

- [<span data-ttu-id="b8551-113">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="b8551-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="b8551-114">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="b8551-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
