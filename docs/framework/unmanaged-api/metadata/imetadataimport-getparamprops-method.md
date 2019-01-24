---
title: Metodo IMetaDataImport::GetParamProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamProps
helpviewer_keywords:
- IMetaDataImport::GetParamProps method [.NET Framework metadata]
- GetParamProps method [.NET Framework metadata]
ms.assetid: 4d5e5f00-bcab-4f41-b191-176511a186a7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c4e4b163cc783ccd01bc406789f5bf92448c697c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685529"
---
# <a name="imetadataimportgetparamprops-method"></a><span data-ttu-id="b7fba-102">Metodo IMetaDataImport::GetParamProps</span><span class="sxs-lookup"><span data-stu-id="b7fba-102">IMetaDataImport::GetParamProps Method</span></span>
<span data-ttu-id="b7fba-103">Ottiene i valori di metadati relativi al parametro a cui fa riferimento il token ParamDef specificato.</span><span class="sxs-lookup"><span data-stu-id="b7fba-103">Gets metadata values for the parameter referenced by the specified ParamDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7fba-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b7fba-104">Syntax</span></span>  
  
```  
HRESULT GetParamProps (  
   [in]  mdParamDef      tk,  
   [out] mdMethodDef     *pmd,  
   [out] ULONG           *pulSequence,  
   [out] LPWSTR          szName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName,  
   [out] DWORD           *pdwAttr,  
   [out] DWORD           *pdwCPlusTypeFlag,  
   [out] UVCP_CONSTANT   *ppValue,  
   [out] ULONG           *pcchValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b7fba-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b7fba-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="b7fba-106">[in] Token ParamDef che rappresenta il parametro per restituire i metadati.</span><span class="sxs-lookup"><span data-stu-id="b7fba-106">[in] A ParamDef token that represents the parameter to return metadata for.</span></span>  
  
 `pmd`  
 <span data-ttu-id="b7fba-107">[out] Un puntatore a un token MethodDef che rappresentano il metodo che accetta il parametro.</span><span class="sxs-lookup"><span data-stu-id="b7fba-107">[out] A pointer to a MethodDef token representing the method that takes the parameter.</span></span>  
  
 `pulSequence`  
 <span data-ttu-id="b7fba-108">[out] La posizione ordinale del parametro nell'elenco di argomenti di metodo.</span><span class="sxs-lookup"><span data-stu-id="b7fba-108">[out] The ordinal position of the parameter in the method argument list.</span></span>  
  
 `szName`  
 <span data-ttu-id="b7fba-109">[out] Un buffer contenente il nome del parametro.</span><span class="sxs-lookup"><span data-stu-id="b7fba-109">[out] A buffer to hold the name of the parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="b7fba-110">[in] Le dimensioni richieste in caratteri wide di `szName`.</span><span class="sxs-lookup"><span data-stu-id="b7fba-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="b7fba-111">[out] Le dimensioni restituite in caratteri wide di `szName`.</span><span class="sxs-lookup"><span data-stu-id="b7fba-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="b7fba-112">[out] Puntatore ai flag di attributo associato al parametro.</span><span class="sxs-lookup"><span data-stu-id="b7fba-112">[out] A pointer to any attribute flags associated with the parameter.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="b7fba-113">[out] Un puntatore a un flag che specifica che il parametro è un <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="b7fba-113">[out] A pointer to a flag specifying that the parameter is a <xref:System.ValueType>.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="b7fba-114">[out] Puntatore a una costante stringa restituita dal parametro.</span><span class="sxs-lookup"><span data-stu-id="b7fba-114">[out] A pointer to a constant string returned by the parameter.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="b7fba-115">[out] Il valore pari `ppValue` in caratteri "wide", oppure zero se `ppValue` non contiene una stringa.</span><span class="sxs-lookup"><span data-stu-id="b7fba-115">[out] The size of `ppValue` in wide characters, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7fba-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b7fba-116">Requirements</span></span>  
 <span data-ttu-id="b7fba-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7fba-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7fba-118">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b7fba-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b7fba-119">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="b7fba-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b7fba-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7fba-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7fba-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7fba-121">See also</span></span>
- [<span data-ttu-id="b7fba-122">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="b7fba-122">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b7fba-123">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="b7fba-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
