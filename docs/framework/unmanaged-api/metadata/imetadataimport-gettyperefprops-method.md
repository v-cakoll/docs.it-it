---
title: Metodo IMetaDataImport::GetTypeRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeRefProps
helpviewer_keywords:
- IMetaDataImport::GetTypeRefProps method [.NET Framework metadata]
- GetTypeRefProps method [.NET Framework metadata]
ms.assetid: 01837955-ce1e-4068-b338-fd473bd77d1d
topic_type:
- apiref
ms.openlocfilehash: 273922e00c3e5319d5a03652cc77b69f4479ea67
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503523"
---
# <a name="imetadataimportgettyperefprops-method"></a><span data-ttu-id="6fcb1-102">Metodo IMetaDataImport::GetTypeRefProps</span><span class="sxs-lookup"><span data-stu-id="6fcb1-102">IMetaDataImport::GetTypeRefProps Method</span></span>
<span data-ttu-id="6fcb1-103">Ottiene i metadati associati all'oggetto <xref:System.Type> a cui fa riferimento il token TypeRef specificato.</span><span class="sxs-lookup"><span data-stu-id="6fcb1-103">Gets the metadata associated with the <xref:System.Type> referenced by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fcb1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6fcb1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeRefProps (  
   [in]  mdTypeRef   tr,  
   [out] mdToken     *ptkResolutionScope,  
   [out] LPWSTR      szName,  
   [in]  ULONG       cchName,  
   [out] ULONG       *pchName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fcb1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6fcb1-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="6fcb1-106">in Token TypeRef che rappresenta il tipo per cui restituire i metadati.</span><span class="sxs-lookup"><span data-stu-id="6fcb1-106">[in] The TypeRef token that represents the type to return metadata for.</span></span>  
  
 `ptkResolutionScope`  
 <span data-ttu-id="6fcb1-107">out Puntatore all'ambito in cui viene eseguito il riferimento.</span><span class="sxs-lookup"><span data-stu-id="6fcb1-107">[out] A pointer to the scope in which the reference is made.</span></span> <span data-ttu-id="6fcb1-108">Questo valore è un token AssemblyRef o ModuleRef.</span><span class="sxs-lookup"><span data-stu-id="6fcb1-108">This value is an AssemblyRef or ModuleRef token.</span></span>  
  
 `szName`  
 <span data-ttu-id="6fcb1-109">out Buffer contenente il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="6fcb1-109">[out] A buffer containing the type name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="6fcb1-110">in Dimensioni richieste in caratteri wide di `szName` .</span><span class="sxs-lookup"><span data-stu-id="6fcb1-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="6fcb1-111">out Dimensione restituita in caratteri wide di `szName` .</span><span class="sxs-lookup"><span data-stu-id="6fcb1-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fcb1-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6fcb1-112">Requirements</span></span>  
 <span data-ttu-id="6fcb1-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fcb1-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fcb1-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6fcb1-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6fcb1-115">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6fcb1-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6fcb1-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fcb1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fcb1-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6fcb1-117">See also</span></span>

- [<span data-ttu-id="6fcb1-118">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="6fcb1-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="6fcb1-119">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="6fcb1-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
