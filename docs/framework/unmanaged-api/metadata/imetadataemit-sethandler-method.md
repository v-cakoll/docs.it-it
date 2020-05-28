---
title: Metodo IMetaDataEmit::SetHandler
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetHandler
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetHandler
helpviewer_keywords:
- IMetaDataEmit::SetHandler method [.NET Framework metadata]
- SetHandler method [.NET Framework metadata]
ms.assetid: c6c1aaaf-e2cd-407c-b73e-fbe6ffd83bb3
topic_type:
- apiref
ms.openlocfilehash: 4fa227d18b8cb10936d93fda9bcaf413ce63ca3b
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003942"
---
# <a name="imetadataemitsethandler-method"></a><span data-ttu-id="3c138-102">Metodo IMetaDataEmit::SetHandler</span><span class="sxs-lookup"><span data-stu-id="3c138-102">IMetaDataEmit::SetHandler Method</span></span>
<span data-ttu-id="3c138-103">Imposta il metodo a cui fa riferimento il `IUnknown` puntatore specificato come callback di notifica per i mapping del token.</span><span class="sxs-lookup"><span data-stu-id="3c138-103">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c138-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3c138-104">Syntax</span></span>  
  
```cpp  
HRESULT SetHandler (
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c138-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3c138-105">Parameters</span></span>  
 `pUnk`  
 <span data-ttu-id="3c138-106">in Gestore da registrare.</span><span class="sxs-lookup"><span data-stu-id="3c138-106">[in] The handler to register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c138-107">Commenti</span><span class="sxs-lookup"><span data-stu-id="3c138-107">Remarks</span></span>  
 <span data-ttu-id="3c138-108">Il motore dei metadati invia una notifica tramite il metodo fornito da `SetHandler` , a compilatori che non generano record in modo ottimizzato e che desiderano ottimizzare i record salvati.</span><span class="sxs-lookup"><span data-stu-id="3c138-108">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span></span>  
  
 <span data-ttu-id="3c138-109">Se il metodo di callback non viene fornito tramite `SetHandler` , non verrà eseguita alcuna ottimizzazione al salvataggio, tranne nel caso in cui diversi ambiti di importazione siano Stati Uniti utilizzando `IMapToken` il merge per ogni ambito.</span><span class="sxs-lookup"><span data-stu-id="3c138-109">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c138-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3c138-110">Requirements</span></span>  
 <span data-ttu-id="3c138-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c138-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c138-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3c138-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3c138-113">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3c138-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3c138-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c138-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c138-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c138-115">See also</span></span>

- [<span data-ttu-id="3c138-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="3c138-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="3c138-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="3c138-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
