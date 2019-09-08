---
title: Funzione StrongNameGetBlob
ms.date: 03/30/2017
api_name:
- StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlob
helpviewer_keywords:
- StrongNameGetBlob function [.NET Framework strong naming]
ms.assetid: 15d09166-be00-4696-913f-2c1fbc7ac2e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d5b3d1d39b5d4c5b7d4db073b3ffaf1c6b88373
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799096"
---
# <a name="strongnamegetblob-function"></a><span data-ttu-id="dcb76-102">Funzione StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="dcb76-102">StrongNameGetBlob Function</span></span>
<span data-ttu-id="dcb76-103">Completa il buffer specificato con la rappresentazione binaria del file eseguibile presente all'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="dcb76-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
 <span data-ttu-id="dcb76-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="dcb76-104">This function has been deprecated.</span></span> <span data-ttu-id="dcb76-105">Usare invece il metodo [ICLRStrongName:: StrongNameGetBlob](../hosting/iclrstrongname-strongnamegetblob-method.md) .</span><span class="sxs-lookup"><span data-stu-id="dcb76-105">Use the [ICLRStrongName::StrongNameGetBLob](../hosting/iclrstrongname-strongnamegetblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcb76-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dcb76-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dcb76-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="dcb76-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="dcb76-108">in Percorso valido del file eseguibile da caricare.</span><span class="sxs-lookup"><span data-stu-id="dcb76-108">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="dcb76-109">in Buffer in cui caricare il file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="dcb76-109">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="dcb76-110">[in, out] Dimensione massima richiesta, in byte, di `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="dcb76-110">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="dcb76-111">Al ritorno, le dimensioni effettive, in byte, `pbBlob`di.</span><span class="sxs-lookup"><span data-stu-id="dcb76-111">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dcb76-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="dcb76-112">Return Value</span></span>  
 <span data-ttu-id="dcb76-113">`true`al completamento; in caso `false`contrario,.</span><span class="sxs-lookup"><span data-stu-id="dcb76-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dcb76-114">Note</span><span class="sxs-lookup"><span data-stu-id="dcb76-114">Remarks</span></span>  
 <span data-ttu-id="dcb76-115">Se la `StrongNameGetBlob` funzione non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="dcb76-115">If the `StrongNameGetBlob` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcb76-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dcb76-116">Requirements</span></span>  
 <span data-ttu-id="dcb76-117">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcb76-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcb76-118">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="dcb76-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="dcb76-119">**Libreria** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="dcb76-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dcb76-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcb76-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcb76-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dcb76-121">See also</span></span>

- [<span data-ttu-id="dcb76-122">Metodo StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="dcb76-122">StrongNameGetBlob Method</span></span>](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="dcb76-123">Metodo StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="dcb76-123">StrongNameGetBlobFromImage Method</span></span>](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="dcb76-124">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="dcb76-124">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
