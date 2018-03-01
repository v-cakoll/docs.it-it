---
title: Metodo IMetaDataImport::GetMemberProps
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 543929390977fc593e86947feece06f43bc0cad6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetmemberprops-method"></a>Metodo IMetaDataImport::GetMemberProps
Ottiene informazioni sui metadati, inclusi il nome, la firma binaria e l'indirizzo virtuale relativo, del <xref:System.Type> membro a cui fa riferimento il token di metadati specificato.  
  
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
 [in] Token che fa riferimento al membro per ottenere i metadati associati.  
  
 `pClass`  
 [out] Puntatore al token di metadati che rappresenta la classe del membro.  
  
 `szMember`  
 [out] Il nome del membro.  
  
 `cchMember`  
 [in] La dimensione in caratteri "wide" del `szMember` buffer.  
  
 `pchMember`  
 [out] Dimensione in caratteri "wide" del nome restituito.  
  
 `pdwAttr`  
 [out] Eventuali valori di flag applicati al membro.  
  
 `ppvSigBlob`  
 [out] Un puntatore per la firma binaria dei metadati del membro.  
  
 `pcbSigBlob`  
 [out] Le dimensioni in byte di `ppvSigBlob`.  
  
 `pulCodeRVA`  
 [out] Un puntatore all'indirizzo virtuale relativo del membro.  
  
 `pdwImplFlags`  
 [out] Flag di implementazione del metodo associato al membro.  
  
 `pdwCPlusTypeFlag`  
 [out] Flag che contrassegna un <xref:System.ValueType>.  
  
 `ppValue`  
 [out] Valore stringa costante restituito da questo membro.  
  
 `pcchValue`  
 [out] La dimensione in caratteri di `ppValue`, oppure zero se `ppValue` non contiene una stringa.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
