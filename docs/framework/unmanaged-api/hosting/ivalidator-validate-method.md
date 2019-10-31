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
ms.openlocfilehash: 8ae47eac713fbee30ea543538957b12460b8e1fc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123278"
---
# <a name="ivalidatorvalidate-method"></a><span data-ttu-id="1660f-102">Metodo IValidator::Validate</span><span class="sxs-lookup"><span data-stu-id="1660f-102">IValidator::Validate Method</span></span>
<span data-ttu-id="1660f-103">Convalida il file eseguibile portabile (PE) o il file MSIL (Microsoft Intermediate Language) specificato.</span><span class="sxs-lookup"><span data-stu-id="1660f-103">Validates the specified portable executable (PE) or Microsoft intermediate language (MSIL) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1660f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1660f-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="1660f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1660f-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="1660f-106">in Puntatore a un'istanza di `IVEHandler` che gestisce gli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="1660f-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="1660f-107">in Puntatore al dominio applicazione in cui viene caricato il file.</span><span class="sxs-lookup"><span data-stu-id="1660f-107">[in] A pointer to the application domain in which the file is loaded.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="1660f-108">in Combinazione bit per bit di valori [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) , che indica le convalide da eseguire.</span><span class="sxs-lookup"><span data-stu-id="1660f-108">[in] A bitwise combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the validations that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="1660f-109">in Numero massimo di errori da consentire prima di uscire dalla convalida.</span><span class="sxs-lookup"><span data-stu-id="1660f-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="1660f-110">in Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="1660f-110">[in] Not used.</span></span>  
  
 `fileName`  
 <span data-ttu-id="1660f-111">in Stringa che specifica il nome del file da convalidare.</span><span class="sxs-lookup"><span data-stu-id="1660f-111">[in] A string that specifies the name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="1660f-112">in Puntatore al buffer di memoria in cui è archiviato il file.</span><span class="sxs-lookup"><span data-stu-id="1660f-112">[in] A pointer to the memory buffer in which the file is stored.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="1660f-113">in Dimensione, in byte, del file da convalidare.</span><span class="sxs-lookup"><span data-stu-id="1660f-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1660f-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1660f-114">Requirements</span></span>  
 <span data-ttu-id="1660f-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1660f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1660f-116">**Intestazione:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="1660f-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="1660f-117">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1660f-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1660f-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1660f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
