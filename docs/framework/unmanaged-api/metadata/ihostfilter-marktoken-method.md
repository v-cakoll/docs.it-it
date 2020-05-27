---
title: Metodo IHostFilter::MarkToken
ms.date: 03/30/2017
api_name:
- IHostFilter.MarkToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostFilter::MarkToken
helpviewer_keywords:
- MarkToken method, IHostFilter interface [.NET Framework metadata]
- IHostFilter::MarkToken method [.NET Framework metadata]
ms.assetid: d7061343-d0a3-4fd5-b312-61974f98bd62
topic_type:
- apiref
ms.openlocfilehash: 11529ce896f265f2b200fa6e511d4b913e9147c8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008222"
---
# <a name="ihostfiltermarktoken-method"></a><span data-ttu-id="2c42d-102">Metodo IHostFilter::MarkToken</span><span class="sxs-lookup"><span data-stu-id="2c42d-102">IHostFilter::MarkToken Method</span></span>
<span data-ttu-id="2c42d-103">Indica che il token di metadati specificato verrà elaborato.</span><span class="sxs-lookup"><span data-stu-id="2c42d-103">Indicates that the specified metadata token will be processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c42d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2c42d-104">Syntax</span></span>  
  
```cpp  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c42d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2c42d-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="2c42d-106">in Token di metadati da elaborare.</span><span class="sxs-lookup"><span data-stu-id="2c42d-106">[in] The metadata token to be processed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c42d-107">Commenti</span><span class="sxs-lookup"><span data-stu-id="2c42d-107">Remarks</span></span>  
 <span data-ttu-id="2c42d-108">In genere, si desidera che un token venga elaborato se è nell'ambito dei metadati.</span><span class="sxs-lookup"><span data-stu-id="2c42d-108">Typically, you want a token to be processed if it is in the metadata scope.</span></span> <span data-ttu-id="2c42d-109">Il `MarkToken` metodo viene passato al motore dei metadati tramite il metodo [IMetaDataEmit::](imetadataemit-sethandler-method.md) SetValue.</span><span class="sxs-lookup"><span data-stu-id="2c42d-109">The `MarkToken` method is passed to the metadata engine via the [IMetaDataEmit::SetHandler](imetadataemit-sethandler-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c42d-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2c42d-110">Requirements</span></span>  
 <span data-ttu-id="2c42d-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c42d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c42d-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2c42d-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2c42d-113">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2c42d-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2c42d-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c42d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c42d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c42d-115">See also</span></span>

- [<span data-ttu-id="2c42d-116">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="2c42d-116">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="2c42d-117">Interfaccia IHostFilter</span><span class="sxs-lookup"><span data-stu-id="2c42d-117">IHostFilter Interface</span></span>](ihostfilter-interface.md)
