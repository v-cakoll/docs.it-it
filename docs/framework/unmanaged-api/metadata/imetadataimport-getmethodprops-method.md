---
title: Metodo IMetaDataImport::GetMethodProps
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e4e0ae7dfed4b13ea83e16d6380443c9d1b72b06
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetmethodprops-method"></a>Metodo IMetaDataImport::GetMethodProps
Ottiene i metadati associati al metodo a cui fa riferimento il token MethodDef specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
#### <a name="parameters"></a>Parametri  
 `mb`  
 [in] Il token MethodDef che rappresenta il metodo per restituire i metadati.  
  
 `pClass`  
 [out] Un puntatore a un token TypeDef che rappresenta il tipo che implementa il metodo.  
  
 `szMethod`  
 [out] Puntatore a un buffer con il nome del metodo.  
  
 `cchMethod`  
 [in] La dimensione richiesta del `szMethod`.  
  
 `pchMethod`  
 [out] Un puntatore alla dimensione in caratteri "wide" di `szMethod`, o in caso di troncamento, il numero effettivo di caratteri "wide" nel nome del metodo.  
  
 `pdwAttr`  
 [out] Puntatore a tutti i flag associati al metodo.  
  
 `ppvSigBlob`  
 [out] Un puntatore per la firma binaria dei metadati del metodo.  
  
 `pcbSigBlob`  
 [out] Un puntatore alla dimensione in byte di `ppvSigBlob`.  
  
 `pulCodeRVA`  
 [out] Un puntatore all'indirizzo virtuale relativo del metodo.  
  
 `pdwImplFlags`  
 [out] Puntatore ai flag di implementazione per il metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
