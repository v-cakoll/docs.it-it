---
title: Metodo Init
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 19e37a4df8055f14a72a4c9093cd594a234ae80d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="init-method"></a><span data-ttu-id="259ed-102">Metodo Init</span><span class="sxs-lookup"><span data-stu-id="259ed-102">Init Method</span></span>
<span data-ttu-id="259ed-103">Prepara oggetti che implementano il [interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="259ed-103">Prepares objects implementing the [IALink Interface](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="259ed-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="259ed-104">Syntax</span></span>  
  
```  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="259ed-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="259ed-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="259ed-106">[Interfaccia IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) puntatore al dispenser di metadati.</span><span class="sxs-lookup"><span data-stu-id="259ed-106">[IMetaDataDispenserEx Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="259ed-107">[Interfaccia IMetaDataError](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) puntatore a un parametro facoltativo interfaccia gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="259ed-107">[IMetaDataError Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="259ed-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="259ed-108">Return Value</span></span>  
 <span data-ttu-id="259ed-109">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="259ed-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="259ed-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="259ed-110">Requirements</span></span>  
 <span data-ttu-id="259ed-111">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="259ed-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="259ed-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="259ed-112">See Also</span></span>  
 [<span data-ttu-id="259ed-113">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="259ed-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="259ed-114">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="259ed-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="259ed-115">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="259ed-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
