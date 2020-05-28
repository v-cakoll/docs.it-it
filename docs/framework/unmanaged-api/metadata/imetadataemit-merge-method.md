---
title: Metodo IMetaDataEmit::Merge
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Merge
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Merge
helpviewer_keywords:
- IMetaDataEmit::Merge method [.NET Framework metadata]
- Merge method [.NET Framework metadata]
ms.assetid: 7596220c-f699-4b6c-8ae7-c83220610650
topic_type:
- apiref
ms.openlocfilehash: e7fe5cbe27c0771a71e4c03d14ab68ada7d0741a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004175"
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="f060c-102">Metodo IMetaDataEmit::Merge</span><span class="sxs-lookup"><span data-stu-id="f060c-102">IMetaDataEmit::Merge Method</span></span>
<span data-ttu-id="f060c-103">Aggiunge l'ambito importato specificato all'elenco di ambiti da unire.</span><span class="sxs-lookup"><span data-stu-id="f060c-103">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f060c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f060c-104">Syntax</span></span>  
  
```cpp  
HRESULT Merge (
    [in]  IMetaDataImport  *pImport,
    [in]  IMapToken        *pHostMapToken,
    [in]  IUnknown         *pHandler
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f060c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f060c-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="f060c-106">in Puntatore a un oggetto [IMetaDataImport](imetadataimport-interface.md) che identifica l'ambito importato da unire.</span><span class="sxs-lookup"><span data-stu-id="f060c-106">[in] A pointer to an [IMetaDataImport](imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="f060c-107">in Puntatore a un oggetto [IMapToken](imaptoken-interface.md) che specifica il mapping di nuovo token.</span><span class="sxs-lookup"><span data-stu-id="f060c-107">[in] A pointer to an [IMapToken](imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandler`  
 <span data-ttu-id="f060c-108">in Puntatore a un oggetto [IUnknown](/cpp/atl/iunknown) che specifica gli errori.</span><span class="sxs-lookup"><span data-stu-id="f060c-108">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f060c-109">Commenti</span><span class="sxs-lookup"><span data-stu-id="f060c-109">Remarks</span></span>  
 <span data-ttu-id="f060c-110">Chiamare [IMetaDataEmit:: MergeEnd](imetadataemit-mergeend-method.md) per attivare l'Unione dei metadati in un singolo ambito.</span><span class="sxs-lookup"><span data-stu-id="f060c-110">Call [IMetaDataEmit::MergeEnd](imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f060c-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f060c-111">Requirements</span></span>  
 <span data-ttu-id="f060c-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f060c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f060c-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f060c-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f060c-114">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f060c-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f060c-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f060c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f060c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f060c-116">See also</span></span>

- [<span data-ttu-id="f060c-117">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="f060c-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="f060c-118">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="f060c-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
