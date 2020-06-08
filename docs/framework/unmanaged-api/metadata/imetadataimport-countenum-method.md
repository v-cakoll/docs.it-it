---
title: Metodo IMetaDataImport::CountEnum
ms.date: 03/30/2017
api_name:
- IMetaDataImport.CountEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::CountEnum
helpviewer_keywords:
- CountEnum method [.NET Framework metadata]
- IMetaDataImport::CountEnum method [.NET Framework metadata]
ms.assetid: d1de53ad-9435-4b5f-9df7-07f21210e5b5
topic_type:
- apiref
ms.openlocfilehash: 4521a3f15ec358a4d786a4533efb6b99d0e1c1cc
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492382"
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="ac883-102">Metodo IMetaDataImport::CountEnum</span><span class="sxs-lookup"><span data-stu-id="ac883-102">IMetaDataImport::CountEnum Method</span></span>
<span data-ttu-id="ac883-103">Ottiene il numero di elementi nell'enumerazione recuperato dall'enumeratore specificato.</span><span class="sxs-lookup"><span data-stu-id="ac883-103">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac883-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ac883-104">Syntax</span></span>  
  
```cpp  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,
   [out] ULONG       *pulCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac883-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ac883-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="ac883-106">in Handle per l'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="ac883-106">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="ac883-107">out Numero di elementi enumerati.</span><span class="sxs-lookup"><span data-stu-id="ac883-107">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac883-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ac883-108">Remarks</span></span>  
 <span data-ttu-id="ac883-109">L'handle specificato da `hEnum` viene ottenuto da una chiamata al `Enum` *nome* precedente (ad esempio, [IMetaDataImport:: EnumTypeDefs](imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="ac883-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac883-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ac883-110">Requirements</span></span>  
 <span data-ttu-id="ac883-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac883-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac883-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ac883-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ac883-113">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ac883-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ac883-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac883-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac883-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac883-115">See also</span></span>

- [<span data-ttu-id="ac883-116">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="ac883-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="ac883-117">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="ac883-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
