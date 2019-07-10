---
title: Metodo IValidator::FormatEventInfo
ms.date: 03/30/2017
api_name:
- IValidator.FormatEventInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FormatEventInfo
helpviewer_keywords:
- IValidator::FormatEventInfo method [.NET Framework hosting]
- FormatEventInfo method, IValidator interface [.NET Framework hosting]
ms.assetid: 4c0c7477-05ba-461b-b21b-cbfba95f1db1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31329a8674a9991a3f306eeff44ee3437ad64a5c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779429"
---
# <a name="ivalidatorformateventinfo-method"></a><span data-ttu-id="03705-102">Metodo IValidator::FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="03705-102">IValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="03705-103">Ottiene il messaggio di errore corrispondente all'errore di convalida specificato.</span><span class="sxs-lookup"><span data-stu-id="03705-103">Gets the error message corresponding to the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03705-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="03705-104">Syntax</span></span>  
  
```cpp  
HRESULT FormatEventInfo(  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03705-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="03705-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="03705-106">[in] Il valore HRESULT passato al gestore di errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="03705-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="03705-107">[in] Oggetto `VEContext` istanza che contiene informazioni contestuali relative all'errore di convalida.</span><span class="sxs-lookup"><span data-stu-id="03705-107">[in] A `VEContext` instance that contains context information about the validation error.</span></span>  
  
 `msg`  
 <span data-ttu-id="03705-108">[in, out] Stringa che contiene il messaggio di errore restituito.</span><span class="sxs-lookup"><span data-stu-id="03705-108">[in, out] A string that contains the returned error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="03705-109">[in] La lunghezza massima del messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="03705-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="03705-110">[in] Una matrice protetta contenente parametri aggiuntivi che descrive l'errore.</span><span class="sxs-lookup"><span data-stu-id="03705-110">[in] A safe array that contains additional parameters describing the error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03705-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="03705-111">Requirements</span></span>  
 <span data-ttu-id="03705-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03705-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03705-113">**Intestazione:** IValidator. idl, IValidator. H</span><span class="sxs-lookup"><span data-stu-id="03705-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="03705-114">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="03705-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="03705-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03705-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
