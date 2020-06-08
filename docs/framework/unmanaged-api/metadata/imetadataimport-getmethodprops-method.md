---
title: Metodo IMetaDataImport::GetMethodProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodProps
helpviewer_keywords:
- GetMethodProps method [.NET Framework metadata]
- IMetaDataImport::GetMethodProps method [.NET Framework metadata]
ms.assetid: e0667ef7-1d31-4c89-a2d3-d426f023f8d2
topic_type:
- apiref
ms.openlocfilehash: 3c7c3525f2f8753241c9a206e4cf5e552bf06efe
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503627"
---
# <a name="imetadataimportgetmethodprops-method"></a><span data-ttu-id="47518-102">Metodo IMetaDataImport::GetMethodProps</span><span class="sxs-lookup"><span data-stu-id="47518-102">IMetaDataImport::GetMethodProps Method</span></span>
<span data-ttu-id="47518-103">Ottiene i metadati associati al metodo a cui fa riferimento il token MethodDef specificato.</span><span class="sxs-lookup"><span data-stu-id="47518-103">Gets the metadata associated with the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47518-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="47518-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodProps (  
    [in]  mdMethodDef         mb,  
    [out] mdTypeDef           *pClass,  
    [out] LPWSTR              szMethod,  
    [in]  ULONG               cchMethod,  
    [out] ULONG               *pchMethod,  
    [out] DWORD               *pdwAttr,  
    [out] PCCOR_SIGNATURE     *ppvSigBlob,  
    [out] ULONG               *pcbSigBlob,  
    [out] ULONG               *pulCodeRVA,  
    [out] DWORD               *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47518-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="47518-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="47518-106">in Token MethodDef che rappresenta il metodo per il quale restituire i metadati.</span><span class="sxs-lookup"><span data-stu-id="47518-106">[in] The MethodDef token that represents the method to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="47518-107">out Puntatore a un token TypeDef che rappresenta il tipo che implementa il metodo.</span><span class="sxs-lookup"><span data-stu-id="47518-107">[out] A Pointer to a TypeDef token that represents the type that implements the method.</span></span>  
  
 `szMethod`  
 <span data-ttu-id="47518-108">out Puntatore a un buffer con il nome del metodo.</span><span class="sxs-lookup"><span data-stu-id="47518-108">[out] A Pointer to a buffer that has the method's name.</span></span>  
  
 `cchMethod`  
 <span data-ttu-id="47518-109">in Dimensione richiesta di `szMethod` .</span><span class="sxs-lookup"><span data-stu-id="47518-109">[in] The requested size of `szMethod`.</span></span>  
  
 `pchMethod`  
 <span data-ttu-id="47518-110">out Un puntatore alla dimensione in caratteri wide di `szMethod` o, nel caso di troncamento, il numero effettivo di caratteri wide nel nome del metodo.</span><span class="sxs-lookup"><span data-stu-id="47518-110">[out] A Pointer to the size in wide characters of `szMethod`, or in the case of truncation, the actual number of wide characters in the method name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="47518-111">out Puntatore a qualsiasi flag associato al metodo.</span><span class="sxs-lookup"><span data-stu-id="47518-111">[out] A pointer to any flags associated with the method.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="47518-112">out Puntatore alla firma dei metadati binari del metodo.</span><span class="sxs-lookup"><span data-stu-id="47518-112">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="47518-113">out Puntatore alla dimensione in byte di `ppvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="47518-113">[out] A Pointer to the size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="47518-114">out Puntatore all'indirizzo virtuale relativo del metodo.</span><span class="sxs-lookup"><span data-stu-id="47518-114">[out] A pointer to the relative virtual address of the method.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="47518-115">out Puntatore a tutti i flag di implementazione per il metodo.</span><span class="sxs-lookup"><span data-stu-id="47518-115">[out] A pointer to any implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47518-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="47518-116">Requirements</span></span>  
 <span data-ttu-id="47518-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47518-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47518-118">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="47518-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="47518-119">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="47518-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="47518-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47518-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47518-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47518-121">See also</span></span>

- [<span data-ttu-id="47518-122">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="47518-122">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="47518-123">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="47518-123">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
