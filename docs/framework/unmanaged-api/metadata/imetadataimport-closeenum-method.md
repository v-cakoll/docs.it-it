---
title: Metodo IMetaDataImport::CloseEnum
ms.date: 03/30/2017
api_name:
- IMetaDataImport.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::CloseEnum
helpviewer_keywords:
- IMetaDataImport::CloseEnum method [.NET Framework metadata]
- CloseEnum method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 727819d5-1dab-4ebb-ac25-950b4111dc72
topic_type:
- apiref
ms.openlocfilehash: 5de62db4180a6a9160193053fe42e39cebc34d0e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492479"
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="8565c-102">Metodo IMetaDataImport::CloseEnum</span><span class="sxs-lookup"><span data-stu-id="8565c-102">IMetaDataImport::CloseEnum Method</span></span>
<span data-ttu-id="8565c-103">Chiude l'enumeratore identificato dall'handle specificato.</span><span class="sxs-lookup"><span data-stu-id="8565c-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8565c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8565c-104">Syntax</span></span>  
  
```cpp  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8565c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8565c-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="8565c-106">in Handle per l'enumeratore da chiudere.</span><span class="sxs-lookup"><span data-stu-id="8565c-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8565c-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8565c-107">Remarks</span></span>  
 <span data-ttu-id="8565c-108">L'handle specificato da `hEnum` viene ottenuto da una chiamata al `Enum` *nome* precedente (ad esempio, [IMetaDataImport:: EnumTypeDefs](imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="8565c-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8565c-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8565c-109">Requirements</span></span>  
 <span data-ttu-id="8565c-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8565c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8565c-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8565c-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8565c-112">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8565c-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8565c-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8565c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8565c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8565c-114">See also</span></span>

- [<span data-ttu-id="8565c-115">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="8565c-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="8565c-116">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="8565c-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
