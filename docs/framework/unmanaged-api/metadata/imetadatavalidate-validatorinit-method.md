---
title: Metodo IMetaDataValidate::ValidatorInit
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 31ff2c62810061cd8b774e934167a5ee3acf040c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645079"
---
# <a name="imetadatavalidatevalidatorinit-method"></a><span data-ttu-id="56de8-102">Metodo IMetaDataValidate::ValidatorInit</span><span class="sxs-lookup"><span data-stu-id="56de8-102">IMetaDataValidate::ValidatorInit Method</span></span>
<span data-ttu-id="56de8-103">Imposta un flag che specifica il tipo del modulo nell'ambito dei metadati corrente e registra il metodo di callback specificato per gli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="56de8-103">Sets a flag that specifies the type of the module in the current metadata scope, and registers the specified callback method for validation errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56de8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="56de8-104">Syntax</span></span>  
  
```  
HRESULT ValidatorInit (  
   [in] DWORD       dwModuleType,  
   [in] IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56de8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="56de8-105">Parameters</span></span>  
 `dwModule`  
 <span data-ttu-id="56de8-106">[in] Valore di [CorValidatorModuleType](../../../../docs/framework/unmanaged-api/metadata/corvalidatormoduletype-enumeration.md) enumerazione che specifica il tipo del modulo nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="56de8-106">[in] A value of the [CorValidatorModuleType](../../../../docs/framework/unmanaged-api/metadata/corvalidatormoduletype-enumeration.md) enumeration that specifies the type of the module in the current metadata scope.</span></span>  
  
 `pUnk`  
 <span data-ttu-id="56de8-107">[in] Un puntatore a un [IUnknown](/cpp/atl/iunknown) istanza che funge da un callback della funzione per gli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="56de8-107">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) instance that serves as a function callback for validation errors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56de8-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="56de8-108">Requirements</span></span>  
 <span data-ttu-id="56de8-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56de8-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56de8-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="56de8-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="56de8-111">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="56de8-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="56de8-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56de8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56de8-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56de8-113">See also</span></span>

- [<span data-ttu-id="56de8-114">Interfaccia IMetaDataValidate</span><span class="sxs-lookup"><span data-stu-id="56de8-114">IMetaDataValidate Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatavalidate-interface.md)
