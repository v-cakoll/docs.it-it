---
title: Metodo IMetaDataEmit::DefineField
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineField
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2a544d7e676b71fb00b8fd7a3d871867f7f55626
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinefield-method"></a>Metodo IMetaDataEmit::DefineField
Crea una definizione per un campo con la firma dei metadati specificati e ottiene un token per tale definizione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DefineField (   
    [in]  mdTypeDef   td,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwFieldFlags,   
    [in]  PCCOR_SIGNATURE pvSigBlob,   
    [in]  ULONG       cbSigBlob,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue,   
    [out] mdFieldDef  *pmd   
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `td`  
 [in] Il `mdTypeDef` token per la classe o interfaccia contenitore.  
  
 `szName`  
 [in] Il nome del campo in formato Unicode.  
  
 `dwFieldFlags`  
 [in] Gli attributi di campo. Si tratta di una maschera di bit di `CorFieldAttr` valori.  
  
 `pvSigBlob`  
 [in] La firma del campo come BLOB.  
  
 `cbSigBlob`  
 [in] Il numero di byte in `pvSigBlob`.  
  
 `dwCPlusTypeFlage`  
 [in] Il `ELEMENT_TYPE_`  *\**  per il valore costante. Si tratta di un `CorElementType` valore. Se non si definisce un valore costante per il campo, utilizzare `ELEMENT_TYPE_END`.  
  
 `pValue`  
 [in] Il valore costante per il campo.  
  
 `cchValue`  
 [in] La dimensione in caratteri (Unicode) di `pValue`.  
  
 `pmd`  
 [out] Il `mdFieldDef` token assegnato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IMetaDataEmit (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
