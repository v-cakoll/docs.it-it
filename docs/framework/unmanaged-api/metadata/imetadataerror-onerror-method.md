---
title: Metodo IMetaDataError::OnError
ms.date: 03/30/2017
api_name:
- IMetaDataError.OnError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError::OnError
helpviewer_keywords:
- IMetaDataError::OnError method [.NET Framework metadata]
- OnError method, IMetaDataError interface [.NET Framework metadata]
ms.assetid: c1e744b8-a6fb-4d9c-a971-8babc875d8f0
topic_type:
- apiref
ms.openlocfilehash: d2252f58af1a319d953fb320a99fad1cfec3dca0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492720"
---
# <a name="imetadataerroronerror-method"></a><span data-ttu-id="e974d-102">Metodo IMetaDataError::OnError</span><span class="sxs-lookup"><span data-stu-id="e974d-102">IMetaDataError::OnError Method</span></span>
<span data-ttu-id="e974d-103">Fornisce la notifica degli errori che si verificano durante l'Unione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="e974d-103">Provides notification of errors that occur during the metadata merge.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e974d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e974d-104">Syntax</span></span>  
  
```cpp  
HRESULT OnError (  
    [in] HRESULT   hrError,
    [in] mdToken   token  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e974d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e974d-105">Parameters</span></span>  
 `hrError`  
 <span data-ttu-id="e974d-106">in Valore HRESULT Error restituito al metodo chiamante.</span><span class="sxs-lookup"><span data-stu-id="e974d-106">[in] The HRESULT error value returned to the calling method.</span></span>  
  
 `token`  
 <span data-ttu-id="e974d-107">in Token di metadati dell'oggetto di codice da unire quando si è verificato l'errore.</span><span class="sxs-lookup"><span data-stu-id="e974d-107">[in] The metadata token of the code object that was being merged when the error occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e974d-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e974d-108">Requirements</span></span>  
 <span data-ttu-id="e974d-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e974d-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e974d-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e974d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e974d-111">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e974d-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e974d-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e974d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e974d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e974d-113">See also</span></span>

- [<span data-ttu-id="e974d-114">Interfaccia IMetaDataError</span><span class="sxs-lookup"><span data-stu-id="e974d-114">IMetaDataError Interface</span></span>](imetadataerror-interface.md)
