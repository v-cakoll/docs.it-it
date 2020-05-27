---
title: Metodo IMetaDataEmit::SaveToStream
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToStream
helpviewer_keywords:
- IMetaDataEmit::SaveToStream method [.NET Framework metadata]
- SaveToStream method [.NET Framework metadata]
ms.assetid: e0290a49-3818-4a43-ad46-3014faa34f97
topic_type:
- apiref
ms.openlocfilehash: 87e00a69643b6bc403188fb0fdb6f9e3f3d82115
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003878"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="74d49-102">Metodo IMetaDataEmit::SaveToStream</span><span class="sxs-lookup"><span data-stu-id="74d49-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="74d49-103">Salva tutti i metadati nell'ambito corrente nell'oggetto specificato `IStream` .</span><span class="sxs-lookup"><span data-stu-id="74d49-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74d49-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="74d49-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToStream (
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74d49-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="74d49-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="74d49-106">in Flusso scrivibile in cui salvare.</span><span class="sxs-lookup"><span data-stu-id="74d49-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="74d49-107">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="74d49-107">[in] Reserved.</span></span> <span data-ttu-id="74d49-108">Deve essere zero.</span><span class="sxs-lookup"><span data-stu-id="74d49-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74d49-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="74d49-109">Requirements</span></span>  
 <span data-ttu-id="74d49-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74d49-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74d49-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="74d49-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="74d49-112">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="74d49-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="74d49-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74d49-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74d49-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74d49-114">See also</span></span>

- [<span data-ttu-id="74d49-115">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="74d49-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="74d49-116">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="74d49-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
