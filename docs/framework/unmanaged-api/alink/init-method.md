---
title: Metodo Init
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.Init
api_location: alink.dll
api_type: COM
f1_keywords: Init
helpviewer_keywords: Init method
ms.assetid: e48b5c64-049f-4f93-ad87-d07ae9cd5845
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 999f572d27f75094ecc72c59acee7d35f86d5342
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="init-method"></a><span data-ttu-id="e9272-102">Metodo Init</span><span class="sxs-lookup"><span data-stu-id="e9272-102">Init Method</span></span>
<span data-ttu-id="e9272-103">Prepara oggetti che implementano il [interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="e9272-103">Prepares objects implementing the [IALink Interface](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9272-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9272-104">Syntax</span></span>  
  
```  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9272-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e9272-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="e9272-106">[Interfaccia IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) puntatore al dispenser di metadati.</span><span class="sxs-lookup"><span data-stu-id="e9272-106">[IMetaDataDispenserEx Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="e9272-107">[Interfaccia IMetaDataError](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) puntatore a un parametro facoltativo interfaccia gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="e9272-107">[IMetaDataError Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e9272-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e9272-108">Return Value</span></span>  
 <span data-ttu-id="e9272-109">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="e9272-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9272-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e9272-110">Requirements</span></span>  
 <span data-ttu-id="e9272-111">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="e9272-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9272-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9272-112">See Also</span></span>  
 [<span data-ttu-id="e9272-113">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="e9272-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="e9272-114">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="e9272-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="e9272-115">ALink (API)</span><span class="sxs-lookup"><span data-stu-id="e9272-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
