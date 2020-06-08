---
title: Metodo IMetaDataEmit2::GetDeltaSaveSize
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.GetDeltaSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::GetDeltaSaveSize
helpviewer_keywords:
- IMetaDataEmit2::GetDeltaSaveSize method [.NET Framework metadata]
- GetDeltaSaveSize method [.NET Framework metadata]
ms.assetid: 036db5e7-8211-4645-9a34-03d1a89be955
topic_type:
- apiref
ms.openlocfilehash: 24fe8fd65b36e133b767cd07c8602aa1ea7b9dfc
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493110"
---
# <a name="imetadataemit2getdeltasavesize-method"></a><span data-ttu-id="eb0bc-102">Metodo IMetaDataEmit2::GetDeltaSaveSize</span><span class="sxs-lookup"><span data-stu-id="eb0bc-102">IMetaDataEmit2::GetDeltaSaveSize Method</span></span>
<span data-ttu-id="eb0bc-103">Ottiene un valore che indica qualsiasi modifica alle dimensioni dei metadati risultante dalla sessione di modifica e continuazione corrente.</span><span class="sxs-lookup"><span data-stu-id="eb0bc-103">Gets a value indicating any change in metadata size that results from the current edit-and-continue session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb0bc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eb0bc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDeltaSaveSize (  
    [in]  CorSaveSize  fSave,  
    [out] DWORD        *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb0bc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="eb0bc-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="eb0bc-106">in Uno dei valori di [CorSaveSize](corsavesize-enumeration.md) , che indica il livello di precisione desiderato.</span><span class="sxs-lookup"><span data-stu-id="eb0bc-106">[in] One of the [CorSaveSize](corsavesize-enumeration.md) values, indicating the level of precision desired.</span></span> <span data-ttu-id="eb0bc-107">Per la versione .NET Framework 2,0, questo parametro viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="eb0bc-107">For the .NET Framework version 2.0, this parameter is ignored.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="eb0bc-108">out Modifica delle dimensioni dei metadati.</span><span class="sxs-lookup"><span data-stu-id="eb0bc-108">[out] The change in the size of the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb0bc-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eb0bc-109">Requirements</span></span>  
 <span data-ttu-id="eb0bc-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb0bc-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb0bc-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="eb0bc-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eb0bc-112">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="eb0bc-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eb0bc-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb0bc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb0bc-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb0bc-114">See also</span></span>

- [<span data-ttu-id="eb0bc-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="eb0bc-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="eb0bc-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="eb0bc-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
