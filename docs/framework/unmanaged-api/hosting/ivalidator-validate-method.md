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
ms.openlocfilehash: 840a3779ca5692787c2c352db60a29d6a4d4ba4f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768596"
---
# <a name="ivalidatorvalidate-method"></a><span data-ttu-id="a8213-102">Metodo IValidator::Validate</span><span class="sxs-lookup"><span data-stu-id="a8213-102">IValidator::Validate Method</span></span>
<span data-ttu-id="a8213-103">Convalida lo specificata eseguibile portabile (PE) o il file Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="a8213-103">Validates the specified portable executable (PE) or Microsoft intermediate language (MSIL) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8213-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a8213-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="a8213-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a8213-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="a8213-106">[in] Un puntatore a un `IVEHandler` istanza che gestisce gli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="a8213-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="a8213-107">[in] Puntatore al dominio dell'applicazione in cui viene caricato il file.</span><span class="sxs-lookup"><span data-stu-id="a8213-107">[in] A pointer to the application domain in which the file is loaded.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="a8213-108">[in] Una combinazione bit per bit di [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) valori, che indica le convalide da eseguire.</span><span class="sxs-lookup"><span data-stu-id="a8213-108">[in] A bitwise combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the validations that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="a8213-109">[in] Il numero massimo di errori consentiti prima di disattivare la convalida.</span><span class="sxs-lookup"><span data-stu-id="a8213-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="a8213-110">[in] Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="a8213-110">[in] Not used.</span></span>  
  
 `fileName`  
 <span data-ttu-id="a8213-111">[in] Stringa che specifica il nome del file da convalidare.</span><span class="sxs-lookup"><span data-stu-id="a8213-111">[in] A string that specifies the name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="a8213-112">[in] Puntatore al buffer di memoria in cui è archiviato il file.</span><span class="sxs-lookup"><span data-stu-id="a8213-112">[in] A pointer to the memory buffer in which the file is stored.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="a8213-113">[in] Le dimensioni, in byte, del file da convalidare.</span><span class="sxs-lookup"><span data-stu-id="a8213-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8213-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a8213-114">Requirements</span></span>  
 <span data-ttu-id="a8213-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8213-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8213-116">**Intestazione:** IValidator. idl, IValidator. H</span><span class="sxs-lookup"><span data-stu-id="a8213-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="a8213-117">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a8213-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a8213-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8213-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
