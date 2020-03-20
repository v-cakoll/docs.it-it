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
ms.openlocfilehash: 5fc71bf240b89afadbf8f2ba10906322921bdda2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175330"
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
 [in] Token che rappresenta la proprietà per cui restituire i metadati.  
  
 `pClass`  
 [fuori] Puntatore al token TypeDef che rappresenta il tipo che implementa la proprietà.  
  
 `szProperty`  
 [fuori] Un buffer per contenere il nome della proprietà.  
  
 `cchProperty`  
 [in] La dimensione in `szProperty`caratteri larghi di .  
  
 `pchProperty`  
 [fuori] Numero di caratteri di `szProperty`tipo "wide" restituiti in .  
  
 `pdwPropFlags`  
 [fuori] Puntatore a tutti i flag di attributo applicati alla proprietà. Questo valore è una maschera di bit dall'enumerazione [CorPropertyAttr.](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md)  
  
 `ppvSig`  
 [fuori] Puntatore alla firma dei metadati della proprietà.  
  
 `pbSig`  
 [fuori] Numero di byte restituiti in . `ppvSig`  
  
 `pdwCPlusTypeFlag`  
 [fuori] Flag che specifica il tipo della costante che è il valore predefinito della proprietà. Questo valore deriva dall'enumerazione CorElementType.  
  
 `ppDefaultValue`  
 [fuori] Puntatore ai byte che archiviano il valore predefinito per questa proprietà.  
  
 `pcchDefaultValue`  
 [fuori] La dimensione in `ppDefaultValue`caratteri `pdwCPlusTypeFlag` di tipo "wide" di , se è ELEMENT_TYPE_STRING; in caso contrario, questo valore non è rilevante. In tal caso, `ppDefaultValue` la lunghezza di viene dedotta `pdwCPlusTypeFlag`dal tipo specificato da .  
  
 `pmdSetter`  
 [fuori] Puntatore al token MethodDef che rappresenta il metodo della funzione di accesso set per la proprietà.  
  
 `pmdGetter`  
 [fuori] Puntatore al token MethodDef che rappresenta il metodo della funzione di accesso get per la proprietà.  
  
 `rmdOtherMethod`  
 [fuori] Matrice di token MethodDef che rappresentano altri metodi associati alla proprietà.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rmdOtherMethod`. Se non si fornisce una matrice sufficientemente grande da contenere tutti i metodi, questi vengono ignorati senza alcun avviso.  
  
 `pcOtherMethod`  
 [fuori] Numero di token MethodDef restituiti in `rmdOtherMethod`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Incluso come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
