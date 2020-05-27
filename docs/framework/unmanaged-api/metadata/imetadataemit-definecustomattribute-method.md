---
title: Metodo IMetaDataEmit::DefineCustomAttribute
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineCustomAttribute
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineCustomAttribute
helpviewer_keywords:
- DefineCustomAttribute method [.NET Framework metadata]
- IMetaDataEmit::DefineCustomAttribute method [.NET Framework metadata]
ms.assetid: 7dd14854-b756-4401-b167-88ca576dc8f0
topic_type:
- apiref
ms.openlocfilehash: 17757df566ba8d141e7adec00dcc1f75959d0e00
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005627"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="2ff17-102">Metodo IMetaDataEmit::DefineCustomAttribute</span><span class="sxs-lookup"><span data-stu-id="2ff17-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="2ff17-103">Crea una definizione per un attributo personalizzato con la firma dei metadati specificata, da allegare all'oggetto specificato e ottiene un token per la definizione di attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2ff17-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ff17-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ff17-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineCustomAttribute (
    [in]  mdToken     tkObj,
    [in]  mdToken     tkType,
    [in]  void const  *pCustomAttribute,
    [in]  ULONG       cbCustomAttribute,
    [out] mdCustomAttribute *pcv
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ff17-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2ff17-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="2ff17-106">in Token per l'elemento proprietario.</span><span class="sxs-lookup"><span data-stu-id="2ff17-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="2ff17-107">in Token che identifica l'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2ff17-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="2ff17-108">in Puntatore all'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2ff17-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="2ff17-109">in Numero di byte in `pCustomAttribute` .</span><span class="sxs-lookup"><span data-stu-id="2ff17-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="2ff17-110">out `mdCustomAttribute`Token assegnato.</span><span class="sxs-lookup"><span data-stu-id="2ff17-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ff17-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2ff17-111">Requirements</span></span>  
 <span data-ttu-id="2ff17-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ff17-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ff17-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2ff17-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2ff17-114">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2ff17-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2ff17-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ff17-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ff17-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ff17-116">See also</span></span>

- [<span data-ttu-id="2ff17-117">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="2ff17-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="2ff17-118">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="2ff17-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
