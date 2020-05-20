---
title: Funzione CoInitializeEE
ms.date: 03/30/2017
api_name:
- CoInitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeEE
helpviewer_keywords:
- CoInitializeEE function [.NET Framework hosting]
ms.assetid: 7e42a928-5068-4ba6-b8c3-806551a01fa8
topic_type:
- apiref
ms.openlocfilehash: 57508a2df3a49c39d25347f2a3038442c37278da
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616762"
---
# <a name="coinitializeee-function"></a><span data-ttu-id="92506-102">Funzione CoInitializeEE</span><span class="sxs-lookup"><span data-stu-id="92506-102">CoInitializeEE Function</span></span>
<span data-ttu-id="92506-103">Garantisce che il motore di esecuzione Common Language Runtime venga caricato in un processo.</span><span class="sxs-lookup"><span data-stu-id="92506-103">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="92506-104">Questa funzione è deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="92506-104">This function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="92506-105">Usare invece il metodo [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) .</span><span class="sxs-lookup"><span data-stu-id="92506-105">Use the [ICLRRuntimeHost::Start](iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92506-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="92506-106">Syntax</span></span>  
  
```cpp  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92506-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="92506-107">Parameters</span></span>  
 `fFlags`  
 <span data-ttu-id="92506-108">in Una delle costanti di enumerazione [COINITIEE](../metadata/coinitiee-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="92506-108">[in] One of the [COINITIEE](../metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="92506-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="92506-109">Return Value</span></span>  
 <span data-ttu-id="92506-110">Questo metodo restituisce i codici di errore COM standard come definito in Winerror. h e i valori nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="92506-110">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="92506-111">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="92506-111">Return code</span></span>|<span data-ttu-id="92506-112">Description</span><span class="sxs-lookup"><span data-stu-id="92506-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="92506-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="92506-113">S_OK</span></span>|<span data-ttu-id="92506-114">Il motore di esecuzione è stato caricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="92506-114">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="92506-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="92506-115">S_FALSE</span></span>|<span data-ttu-id="92506-116">Il motore di esecuzione è già caricato.</span><span class="sxs-lookup"><span data-stu-id="92506-116">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="92506-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="92506-117">E_FAIL</span></span>|<span data-ttu-id="92506-118">Non è stato possibile caricare il motore di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="92506-118">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92506-119">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="92506-119">Remarks</span></span>  
 <span data-ttu-id="92506-120">Questo metodo carica il motore di esecuzione se non è stato caricato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="92506-120">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92506-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="92506-121">Requirements</span></span>  
 <span data-ttu-id="92506-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92506-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92506-123">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="92506-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="92506-124">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="92506-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="92506-125">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92506-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92506-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92506-126">See also</span></span>

- [<span data-ttu-id="92506-127">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="92506-127">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
