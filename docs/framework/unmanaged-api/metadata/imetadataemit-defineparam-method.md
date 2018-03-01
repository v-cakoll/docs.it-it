---
title: Metodo IMetaDataEmit::DefineParam
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
- IMetaDataEmit.DefineParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineParam
helpviewer_keywords:
- IMetaDataEmit::DefineParam method [.NET Framework metadata]
- DefineParam method [.NET Framework metadata]
ms.assetid: d86a3d14-4796-4909-9591-dfafe3de5ce4
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f4bf36edfad504f2858a45d5e34891042d8850bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefineparam-method"></a>Metodo IMetaDataEmit::DefineParam
Crea una definizione di parametro con la firma specificata per il metodo a cui fa riferimento il token specificato e ottiene un token per la definizione di parametro.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DefineParam (  
    [in]  mdMethodDef md,   
    [in]  ULONG       ulParamSeq,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwParamFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,  
    [in]  ULONG       cchValue,   
    [out] mdParamDef  *ppd   
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `md`  
 [in] Il token per il metodo viene definito il cui parametro.  
  
 `ulParamSeq`  
 [in] Il numero di sequenza del parametro.  
  
 `szName`  
 [in] Il nome del parametro in formato Unicode.  
  
 `dwParamFlags`  
 [in] Flag per il parametro. Si tratta di una maschera di bit di `CorParamAttr` valori.  
  
 `dwCPlusTypeFlag`  
 [in] `ELEMENT_TYPE_`  *\**  per il valore costante.  
  
 `pValue`  
 [in] Il valore costante per il parametro.  
  
 `cchValue`  
 [in] Le dimensioni, in caratteri Unicode, di `pValue`.  
  
 `ppd`  
 [out] Il `mdParamDef` token assegnato.  
  
## <a name="remarks"></a>Note  
 La sequenza di valori `ulParamSeq` iniziano con 1 per i parametri. Valore restituito è un numero di sequenza pari a 0.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
