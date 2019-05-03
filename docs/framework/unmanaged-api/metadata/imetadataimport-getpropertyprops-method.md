---
title: Metodo IMetaDataImport::GetPropertyProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPropertyProps
helpviewer_keywords:
- GetPropertyProps method [.NET Framework metadata]
- IMetaDataImport::GetPropertyProps method [.NET Framework metadata]
ms.assetid: dc0ff3e6-7e7d-4f6c-948d-52b28f5cb78c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a08bd5beeb9fab1cd5b703c3afc4e82aaf71dbbc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777557"
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
  
## <a name="parameters"></a>Parametri  
 `prop`  
 [in] Token che rappresenta la proprietà per restituire i metadati.  
  
 `pClass`  
 [out] Puntatore al token TypeDef che rappresenta il tipo che implementa la proprietà.  
  
 `szProperty`  
 [out] Un buffer contenente il nome della proprietà.  
  
 `cchProperty`  
 [in] La dimensione in caratteri "wide" di `szProperty`.  
  
 `pchProperty`  
 [out] Il numero di caratteri "wide", restituito nel `szProperty`.  
  
 `pdwPropFlags`  
 [out] Puntatore al flag di attributi applicati alla proprietà. Questo valore è una maschera di bit di [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumerazione.  
  
 `ppvSig`  
 [out] Un puntatore per la firma dei metadati della proprietà.  
  
 `pbSig`  
 [out] Il numero di byte restituiti nella `ppvSig`.  
  
 `pdwCPlusTypeFlag`  
 [out] Flag che specifica il tipo della costante che rappresenta il valore predefinito della proprietà. Questo valore viene ricavato dall'enumerazione CorElementType.  
  
 `ppDefaultValue`  
 [out] Puntatore ai byte che archiviano il valore predefinito per questa proprietà.  
  
 `pcchDefaultValue`  
 [out] La dimensione in caratteri wide di `ppDefaultValue`, se `pdwCPlusTypeFlag` è ELEMENT_TYPE_STRING; in caso contrario, questo valore non è rilevante. In tal caso, la lunghezza di `ppDefaultValue` viene dedotto dal tipo specificato dal `pdwCPlusTypeFlag`.  
  
 `pmdSetter`  
 [out] Puntatore al token MethodDef che rappresenta il metodo della funzione di accesso set della proprietà.  
  
 `pmdGetter`  
 [out] Puntatore al token MethodDef che rappresenta il metodo della funzione di accesso get della proprietà.  
  
 `rmdOtherMethod`  
 [out] Matrice dei token MethodDef che rappresentano gli altri metodi associati alla proprietà.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rmdOtherMethod`. Se non si specifica una matrice sufficientemente grande da contenere tutti i metodi, vengono ignorati senza avviso.  
  
 `pcOtherMethod`  
 [out] Il numero di token MethodDef restituiti in `rmdOtherMethod`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
