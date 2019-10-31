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
ms.openlocfilehash: 9b3a6bab8672f3ef3fca5f89c60b03a43477cce5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123303"
---
# <a name="ivalidatorformateventinfo-method"></a><span data-ttu-id="b1bc8-102">Metodo IValidator::FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="b1bc8-102">IValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="b1bc8-103">Ottiene il messaggio di errore corrispondente all'errore di convalida specificato.</span><span class="sxs-lookup"><span data-stu-id="b1bc8-103">Gets the error message corresponding to the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1bc8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b1bc8-104">Syntax</span></span>  
  
```cpp  
HRESULT FormatEventInfo(  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1bc8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b1bc8-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="b1bc8-106">in Valore HRESULT passato al gestore degli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="b1bc8-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="b1bc8-107">in Istanza `VEContext` contenente le informazioni di contesto sull'errore di convalida.</span><span class="sxs-lookup"><span data-stu-id="b1bc8-107">[in] A `VEContext` instance that contains context information about the validation error.</span></span>  
  
 `msg`  
 <span data-ttu-id="b1bc8-108">[in, out] Stringa che contiene il messaggio di errore restituito.</span><span class="sxs-lookup"><span data-stu-id="b1bc8-108">[in, out] A string that contains the returned error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="b1bc8-109">in Lunghezza massima del messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="b1bc8-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="b1bc8-110">in Matrice sicura che contiene parametri aggiuntivi che descrivono l'errore.</span><span class="sxs-lookup"><span data-stu-id="b1bc8-110">[in] A safe array that contains additional parameters describing the error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1bc8-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b1bc8-111">Requirements</span></span>  
 <span data-ttu-id="b1bc8-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1bc8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1bc8-113">**Intestazione:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="b1bc8-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="b1bc8-114">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b1bc8-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b1bc8-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1bc8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
