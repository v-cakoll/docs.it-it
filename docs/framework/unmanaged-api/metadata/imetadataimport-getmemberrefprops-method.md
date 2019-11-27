---
title: Metodo IMetaDataImport::GetMemberRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberRefProps
helpviewer_keywords:
- GetMemberRefProps method [.NET Framework metadata]
- IMetaDataImport::GetMemberRefProps method [.NET Framework metadata]
ms.assetid: 0ea73055-ece0-4151-a094-414c88ef8941
topic_type:
- apiref
ms.openlocfilehash: 1d6d66ea62cbf679f722f830b3638455001aedd6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437484"
---
# <a name="imetadataimportgetmemberrefprops-method"></a>Metodo IMetaDataImport::GetMemberRefProps
Ottiene i metadati associati al membro a cui fa riferimento il token specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
## <a name="parameters"></a>Parametri  
 `mr`  
 in Token MemberRef per il quale restituire i metadati associati.  
  
 `ptk`  
 out Token TypeDef o TypeRef o TypeSpec che rappresenta la classe che dichiara il membro o un token ModuleRef che rappresenta la classe modulo che dichiara il membro o un MethodDef che rappresenta il membro.  
  
 `szMember`  
 out Buffer di stringa per il nome del membro.  
  
 `cchMember`  
 in Dimensioni richieste in caratteri wide di `szMember`.  
  
 `pchMember`  
 out Dimensioni restituite in caratteri wide di `szMember`.  
  
 `ppvSibBlob`  
 out Puntatore alla firma dei metadati binaria per il membro.  
  
 `pbSig`  
 out Dimensioni in byte del `ppvSigBlob`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
