---
title: Metodo IMetaDataTables2::GetMetaDataStorage
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStorage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStorage
helpviewer_keywords:
- GetMetaDataStorage method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStorage method [.NET Framework metadata]
ms.assetid: 667a6d1e-753d-4ea2-8fd8-a8337d1bb9cd
topic_type:
- apiref
ms.openlocfilehash: 55fcde6c47705e515eb2d20f25ac870e257b92c0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501131"
---
# <a name="imetadatatables2getmetadatastorage-method"></a><span data-ttu-id="39ecb-102">Metodo IMetaDataTables2::GetMetaDataStorage</span><span class="sxs-lookup"><span data-stu-id="39ecb-102">IMetaDataTables2::GetMetaDataStorage Method</span></span>
<span data-ttu-id="39ecb-103">Ottiene le dimensioni e il contenuto dei metadati archiviati nella sezione specificata.</span><span class="sxs-lookup"><span data-stu-id="39ecb-103">Gets the size and contents of the metadata stored in the specified section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39ecb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39ecb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataStorage (  
   [in, out] const void   **ppvMd,  
   [out] ULONG   *pcbMd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39ecb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="39ecb-105">Parameters</span></span>  
 `ppvMd`  
 <span data-ttu-id="39ecb-106">[in, out] Puntatore a una sezione di metadati.</span><span class="sxs-lookup"><span data-stu-id="39ecb-106">[in, out] A pointer to a metadata section.</span></span>  
  
 `pcbMd`  
 <span data-ttu-id="39ecb-107">out Dimensioni del flusso di metadati.</span><span class="sxs-lookup"><span data-stu-id="39ecb-107">[out] The size of the metadata stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39ecb-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="39ecb-108">Requirements</span></span>  
 <span data-ttu-id="39ecb-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39ecb-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39ecb-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="39ecb-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="39ecb-111">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="39ecb-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="39ecb-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39ecb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39ecb-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39ecb-113">See also</span></span>

- [<span data-ttu-id="39ecb-114">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="39ecb-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
- [<span data-ttu-id="39ecb-115">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="39ecb-115">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
