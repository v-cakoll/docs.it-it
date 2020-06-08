---
title: Metodo IMetaDataImport::EnumModuleRefs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumModuleRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumModuleRefs
helpviewer_keywords:
- EnumModuleRefs method [.NET Framework metadata]
- IMetaDataImport::EnumModuleRefs method [.NET Framework metadata]
ms.assetid: 53441f3a-68d2-477c-906e-37c55dfcfb4d
topic_type:
- apiref
ms.openlocfilehash: fe7350e6d8e400ae37b5b8b7854a56f3c5c53ea7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491751"
---
# <a name="imetadataimportenummodulerefs-method"></a><span data-ttu-id="49bcd-102">Metodo IMetaDataImport::EnumModuleRefs</span><span class="sxs-lookup"><span data-stu-id="49bcd-102">IMetaDataImport::EnumModuleRefs Method</span></span>
<span data-ttu-id="49bcd-103">Enumera i token ModuleRef che rappresentano i moduli importati.</span><span class="sxs-lookup"><span data-stu-id="49bcd-103">Enumerates ModuleRef tokens that represent imported modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49bcd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="49bcd-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleRefs (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdModuleRef  rModuleRefs[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcModuleRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49bcd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="49bcd-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="49bcd-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="49bcd-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="49bcd-107">Deve essere NULL per la prima chiamata di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="49bcd-107">This must be NULL for the first call of this method.</span></span>  
  
 `rModuleRefs`  
 <span data-ttu-id="49bcd-108">out Matrice utilizzata per archiviare i token ModuleRef.</span><span class="sxs-lookup"><span data-stu-id="49bcd-108">[out] The array used to store the ModuleRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="49bcd-109">[in] Dimensione massima della matrice `rModuleRefs`.</span><span class="sxs-lookup"><span data-stu-id="49bcd-109">[in] The maximum size of the `rModuleRefs` array.</span></span>  
  
 `pcModuleRefs`  
 <span data-ttu-id="49bcd-110">out Numero di token ModuleRef restituiti in `rModuleRefs` .</span><span class="sxs-lookup"><span data-stu-id="49bcd-110">[out] The number of ModuleRef tokens returned in `rModuleRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49bcd-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="49bcd-111">Return Value</span></span>  
  
|<span data-ttu-id="49bcd-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="49bcd-112">HRESULT</span></span>|<span data-ttu-id="49bcd-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49bcd-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="49bcd-114">`EnumModuleRefs`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="49bcd-114">`EnumModuleRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="49bcd-115">Nessun token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="49bcd-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="49bcd-116">In tal caso, `pcModuleRefs` è zero.</span><span class="sxs-lookup"><span data-stu-id="49bcd-116">In that case, `pcModuleRefs` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="49bcd-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="49bcd-117">Requirements</span></span>  
 <span data-ttu-id="49bcd-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49bcd-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49bcd-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="49bcd-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="49bcd-120">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="49bcd-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="49bcd-121">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49bcd-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49bcd-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49bcd-122">See also</span></span>

- [<span data-ttu-id="49bcd-123">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="49bcd-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="49bcd-124">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="49bcd-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
