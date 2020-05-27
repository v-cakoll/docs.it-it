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
ms.openlocfilehash: 688abd210cca193bf03c40f000b74ecb66eb8ede
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008547"
---
# <a name="ivalidatorvalidate-method"></a><span data-ttu-id="04a0f-102">Metodo IValidator::Validate</span><span class="sxs-lookup"><span data-stu-id="04a0f-102">IValidator::Validate Method</span></span>
<span data-ttu-id="04a0f-103">Convalida il file eseguibile portabile (PE) o il file MSIL (Microsoft Intermediate Language) specificato.</span><span class="sxs-lookup"><span data-stu-id="04a0f-103">Validates the specified portable executable (PE) or Microsoft intermediate language (MSIL) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04a0f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="04a0f-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="04a0f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="04a0f-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="04a0f-106">in Puntatore a un' `IVEHandler` istanza di che gestisce gli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="04a0f-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="04a0f-107">in Puntatore al dominio applicazione in cui viene caricato il file.</span><span class="sxs-lookup"><span data-stu-id="04a0f-107">[in] A pointer to the application domain in which the file is loaded.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="04a0f-108">in Combinazione bit per bit di valori [ValidatorFlags](validatorflags-enumeration.md) , che indica le convalide da eseguire.</span><span class="sxs-lookup"><span data-stu-id="04a0f-108">[in] A bitwise combination of [ValidatorFlags](validatorflags-enumeration.md) values, indicating the validations that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="04a0f-109">in Numero massimo di errori da consentire prima di uscire dalla convalida.</span><span class="sxs-lookup"><span data-stu-id="04a0f-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="04a0f-110">[in] Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="04a0f-110">[in] Not used.</span></span>  
  
 `fileName`  
 <span data-ttu-id="04a0f-111">in Stringa che specifica il nome del file da convalidare.</span><span class="sxs-lookup"><span data-stu-id="04a0f-111">[in] A string that specifies the name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="04a0f-112">in Puntatore al buffer di memoria in cui è archiviato il file.</span><span class="sxs-lookup"><span data-stu-id="04a0f-112">[in] A pointer to the memory buffer in which the file is stored.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="04a0f-113">in Dimensione, in byte, del file da convalidare.</span><span class="sxs-lookup"><span data-stu-id="04a0f-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04a0f-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="04a0f-114">Requirements</span></span>  
 <span data-ttu-id="04a0f-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04a0f-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04a0f-116">**Intestazione:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="04a0f-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="04a0f-117">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="04a0f-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="04a0f-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04a0f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
