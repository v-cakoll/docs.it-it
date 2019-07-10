---
title: Metodo IMetaDataEmit2::SaveDelta
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDelta
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDelta
helpviewer_keywords:
- IMetaDataEmit2::SaveDelta method [.NET Framework metadata]
- SaveDelta method [.NET Framework metadata]
ms.assetid: b95739fe-d2fa-4776-ae0d-31d9707ef799
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 212625fd460e88201dd4799754297861826d3aa7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777152"
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="46291-102">Metodo IMetaDataEmit2::SaveDelta</span><span class="sxs-lookup"><span data-stu-id="46291-102">IMetaDataEmit2::SaveDelta Method</span></span>
<span data-ttu-id="46291-103">Salva le modifiche dalla sessione corrente di modifica e continuazione per il file specificato.</span><span class="sxs-lookup"><span data-stu-id="46291-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46291-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="46291-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46291-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="46291-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="46291-106">[in] Il nome del file in cui salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="46291-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="46291-107">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="46291-107">[in] Reserved.</span></span> <span data-ttu-id="46291-108">Deve essere zero.</span><span class="sxs-lookup"><span data-stu-id="46291-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46291-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="46291-109">Requirements</span></span>  
 <span data-ttu-id="46291-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46291-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46291-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="46291-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="46291-112">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="46291-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="46291-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46291-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46291-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46291-114">See also</span></span>

- [<span data-ttu-id="46291-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="46291-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="46291-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="46291-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
