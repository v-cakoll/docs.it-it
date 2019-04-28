---
title: Metodo IValidator::Validate
ms.date: 03/30/2017
api_name:
- IValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Validate
helpviewer_keywords:
- IValidator::Validate method [.NET Framework hosting]
- Validate method, IValidator interface [.NET Framework hosting]
ms.assetid: 7d68666a-fb73-4455-bebd-908d49a16abc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1fba06360a0c31e0a7fa3e61de9793bad14650fa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765297"
---
# <a name="ivalidatorvalidate-method"></a><span data-ttu-id="1e857-102">Metodo IValidator::Validate</span><span class="sxs-lookup"><span data-stu-id="1e857-102">IValidator::Validate Method</span></span>
<span data-ttu-id="1e857-103">Convalida lo specificata eseguibile portabile (PE) o il file Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="1e857-103">Validates the specified portable executable (PE) or Microsoft intermediate language (MSIL) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e857-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1e857-104">Syntax</span></span>  
  
```  
HRESULT Validate (  
    [in] IVEHandler            *veh,  
    [in] IUnknown              *pAppDomain,  
    [in] unsigned long          ulFlags,  
    [in] unsigned long          ulMaxError,  
    [in] unsigned long          token,  
    [in] LPWSTR                 fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long          ulSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e857-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1e857-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="1e857-106">[in] Un puntatore a un `IVEHandler` istanza che gestisce gli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="1e857-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="1e857-107">[in] Puntatore al dominio dell'applicazione in cui viene caricato il file.</span><span class="sxs-lookup"><span data-stu-id="1e857-107">[in] A pointer to the application domain in which the file is loaded.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="1e857-108">[in] Una combinazione bit per bit di [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) valori, che indica le convalide da eseguire.</span><span class="sxs-lookup"><span data-stu-id="1e857-108">[in] A bitwise combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the validations that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="1e857-109">[in] Il numero massimo di errori consentiti prima di disattivare la convalida.</span><span class="sxs-lookup"><span data-stu-id="1e857-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="1e857-110">[in] Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="1e857-110">[in] Not used.</span></span>  
  
 `fileName`  
 <span data-ttu-id="1e857-111">[in] Stringa che specifica il nome del file da convalidare.</span><span class="sxs-lookup"><span data-stu-id="1e857-111">[in] A string that specifies the name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="1e857-112">[in] Puntatore al buffer di memoria in cui è archiviato il file.</span><span class="sxs-lookup"><span data-stu-id="1e857-112">[in] A pointer to the memory buffer in which the file is stored.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="1e857-113">[in] Le dimensioni, in byte, del file da convalidare.</span><span class="sxs-lookup"><span data-stu-id="1e857-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e857-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1e857-114">Requirements</span></span>  
 <span data-ttu-id="1e857-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e857-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e857-116">**Intestazione:** IValidator. idl, IValidator. H</span><span class="sxs-lookup"><span data-stu-id="1e857-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="1e857-117">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="1e857-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1e857-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e857-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
