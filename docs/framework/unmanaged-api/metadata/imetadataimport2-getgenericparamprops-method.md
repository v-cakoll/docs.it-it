---
title: Metodo IMetaDataImport2::GetGenericParamProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamProps method [.NET Framework metadata]
- GetGenericParamProps method [.NET Framework metadata]
ms.assetid: dbb21e67-712b-49e7-a27c-a1e73ffd46c5
topic_type:
- apiref
ms.openlocfilehash: 7e97b2d4ad1fec4675d1484959b115a4d4b87e90
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490614"
---
# <a name="imetadataimport2getgenericparamprops-method"></a><span data-ttu-id="08534-102">Metodo IMetaDataImport2::GetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="08534-102">IMetaDataImport2::GetGenericParamProps Method</span></span>
<span data-ttu-id="08534-103">Ottiene i metadati associati al parametro generico rappresentato dal token specificato.</span><span class="sxs-lookup"><span data-stu-id="08534-103">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08534-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="08534-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGenericParamProps (  
   [in]  mdGenericParam  gp,  
   [out] ULONG           *pulParamSeq,  
   [out] DWORD           *pdwParamFlags,  
   [out] mdToken         *ptOwner,  
   [out] DWORD           *reserved,  
   [out] LPWSTR          wzName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08534-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="08534-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="08534-106">in Token che rappresenta il parametro generico per il quale restituire i metadati.</span><span class="sxs-lookup"><span data-stu-id="08534-106">[in] The token that represents the generic parameter for which to return metadata.</span></span>  
  
 `pulParamSeq`  
 <span data-ttu-id="08534-107">out Posizione ordinale del `Type` parametro nel costruttore o metodo padre.</span><span class="sxs-lookup"><span data-stu-id="08534-107">[out] The ordinal position of the `Type` parameter in the parent constructor or method.</span></span>  
  
 `pdwParamFlags`  
 <span data-ttu-id="08534-108">out Valore dell'enumerazione [CorGenericParamAttr](corgenericparamattr-enumeration.md) che descrive l'oggetto `Type` per il parametro generico.</span><span class="sxs-lookup"><span data-stu-id="08534-108">[out] A value of the [CorGenericParamAttr](corgenericparamattr-enumeration.md) enumeration that describes the `Type` for the generic parameter.</span></span>  
  
 `ptOwner`  
 <span data-ttu-id="08534-109">out Token TypeDef o MethodDef che rappresenta il proprietario del parametro.</span><span class="sxs-lookup"><span data-stu-id="08534-109">[out] A TypeDef or MethodDef token that represents the owner of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="08534-110">out Riservato per l'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="08534-110">[out] Reserved for future extensibility.</span></span>  
  
 `wzName`  
 <span data-ttu-id="08534-111">out Nome del parametro generico.</span><span class="sxs-lookup"><span data-stu-id="08534-111">[out] The name of the generic parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="08534-112">in Dimensioni del `wzName` buffer.</span><span class="sxs-lookup"><span data-stu-id="08534-112">[in] The size of the `wzName` buffer.</span></span>  
  
 `pchName`  
 <span data-ttu-id="08534-113">out Dimensioni restituite del nome, in caratteri wide.</span><span class="sxs-lookup"><span data-stu-id="08534-113">[out] The returned size of the name, in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08534-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="08534-114">Requirements</span></span>  
 <span data-ttu-id="08534-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08534-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08534-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="08534-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="08534-117">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="08534-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="08534-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08534-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08534-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08534-119">See also</span></span>

- [<span data-ttu-id="08534-120">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="08534-120">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="08534-121">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="08534-121">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
