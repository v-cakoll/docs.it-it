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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dd75fa12a95478a65d93eb07a32acf4cfd8b9632
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782087"
---
# <a name="imetadatatables2getmetadatastorage-method"></a><span data-ttu-id="7ab62-102">Metodo IMetaDataTables2::GetMetaDataStorage</span><span class="sxs-lookup"><span data-stu-id="7ab62-102">IMetaDataTables2::GetMetaDataStorage Method</span></span>
<span data-ttu-id="7ab62-103">Ottiene le dimensioni e il contenuto dei metadati archiviati nella sezione specificata.</span><span class="sxs-lookup"><span data-stu-id="7ab62-103">Gets the size and contents of the metadata stored in the specified section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ab62-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7ab62-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataStorage (  
   [in, out] const void   **ppvMd,  
   [out] ULONG   *pcbMd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ab62-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7ab62-105">Parameters</span></span>  
 `ppvMd`  
 <span data-ttu-id="7ab62-106">[in, out] Puntatore a una sezione di metadati.</span><span class="sxs-lookup"><span data-stu-id="7ab62-106">[in, out] A pointer to a metadata section.</span></span>  
  
 `pcbMd`  
 <span data-ttu-id="7ab62-107">[out] Le dimensioni del flusso di metadati.</span><span class="sxs-lookup"><span data-stu-id="7ab62-107">[out] The size of the metadata stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ab62-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7ab62-108">Requirements</span></span>  
 <span data-ttu-id="7ab62-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ab62-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ab62-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7ab62-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7ab62-111">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="7ab62-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7ab62-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ab62-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ab62-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ab62-113">See also</span></span>

- [<span data-ttu-id="7ab62-114">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="7ab62-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
- [<span data-ttu-id="7ab62-115">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="7ab62-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
