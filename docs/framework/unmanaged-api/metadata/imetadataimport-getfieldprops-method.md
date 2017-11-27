---
title: Metodo IMetaDataImport::GetFieldProps
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetFieldProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetFieldProps
helpviewer_keywords:
- IMetaDataImport::GetFieldProps method [.NET Framework metadata]
- GetFieldProps method [.NET Framework metadata]
ms.assetid: 7b0e9b10-8cef-4ba6-8432-40bf63e65ab1
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d5874169e0f8c452b177309702444ea84858557e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetfieldprops-method"></a>Metodo IMetaDataImport::GetFieldProps
Ottiene i metadati associati al campo a cui fa riferimento il token FieldDef specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetFieldProps (  
   [in]  mdFieldDef        mb,   
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szField,  
   [in]  ULONG             cchField,   
   [out] ULONG             *pchField,  
   [out] DWORD             *pdwAttr,  
   [in]  PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pcbSigBlob,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `mb`  
 [in] Token FieldDef che rappresenta il campo per ottenere i metadati associati.  
  
 `pClass`  
 [out] Un puntatore a un token TypeDef che rappresenta il tipo della classe a cui appartiene il campo.  
  
 `szField`  
 [out] Il nome del campo.  
  
 `cchField`  
 [in] La dimensione in caratteri wide del buffer per *szField*.  
  
 `pchField`  
 [out] Le dimensioni effettive del buffer restituito.  
  
 `pdwAttr`  
 [out] Flag associato ai metadati del campo.  
  
 `ppvSigBlob`  
 [in] Puntatore al valore binario dei metadati che descrive il campo.  
  
 `pcbSigBlob`  
 [out] Le dimensioni in byte di `ppvSigBlob`.  
  
 `pdwCPlusTypeFlag`  
 [out] Flag che specifica il tipo di valore del campo.  
  
 `ppValue`  
 [out] Un valore costante per il campo.  
  
 `pcchValue`  
 [out] Dimensione in caratteri di `ppValue`, oppure zero se non esiste alcuna stringa.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IMetaDataImport (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
