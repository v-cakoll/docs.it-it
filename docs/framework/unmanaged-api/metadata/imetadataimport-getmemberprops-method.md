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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 98d7be5adc81cff09b121265e7d5b5f712122607
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611410"
---
# <a name="imetadataimportgetmemberprops-method"></a>Metodo IMetaDataImport::GetMemberProps
Ottiene le informazioni sui metadati, inclusi il nome, la firma binaria e indirizzo virtuale relativo, del <xref:System.Type> membro a cui fa riferimento il token di metadati specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
#### <a name="parameters"></a>Parametri  
 `mb`  
 [in] Il token che fa riferimento al membro per ottenere i metadati associati.  
  
 `pClass`  
 [out] Puntatore al token di metadati che rappresenta la classe del membro.  
  
 `szMember`  
 [out] Il nome del membro.  
  
 `cchMember`  
 [in] La dimensione in caratteri "wide" del `szMember` buffer.  
  
 `pchMember`  
 [out] Dimensione in caratteri "wide" del nome restituito.  
  
 `pdwAttr`  
 [out] I valori di flag applicati al membro.  
  
 `ppvSigBlob`  
 [out] Un puntatore per la firma binaria dei metadati del membro.  
  
 `pcbSigBlob`  
 [out] La dimensione in byte di `ppvSigBlob`.  
  
 `pulCodeRVA`  
 [out] Un puntatore all'indirizzo virtuale relativo del membro.  
  
 `pdwImplFlags`  
 [out] Flag di implementazione del metodo associato al membro.  
  
 `pdwCPlusTypeFlag`  
 [out] Un flag che contrassegna un <xref:System.ValueType>.  
  
 `ppValue`  
 [out] Un valore stringa costante restituito da questo membro.  
  
 `pcchValue`  
 [out] La dimensione in caratteri della `ppValue`, oppure zero se `ppValue` non contiene una stringa.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
