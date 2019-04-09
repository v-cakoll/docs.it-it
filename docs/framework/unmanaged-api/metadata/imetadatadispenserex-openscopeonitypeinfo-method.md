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
ms.openlocfilehash: deecd9ed4161bbd72e97a6320188961ae76d1e7c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218784"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="1bf77-102">Metodo IMetaDataDispenserEx::OpenScopeOnITypeInfo</span><span class="sxs-lookup"><span data-stu-id="1bf77-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="1bf77-103">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="1bf77-103">This method is not implemented.</span></span> <span data-ttu-id="1bf77-104">Se chiamato, viene restituito E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="1bf77-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bf77-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1bf77-105">Syntax</span></span>  
  
```  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1bf77-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="1bf77-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="1bf77-107">[in] Puntatore a un [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interfaccia che fornisce le informazioni sul tipo in cui aprire l'ambito.</span><span class="sxs-lookup"><span data-stu-id="1bf77-107">[in] Pointer to an [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="1bf77-108">[in] I flag di modalità di apertura.</span><span class="sxs-lookup"><span data-stu-id="1bf77-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="1bf77-109">[in] L'interfaccia desiderata.</span><span class="sxs-lookup"><span data-stu-id="1bf77-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="1bf77-110">[out] Puntatore a un puntatore a interfaccia restituito.</span><span class="sxs-lookup"><span data-stu-id="1bf77-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bf77-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1bf77-111">Requirements</span></span>  
 <span data-ttu-id="1bf77-112">**Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bf77-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bf77-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1bf77-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1bf77-114">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="1bf77-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="1bf77-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="1bf77-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1bf77-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bf77-116">See also</span></span>

- [<span data-ttu-id="1bf77-117">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="1bf77-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="1bf77-118">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="1bf77-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
