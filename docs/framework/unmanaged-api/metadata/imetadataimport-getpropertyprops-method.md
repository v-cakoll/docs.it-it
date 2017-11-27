---
title: Metodo IMetaDataImport::GetPropertyProps
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetPropertyProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetPropertyProps
helpviewer_keywords:
- GetPropertyProps method [.NET Framework metadata]
- IMetaDataImport::GetPropertyProps method [.NET Framework metadata]
ms.assetid: dc0ff3e6-7e7d-4f6c-948d-52b28f5cb78c
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: fc3a1ce1d07bda50b2b578e7d20870324d60edc0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetpropertyprops-method"></a>Metodo IMetaDataImport::GetPropertyProps
Ottiene i metadati per la proprietà rappresentata dal token specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetPropertyProps (  
   [in]  mdProperty        prop,  
   [out] mdTypeDef         *pClass,   
   [out] LPCWSTR           szProperty,   
   [in]  ULONG             cchProperty,   
   [out] ULONG             *pchProperty,   
   [out] DWORD             *pdwPropFlags,   
   [out] PCCOR_SIGNATURE   *ppvSig,   
   [out] ULONG             *pbSig,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppDefaultValue,  
   [out] ULONG             *pcchDefaultValue,  
   [out] mdMethodDef       *pmdSetter,   
   [out] mdMethodDef       *pmdGetter,   
   [out] mdMethodDef       rmdOtherMethod[],  
   [in]  ULONG             cMax,   
   [out] ULONG             *pcOtherMethod   
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `prop`  
 [in] Un token che rappresenta la proprietà per restituire i metadati.  
  
 `pClass`  
 [out] Puntatore al token TypeDef che rappresenta il tipo che implementa la proprietà.  
  
 `szProperty`  
 [out] Un buffer contenente il nome della proprietà.  
  
 `cchProperty`  
 [in] La dimensione in caratteri "wide" di `szProperty`.  
  
 `pchProperty`  
 [out] Il numero di caratteri "wide" restituiti in `szProperty`.  
  
 `pdwPropFlags`  
 [out] Puntatore ai flag di attributo applicato alla proprietà. Questo valore è una maschera di bit di [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumerazione.  
  
 `ppvSig`  
 [out] Un puntatore per la firma dei metadati della proprietà.  
  
 `pbSig`  
 [out] Il numero di byte restituiti nella `ppvSig`.  
  
 `pdwCPlusTypeFlag`  
 [out] Flag che specificano il tipo della costante che rappresenta il valore predefinito della proprietà. Questo valore è un'enumerazione CorElementType.  
  
 `ppDefaultValue`  
 [out] Puntatore ai byte archiviare il valore predefinito per questa proprietà.  
  
 `pcchDefaultValue`  
 [out] La dimensione in caratteri "wide" di `ppDefaultValue`, se `pdwCPlusTypeFlag` è ELEMENT_TYPE_STRING; in caso contrario, questo valore non è rilevante. In questo caso, la lunghezza di `ppDefaultValue` viene dedotto dal tipo specificato da `pdwCPlusTypeFlag`.  
  
 `pmdSetter`  
 [out] Puntatore al token MethodDef che rappresenta il metodo della funzione di accesso set per la proprietà.  
  
 `pmdGetter`  
 [out] Puntatore al token MethodDef che rappresenta il metodo di funzione di accesso get della proprietà.  
  
 `rmdOtherMethod`  
 [out] Matrice di token MethodDef che rappresentano gli altri metodi associati alla proprietà.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rmdOtherMethod`. Se non si specifica una matrice sufficientemente grande da contenere tutti i metodi, questi verranno ignorati senza avviso.  
  
 `pcOtherMethod`  
 [out] Il numero di token MethodDef restituiti in `rmdOtherMethod`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IMetaDataImport (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
