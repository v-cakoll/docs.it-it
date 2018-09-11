---
title: Metodo IMetaDataDispenserEx::OpenScopeOnITypeInfo
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.OpenScopeOnITypeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::OpenScopeOnITypeInfo
helpviewer_keywords:
- OpenScopeOnITypeInfo method [.NET Framework metadata]
- IMetaDataDispenserEx::OpenScopeOnITypeInfo method [.NET Framework metadata]
ms.assetid: 3480bbdb-c442-44a0-b7c6-333354503c52
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d5fd96f390b0bba60d1b95d20273bbf670208d41
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/11/2018
ms.locfileid: "44360979"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="c9d8a-102">Metodo IMetaDataDispenserEx::OpenScopeOnITypeInfo</span><span class="sxs-lookup"><span data-stu-id="c9d8a-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="c9d8a-103">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="c9d8a-103">This method is not implemented.</span></span> <span data-ttu-id="c9d8a-104">Se chiamato, viene restituito E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="c9d8a-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9d8a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c9d8a-105">Syntax</span></span>  
  
```  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c9d8a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c9d8a-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="c9d8a-107">[in] Puntatore a un [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interfaccia che fornisce le informazioni sul tipo in cui aprire l'ambito.</span><span class="sxs-lookup"><span data-stu-id="c9d8a-107">[in] Pointer to an [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="c9d8a-108">[in] I flag di modalità di apertura.</span><span class="sxs-lookup"><span data-stu-id="c9d8a-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="c9d8a-109">[in] L'interfaccia desiderata.</span><span class="sxs-lookup"><span data-stu-id="c9d8a-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="c9d8a-110">[out] Puntatore a un puntatore a interfaccia restituito.</span><span class="sxs-lookup"><span data-stu-id="c9d8a-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9d8a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c9d8a-111">Requirements</span></span>  
 <span data-ttu-id="c9d8a-112">**Piattaforma:** visualizzare [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9d8a-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9d8a-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c9d8a-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c9d8a-114">**Libreria:** usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c9d8a-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c9d8a-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9d8a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9d8a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9d8a-116">See Also</span></span>  
 [<span data-ttu-id="c9d8a-117">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="c9d8a-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="c9d8a-118">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="c9d8a-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
