---
title: Metodo IMetaDataImport::GetMemberProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberProps
helpviewer_keywords:
- IMetaDataImport::GetMemberProps method [.NET Framework metadata]
- GetMemberProps method [.NET Framework metadata]
ms.assetid: 42790918-4142-4938-b8f4-a56979a55846
topic_type:
- apiref
ms.openlocfilehash: bc5bbba2fa4a95955e52a2e083a2097178b5d96a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437510"
---
# <a name="imetadataimportgetmemberprops-method"></a>Metodo IMetaDataImport::GetMemberProps
Ottiene le informazioni archiviate nei metadati per una definizione di membro specificata, inclusi il nome, la firma binaria e l'indirizzo virtuale relativo, del membro <xref:System.Type> a cui fa riferimento il token di metadati specificato. Si tratta di un semplice metodo helper: se *MB* è un MethodDef, viene chiamato **GetMethodProps** . Se *MB* è un FieldDef, viene chiamato **GetFieldProps** . Per informazioni dettagliate, vedere gli altri metodi. 
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetMemberProps (  
   [in]  mdToken           mb,   
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szMember,   
   [in]  ULONG             cchMember,   
   [out] ULONG             *pchMember,   
   [out] DWORD             *pdwAttr,  
   [out] PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pcbSigBlob,   
   [out] ULONG             *pulCodeRVA,   
   [out] DWORD             *pdwImplFlags,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `mb`  
 in Token che fa riferimento al membro per il quale ottenere i metadati associati.  
  
 `pClass`  
 out Puntatore al token di metadati che rappresenta la classe del membro.  
  
 `szMember`  
 out Nome del membro.  
  
 `cchMember`  
 in Dimensioni in caratteri wide del buffer `szMember`.  
  
 `pchMember`  
 out Dimensioni in caratteri wide del nome restituito.  
  
 `pdwAttr`  
 out Qualsiasi valore del flag applicato al membro.  
  
 `ppvSigBlob`  
 out Puntatore alla firma dei metadati binari del membro.  
  
 `pcbSigBlob`  
 out Dimensioni in byte del `ppvSigBlob`.  
  
 `pulCodeRVA`  
 out Puntatore all'indirizzo virtuale relativo del membro.  
  
 `pdwImplFlags`  
 out Qualsiasi flag di implementazione del metodo associato al membro.  
  
 `pdwCPlusTypeFlag`  
 out Flag che contrassegna un <xref:System.ValueType>. È uno dei valori di `ELEMENT_TYPE_*`.
  
 `ppValue`  
 out Valore stringa costante restituito da questo membro.  
  
 `pcchValue`  
 out Dimensioni in caratteri di `ppValue`o zero se `ppValue` non dispone di una stringa.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
