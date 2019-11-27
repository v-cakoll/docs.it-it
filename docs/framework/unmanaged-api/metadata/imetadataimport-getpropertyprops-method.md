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
ms.openlocfilehash: 247a2793bf3806f5ee38585d50b4535820dfcb69
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437066"
---
# <a name="imetadataimportgetpropertyprops-method"></a>Metodo IMetaDataImport::GetPropertyProps
Ottiene i metadati per la proprietà rappresentata dal token specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
 in Token che rappresenta la proprietà per la quale restituire i metadati.  
  
 `pClass`  
 out Puntatore al token TypeDef che rappresenta il tipo che implementa la proprietà.  
  
 `szProperty`  
 out Buffer in cui memorizzare il nome della proprietà.  
  
 `cchProperty`  
 in Dimensioni in caratteri wide di `szProperty`.  
  
 `pchProperty`  
 out Numero di caratteri wide restituiti in `szProperty`.  
  
 `pdwPropFlags`  
 out Puntatore a qualsiasi flag di attributo applicato alla proprietà. Questo valore è una maschera di maschera dall'enumerazione [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) .  
  
 `ppvSig`  
 out Puntatore alla firma dei metadati della proprietà.  
  
 `pbSig`  
 out Numero di byte restituiti in `ppvSig`.  
  
 `pdwCPlusTypeFlag`  
 out Flag che specifica il tipo della costante che corrisponde al valore predefinito della proprietà. Questo valore è dall'enumerazione CorElementType.  
  
 `ppDefaultValue`  
 out Puntatore ai byte in cui è archiviato il valore predefinito per questa proprietà.  
  
 `pcchDefaultValue`  
 out Dimensioni in caratteri wide di `ppDefaultValue`, se `pdwCPlusTypeFlag` è ELEMENT_TYPE_STRING; in caso contrario, questo valore non è pertinente. In tal caso, la lunghezza di `ppDefaultValue` viene dedotta dal tipo specificato da `pdwCPlusTypeFlag`.  
  
 `pmdSetter`  
 out Puntatore al token MethodDef che rappresenta il metodo della funzione di accesso set per la proprietà.  
  
 `pmdGetter`  
 out Puntatore al token MethodDef che rappresenta il metodo della funzione di accesso get per la proprietà.  
  
 `rmdOtherMethod`  
 out Matrice di token MethodDef che rappresentano altri metodi associati alla proprietà.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rmdOtherMethod`. Se non si specifica una matrice sufficientemente grande da conservare tutti i metodi, verranno ignorati senza preavviso.  
  
 `pcOtherMethod`  
 out Numero di token MethodDef restituiti in `rmdOtherMethod`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
