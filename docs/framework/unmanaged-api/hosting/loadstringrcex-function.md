---
title: Funzione LoadStringRCEx
ms.date: 03/30/2017
api_name:
- LoadStringRCEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRCEx
helpviewer_keywords:
- LoadStringRCEx function [.NET Framework hosting]
ms.assetid: bc789636-ca14-4f07-8f77-9305874d7495
topic_type:
- apiref
ms.openlocfilehash: a05cbe985c2cfebb67756fdfb54398b36e87f441
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008514"
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="6b469-102">Funzione LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="6b469-102">LoadStringRCEx Function</span></span>
<span data-ttu-id="6b469-103">Converte un valore HRESULT in un messaggio di errore appropriato per le impostazioni cultura specificate.</span><span class="sxs-lookup"><span data-stu-id="6b469-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="6b469-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="6b469-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b469-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6b469-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,
    [in]  UINT    iResouceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet,
    [out] int    *pcwchUsed  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b469-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="6b469-106">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="6b469-107">in Identificatore di impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="6b469-107">[in] A culture identifier.</span></span> <span data-ttu-id="6b469-108">Passare-1 per per `lcid` usare le impostazioni cultura predefinite.</span><span class="sxs-lookup"><span data-stu-id="6b469-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="6b469-109">[in] Un HRESULT.</span><span class="sxs-lookup"><span data-stu-id="6b469-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="6b469-110">out Un buffer che contiene il messaggio di errore al completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="6b469-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="6b469-111">in Dimensioni del buffer dei messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="6b469-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="6b469-112">in Ignorato.</span><span class="sxs-lookup"><span data-stu-id="6b469-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="6b469-113">out Puntatore alla lunghezza del messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="6b469-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6b469-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6b469-114">Return Value</span></span>  
 <span data-ttu-id="6b469-115">Questo metodo restituisce i codici di errore COM standard, come definito in WinError. h, oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="6b469-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="6b469-116">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="6b469-116">Return code</span></span>|<span data-ttu-id="6b469-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6b469-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="6b469-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="6b469-118">S_OK</span></span>|<span data-ttu-id="6b469-119">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="6b469-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="6b469-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="6b469-120">E_INVALIDARG</span></span>|<span data-ttu-id="6b469-121">`szBuffer`è null o `iMax` è zero (0).</span><span class="sxs-lookup"><span data-stu-id="6b469-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b469-122">Commenti</span><span class="sxs-lookup"><span data-stu-id="6b469-122">Remarks</span></span>  
 <span data-ttu-id="6b469-123">Se il metodo non viene completato correttamente, `szBuffer` contiene una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="6b469-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b469-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6b469-124">Requirements</span></span>  
 <span data-ttu-id="6b469-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b469-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b469-126">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6b469-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6b469-127">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6b469-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6b469-128">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b469-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b469-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b469-129">See also</span></span>

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [<span data-ttu-id="6b469-130">Funzione LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="6b469-130">LoadStringRC Function</span></span>](loadstringrc-function.md)
- [<span data-ttu-id="6b469-131">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="6b469-131">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
