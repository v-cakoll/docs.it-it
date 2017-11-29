---
title: Metodo IMetaDataDispenserEx::OpenScopeOnITypeInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenserEx.OpenScopeOnITypeInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenserEx::OpenScopeOnITypeInfo
helpviewer_keywords:
- OpenScopeOnITypeInfo method [.NET Framework metadata]
- IMetaDataDispenserEx::OpenScopeOnITypeInfo method [.NET Framework metadata]
ms.assetid: 3480bbdb-c442-44a0-b7c6-333354503c52
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a0838895870370e3003aac4967a535b44c8e7943
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="623a5-102">Metodo IMetaDataDispenserEx::OpenScopeOnITypeInfo</span><span class="sxs-lookup"><span data-stu-id="623a5-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="623a5-103">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="623a5-103">This method is not implemented.</span></span> <span data-ttu-id="623a5-104">Se chiamato, restituisce E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="623a5-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="623a5-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="623a5-105">Syntax</span></span>  
  
```  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="623a5-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="623a5-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="623a5-107">[in] Puntatore a un [ITypeInfo](http://msdn.microsoft.com/en-us/f3356463-3373-4279-bae1-953378aa2680) interfaccia che fornisce le informazioni sul tipo in cui aprire l'ambito.</span><span class="sxs-lookup"><span data-stu-id="623a5-107">[in] Pointer to an [ITypeInfo](http://msdn.microsoft.com/en-us/f3356463-3373-4279-bae1-953378aa2680) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="623a5-108">[in] I flag della modalità di apertura.</span><span class="sxs-lookup"><span data-stu-id="623a5-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="623a5-109">[in] L'interfaccia desiderata.</span><span class="sxs-lookup"><span data-stu-id="623a5-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="623a5-110">[out] Puntatore a un puntatore all'interfaccia restituita.</span><span class="sxs-lookup"><span data-stu-id="623a5-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="623a5-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="623a5-111">Requirements</span></span>  
 <span data-ttu-id="623a5-112">**Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="623a5-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="623a5-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="623a5-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="623a5-114">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="623a5-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="623a5-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="623a5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="623a5-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="623a5-116">See Also</span></span>  
 [<span data-ttu-id="623a5-117">IMetaDataDispenserEx (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="623a5-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="623a5-118">IMetaDataDispenser (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="623a5-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
