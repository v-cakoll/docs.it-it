---
title: Metodo Init
ms.date: 03/30/2017
api_name:
- IALink.Init
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- Init
helpviewer_keywords:
- Init method
ms.assetid: e48b5c64-049f-4f93-ad87-d07ae9cd5845
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 60602462376543fe934bb3c58bc4988fa8ab34bf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59119366"
---
# <a name="init-method"></a><span data-ttu-id="5aae3-102">Metodo Init</span><span class="sxs-lookup"><span data-stu-id="5aae3-102">Init Method</span></span>
<span data-ttu-id="5aae3-103">Prepara gli oggetti che implementano il [interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) per l'uso.</span><span class="sxs-lookup"><span data-stu-id="5aae3-103">Prepares objects implementing the [IALink Interface](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5aae3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5aae3-104">Syntax</span></span>  
  
```  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="5aae3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5aae3-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="5aae3-106">[Interfaccia IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) puntatore a dispenser di metadati.</span><span class="sxs-lookup"><span data-stu-id="5aae3-106">[IMetaDataDispenserEx Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="5aae3-107">[Interfaccia IMetaDataError](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) puntatore a un'interfaccia di gestione degli errori facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5aae3-107">[IMetaDataError Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5aae3-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5aae3-108">Return Value</span></span>  
 <span data-ttu-id="5aae3-109">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5aae3-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5aae3-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5aae3-110">Requirements</span></span>  
 <span data-ttu-id="5aae3-111">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="5aae3-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5aae3-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5aae3-112">See also</span></span>

- [<span data-ttu-id="5aae3-113">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="5aae3-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="5aae3-114">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="5aae3-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="5aae3-115">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="5aae3-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
