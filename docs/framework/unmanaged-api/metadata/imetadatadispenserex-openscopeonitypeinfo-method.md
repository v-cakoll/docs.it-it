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
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43456532"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="49fdc-102">Metodo IMetaDataDispenserEx::OpenScopeOnITypeInfo</span><span class="sxs-lookup"><span data-stu-id="49fdc-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="49fdc-103">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="49fdc-103">This method is not implemented.</span></span> <span data-ttu-id="49fdc-104">Se chiamato, viene restituito E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="49fdc-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49fdc-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="49fdc-105">Syntax</span></span>  
  
```  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="49fdc-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="49fdc-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="49fdc-107">[in] Puntatore a un [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interfaccia che fornisce le informazioni sul tipo in cui aprire l'ambito.</span><span class="sxs-lookup"><span data-stu-id="49fdc-107">[in] Pointer to an [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="49fdc-108">[in] I flag di modalità di apertura.</span><span class="sxs-lookup"><span data-stu-id="49fdc-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="49fdc-109">[in] L'interfaccia desiderata.</span><span class="sxs-lookup"><span data-stu-id="49fdc-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="49fdc-110">[out] Puntatore a un puntatore a interfaccia restituito.</span><span class="sxs-lookup"><span data-stu-id="49fdc-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49fdc-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="49fdc-111">Requirements</span></span>  
 <span data-ttu-id="49fdc-112">**Piattaforma:** visualizzare [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49fdc-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49fdc-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="49fdc-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="49fdc-114">**Libreria:** usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="49fdc-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="49fdc-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49fdc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49fdc-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49fdc-116">See Also</span></span>  
 [<span data-ttu-id="49fdc-117">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="49fdc-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="49fdc-118">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="49fdc-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
