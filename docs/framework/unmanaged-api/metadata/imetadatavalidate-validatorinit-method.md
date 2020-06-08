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
ms.openlocfilehash: 687f33c364f9730a554a41ade1ca2b78e33ffdc5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84489717"
---
# <a name="imetadatavalidatevalidatorinit-method"></a><span data-ttu-id="c948f-102">Metodo IMetaDataValidate::ValidatorInit</span><span class="sxs-lookup"><span data-stu-id="c948f-102">IMetaDataValidate::ValidatorInit Method</span></span>
<span data-ttu-id="c948f-103">Imposta un flag che specifica il tipo del modulo nell'ambito dei metadati corrente e registra il metodo di callback specificato per gli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="c948f-103">Sets a flag that specifies the type of the module in the current metadata scope, and registers the specified callback method for validation errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c948f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c948f-104">Syntax</span></span>  
  
```cpp  
HRESULT ValidatorInit (  
   [in] DWORD       dwModuleType,  
   [in] IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c948f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c948f-105">Parameters</span></span>  
 `dwModule`  
 <span data-ttu-id="c948f-106">in Valore dell'enumerazione [CorValidatorModuleType](corvalidatormoduletype-enumeration.md) che specifica il tipo del modulo nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="c948f-106">[in] A value of the [CorValidatorModuleType](corvalidatormoduletype-enumeration.md) enumeration that specifies the type of the module in the current metadata scope.</span></span>  
  
 `pUnk`  
 <span data-ttu-id="c948f-107">in Puntatore a un'istanza [IUnknown](/cpp/atl/iunknown) che funge da callback di funzione per gli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="c948f-107">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) instance that serves as a function callback for validation errors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c948f-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c948f-108">Requirements</span></span>  
 <span data-ttu-id="c948f-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c948f-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c948f-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c948f-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c948f-111">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c948f-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c948f-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c948f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c948f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c948f-113">See also</span></span>

- [<span data-ttu-id="c948f-114">Interfaccia IMetaDataValidate</span><span class="sxs-lookup"><span data-stu-id="c948f-114">IMetaDataValidate Interface</span></span>](imetadatavalidate-interface.md)
