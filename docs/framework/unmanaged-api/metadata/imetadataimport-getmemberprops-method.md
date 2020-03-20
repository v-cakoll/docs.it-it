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
ms.openlocfilehash: 72e14ea0414ebdeb8f54a4bdef8ce5208fc8ef72
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177222"
---
# <a name="imetadataimportgetmemberprops-method"></a>Metodo IMetaDataImport::GetMemberProps
Ottiene le informazioni archiviate nei metadati per una definizione di membro specificata, inclusi il nome, la firma binaria e l'indirizzo <xref:System.Type> virtuale relativo, del membro a cui fa riferimento il token di metadati specificato. Questo è un metodo helper semplice: se *mb* è un MethodDef, quindi **GetMethodProps** viene chiamato; se *mb* è un FieldDef, quindi **GetFieldProps** viene chiamato. Vedere questi altri metodi per i dettagli.
  
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
 [in] Token che fa riferimento al membro per cui ottenere i metadati associati.  
  
 `pClass`  
 [fuori] Puntatore al token di metadati che rappresenta la classe del membro.  
  
 `szMember`  
 [fuori] Nome del membro.  
  
 `cchMember`  
 [in] Dimensione in caratteri di `szMember` tipo "wide" del buffer.  
  
 `pchMember`  
 [fuori] Dimensione in caratteri di tipo "wide" del nome restituito.  
  
 `pdwAttr`  
 [fuori] Eventuali valori di flag applicati al membro.  
  
 `ppvSigBlob`  
 [fuori] Puntatore alla firma dei metadati binari del membro.  
  
 `pcbSigBlob`  
 [fuori] Dimensione in byte `ppvSigBlob`di .  
  
 `pulCodeRVA`  
 [fuori] Puntatore all'indirizzo virtuale relativo del membro.  
  
 `pdwImplFlags`  
 [fuori] Qualsiasi flag di implementazione del metodo associato al membro.  
  
 `pdwCPlusTypeFlag`  
 [fuori] Una bandiera che <xref:System.ValueType>contrassegna un oggetto . È uno dei `ELEMENT_TYPE_*` valori.
  
 `ppValue`  
 [fuori] Valore stringa costante restituito da questo membro.  
  
 `pcchValue`  
 [fuori] La dimensione in `ppValue`caratteri di `ppValue` , o zero se non contiene una stringa.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Incluso come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
