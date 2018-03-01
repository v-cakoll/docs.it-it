---
title: Metodo IMetaDataValidate::ValidatorInit
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
- IMetaDataValidate.ValidatorInit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataValidate::ValidatorInit
helpviewer_keywords:
- IMetaDataValidate::ValidatorInit method [.NET Framework metadata]
- ValidatorInit method [.NET Framework metadata]
ms.assetid: 6bafd75a-e2d0-4aea-aed1-074374d5dff6
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 26f5f6626766d7341ef5c8b2ecbe5e56a17eafdd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatavalidatevalidatorinit-method"></a><span data-ttu-id="8db8a-102">Metodo IMetaDataValidate::ValidatorInit</span><span class="sxs-lookup"><span data-stu-id="8db8a-102">IMetaDataValidate::ValidatorInit Method</span></span>
<span data-ttu-id="8db8a-103">Imposta un flag che specifica il tipo del modulo nell'ambito dei metadati corrente e registra il metodo di callback specificato per gli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="8db8a-103">Sets a flag that specifies the type of the module in the current metadata scope, and registers the specified callback method for validation errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8db8a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8db8a-104">Syntax</span></span>  
  
```  
HRESULT ValidatorInit (  
   [in] DWORD       dwModuleType,  
   [in] IUnknown    *pUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8db8a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8db8a-105">Parameters</span></span>  
 `dwModule`  
 <span data-ttu-id="8db8a-106">[in] Il valore di [CorValidatorModuleType](../../../../docs/framework/unmanaged-api/metadata/corvalidatormoduletype-enumeration.md) enumerazione che specifica il tipo del modulo nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="8db8a-106">[in] A value of the [CorValidatorModuleType](../../../../docs/framework/unmanaged-api/metadata/corvalidatormoduletype-enumeration.md) enumeration that specifies the type of the module in the current metadata scope.</span></span>  
  
 `pUnk`  
 <span data-ttu-id="8db8a-107">[in] Un puntatore a un <<!--zzxref:IUnknown --> `IUnknown`> istanza che funge da un callback di funzione per gli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="8db8a-107">[in] A pointer to an <<!--zzxref:IUnknown --> `IUnknown`> instance that serves as a function callback for validation errors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8db8a-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8db8a-108">Requirements</span></span>  
 <span data-ttu-id="8db8a-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8db8a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8db8a-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8db8a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8db8a-111">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8db8a-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8db8a-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8db8a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8db8a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8db8a-113">See Also</span></span>  
 [<span data-ttu-id="8db8a-114">Interfaccia IMetaDataValidate</span><span class="sxs-lookup"><span data-stu-id="8db8a-114">IMetaDataValidate Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatavalidate-interface.md)
