---
title: Metodo IMetaDataImport::GetFieldProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldProps
helpviewer_keywords:
- IMetaDataImport::GetFieldProps method [.NET Framework metadata]
- GetFieldProps method [.NET Framework metadata]
ms.assetid: 7b0e9b10-8cef-4ba6-8432-40bf63e65ab1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d7f8cccf8d583645982eb37f6afcb553914679ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777754"
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
  
## <a name="parameters"></a>Parametri  
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
 [out] La dimensione in byte di `ppvSigBlob`.  
  
 `pdwCPlusTypeFlag`  
 [out] Un flag che specifica il tipo di valore del campo.  
  
 `ppValue`  
 [out] Un valore costante per il campo.  
  
 `pcchValue`  
 [out] La dimensione in caratteri di `ppValue`, oppure zero se è presente alcuna stringa.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
