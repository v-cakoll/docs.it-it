---
title: Metodo IMetaDataImport::GetCustomAttributeProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetCustomAttributeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeProps
helpviewer_keywords:
- GetCustomAttributeProps method [.NET Framework metadata]
- IMetaDataImport::GetCustomAttributeProps method [.NET Framework metadata]
ms.assetid: 6eefb243-a281-41c1-bcdc-7e17513bc446
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c27a55166ebc055f324ec45ba6dfd835c8b8bbf6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075743"
---
# <a name="imetadataimportgetcustomattributeprops-method"></a><span data-ttu-id="4e4e3-102">Metodo IMetaDataImport::GetCustomAttributeProps</span><span class="sxs-lookup"><span data-stu-id="4e4e3-102">IMetaDataImport::GetCustomAttributeProps Method</span></span>
<span data-ttu-id="4e4e3-103">Ottiene il valore dell'attributo personalizzato, dato il relativo token di metadati.</span><span class="sxs-lookup"><span data-stu-id="4e4e3-103">Gets the value of the custom attribute, given its metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e4e3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4e4e3-104">Syntax</span></span>  
  
```  
HRESULT GetCustomAttributeProps (  
   [in]            mdCustomAttribute   cv,  
   [out, optional] mdToken             *ptkObj,  
   [out, optional] mdToken             *ptkType,  
   [out, optional] void const          **ppBlob,  
   [out, optional] ULONG               *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e4e3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4e4e3-105">Parameters</span></span>  
 `cv`  
 <span data-ttu-id="4e4e3-106">[in] Token di metadati che rappresenta l'attributo personalizzato da recuperare.</span><span class="sxs-lookup"><span data-stu-id="4e4e3-106">[in] A metadata token that represents the custom attribute to be retrieved.</span></span>  
  
 `ptkObj`  
 <span data-ttu-id="4e4e3-107">[out, facoltativo] Token di metadati che rappresenta l'oggetto che viene modificato dall'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4e4e3-107">[out, optional] A metadata token representing the object that the custom attribute modifies.</span></span> <span data-ttu-id="4e4e3-108">Questo valore può essere un tipo qualsiasi di token di metadati, eccetto `mdCustomAttribute`.</span><span class="sxs-lookup"><span data-stu-id="4e4e3-108">This value can be any type of metadata token except `mdCustomAttribute`.</span></span>  
  
 `ptkType`  
 <span data-ttu-id="4e4e3-109">[out, facoltativo] Token di metadati `mdMethodDef` o `mdMemberRef` che rappresenta la classe <xref:System.Type> dell'attributo personalizzato restituito.</span><span class="sxs-lookup"><span data-stu-id="4e4e3-109">[out, optional] An `mdMethodDef` or `mdMemberRef` metadata token representing the <xref:System.Type> of the returned custom attribute.</span></span>  
  
 `ppBlob`  
 <span data-ttu-id="4e4e3-110">[out, facoltativo] Puntatore a una matrice di dati che è il valore dell'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4e4e3-110">[out, optional] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="4e4e3-111">[out, facoltativo] Dimensione in byte dei dati restituiti in \*`ppBlob`.</span><span class="sxs-lookup"><span data-stu-id="4e4e3-111">[out, optional] The size in bytes of the data returned in \*`ppBlob`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e4e3-112">Note</span><span class="sxs-lookup"><span data-stu-id="4e4e3-112">Remarks</span></span>  
 <span data-ttu-id="4e4e3-113">Un attributo personalizzato viene archiviato come matrice di dati, il formato riconosciuto dal modulo di gestione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="4e4e3-113">A custom attribute is stored as an array of data, the format which is understood by the metadata engine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e4e3-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4e4e3-114">Requirements</span></span>  
 <span data-ttu-id="4e4e3-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e4e3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e4e3-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4e4e3-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4e4e3-117">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="4e4e3-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4e4e3-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e4e3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e4e3-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e4e3-119">See also</span></span>

- [<span data-ttu-id="4e4e3-120">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="4e4e3-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="4e4e3-121">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="4e4e3-121">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
