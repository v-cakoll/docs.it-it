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
ms.openlocfilehash: 91ef9eaa855ed841bc75bfaeead462f045eb1d8b
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007455"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="73c1a-102">Metodo IMetaDataDispenserEx::OpenScopeOnITypeInfo</span><span class="sxs-lookup"><span data-stu-id="73c1a-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="73c1a-103">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="73c1a-103">This method is not implemented.</span></span> <span data-ttu-id="73c1a-104">Se chiamato, restituisce E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="73c1a-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73c1a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="73c1a-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73c1a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="73c1a-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="73c1a-107">in Puntatore a un'interfaccia [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) che fornisce le informazioni sul tipo su cui aprire l'ambito.</span><span class="sxs-lookup"><span data-stu-id="73c1a-107">[in] Pointer to an [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="73c1a-108">in Flag della modalità di apertura.</span><span class="sxs-lookup"><span data-stu-id="73c1a-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="73c1a-109">in Interfaccia desiderata.</span><span class="sxs-lookup"><span data-stu-id="73c1a-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="73c1a-110">out Puntatore a un puntatore all'interfaccia restituita.</span><span class="sxs-lookup"><span data-stu-id="73c1a-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73c1a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="73c1a-111">Requirements</span></span>  
 <span data-ttu-id="73c1a-112">**Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73c1a-112">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73c1a-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="73c1a-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="73c1a-114">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="73c1a-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="73c1a-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73c1a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73c1a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73c1a-116">See also</span></span>

- [<span data-ttu-id="73c1a-117">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="73c1a-117">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="73c1a-118">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="73c1a-118">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
