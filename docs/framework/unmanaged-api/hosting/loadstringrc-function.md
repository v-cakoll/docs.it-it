---
title: Funzione LoadStringRC
ms.date: 03/30/2017
api_name:
- LoadStringRC
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRC
helpviewer_keywords:
- LoadStringRC function [.NET Framework hosting]
ms.assetid: 752e49b4-987c-4c28-a118-1a0c1ed510c5
topic_type:
- apiref
ms.openlocfilehash: 8bd0292ddf22453f8892ed8bddd10c2144877097
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008515"
---
# <a name="loadstringrc-function"></a><span data-ttu-id="17e6c-102">Funzione LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="17e6c-102">LoadStringRC Function</span></span>
<span data-ttu-id="17e6c-103">Converte un valore HRESULT in un messaggio di errore utilizzando le impostazioni cultura predefinite del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="17e6c-103">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 <span data-ttu-id="17e6c-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="17e6c-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17e6c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="17e6c-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17e6c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="17e6c-106">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="17e6c-107">[in] Un HRESULT.</span><span class="sxs-lookup"><span data-stu-id="17e6c-107">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="17e6c-108">out Un buffer che contiene il messaggio di errore al completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="17e6c-108">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="17e6c-109">in Dimensioni del buffer dei messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="17e6c-109">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="17e6c-110">in Ignorato.</span><span class="sxs-lookup"><span data-stu-id="17e6c-110">[in] Ignored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="17e6c-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="17e6c-111">Return Value</span></span>  
 <span data-ttu-id="17e6c-112">Questo metodo restituisce i codici di errore standard Component Object Model (COM), come definito in WinError. h, oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="17e6c-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="17e6c-113">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="17e6c-113">Return code</span></span>|<span data-ttu-id="17e6c-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="17e6c-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="17e6c-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="17e6c-115">S_OK</span></span>|<span data-ttu-id="17e6c-116">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="17e6c-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="17e6c-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="17e6c-117">E_INVALIDARG</span></span>|<span data-ttu-id="17e6c-118">`szBuffer`è null o `iMax` è zero (0).</span><span class="sxs-lookup"><span data-stu-id="17e6c-118">`szBuffer` is null or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17e6c-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="17e6c-119">Remarks</span></span>  
 <span data-ttu-id="17e6c-120">Se il metodo non viene completato correttamente, `szBuffer` contiene una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="17e6c-120">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17e6c-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="17e6c-121">Requirements</span></span>  
 <span data-ttu-id="17e6c-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17e6c-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17e6c-123">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="17e6c-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="17e6c-124">**Libreria:** MSCorEE. dll e mscorwks. dll.</span><span class="sxs-lookup"><span data-stu-id="17e6c-124">**Library:** MSCorEE.dll and Mscorwks.dll.</span></span> <span data-ttu-id="17e6c-125">Utilizzare MSCorEE. dll invece di mscorwks. dll per assicurarsi di avere come destinazione la versione corretta del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="17e6c-125">Use MSCorEE.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="17e6c-126">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17e6c-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17e6c-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17e6c-127">See also</span></span>

- [<span data-ttu-id="17e6c-128">Funzione LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="17e6c-128">LoadStringRCEx Function</span></span>](loadstringrcex-function.md)
- [<span data-ttu-id="17e6c-129">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="17e6c-129">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
