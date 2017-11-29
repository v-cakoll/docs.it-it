---
title: Metodo IMetaDataImport::GetMemberRefProps
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetMemberRefProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetMemberRefProps
helpviewer_keywords:
- GetMemberRefProps method [.NET Framework metadata]
- IMetaDataImport::GetMemberRefProps method [.NET Framework metadata]
ms.assetid: 0ea73055-ece0-4151-a094-414c88ef8941
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0b4b0399c22890226ad49ca0f3a5c709fb251653
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetmemberrefprops-method"></a>Metodo IMetaDataImport::GetMemberRefProps
Ottiene i metadati associati al membro a cui fa riferimento il token specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetMemberRefProps (  
   [in]  mdMemberRef       mr,   
   [out] mdToken           *ptk,   
   [out] LPWSTR            szMember,   
   [in]  ULONG             cchMember,   
   [out] ULONG             *pchMember,   
   [out] PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pbSig   
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `mr`  
 [in] Il token di MemberRef per restituire i metadati associati.  
  
 `ptk`  
 [out] Token TypeDef o TypeRef o TypeSpec che rappresenta la classe che dichiara il membro o un token ModuleRef che rappresenta la classe del modulo che dichiara il membro o un MethodDef che rappresenta il membro.  
  
 `szMember`  
 [out] Un buffer di stringa per il nome del membro.  
  
 `cchMember`  
 [in] La dimensione in caratteri wide della richiesta `szMember`.  
  
 `pchMember`  
 [out] Dimensione restituita in caratteri "wide" di `szMember`.  
  
 `ppvSibBlob`  
 [out] Puntatore a firma binaria dei metadati per il membro.  
  
 `pbSig`  
 [out] Le dimensioni in byte di `ppvSigBlob`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IMetaDataImport (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
