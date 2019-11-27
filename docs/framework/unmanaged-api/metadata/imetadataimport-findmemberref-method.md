---
title: Metodo IMetaDataImport::FindMemberRef
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMemberRef
helpviewer_keywords:
- IMetaDataImport::FindMemberRef method [.NET Framework metadata]
- FindMemberRef method [.NET Framework metadata]
ms.assetid: 1ccda329-d752-4d89-abe8-511af3c3f4c9
topic_type:
- apiref
ms.openlocfilehash: 59512cc1c1b280d7fe6deb2f9d721ad53547e356
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437960"
---
# <a name="imetadataimportfindmemberref-method"></a>Metodo IMetaDataImport::FindMemberRef
Ottiene un puntatore al token MemberRef per il riferimento al membro racchiuso dall'<xref:System.Type> specificato e con il nome e la firma dei metadati specificati.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMemberRef        *pmr  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `td`  
 in Token TypeRef per la classe o l'interfaccia che racchiude il riferimento del membro da cercare. Se questo valore è `mdTokenNil`, la ricerca viene eseguita per una variabile globale o un riferimento a una funzione globale.  
  
 `szName`  
 in Nome del riferimento del membro da cercare.  
  
 `pvSigBlob`  
 in Puntatore alla firma dei metadati binari del riferimento al membro.  
  
 `cbSigBlob`  
 in Dimensioni in byte del `pvSigBlob`.  
  
 `pmr`  
 out Puntatore al token MemberRef corrispondente.  
  
## <a name="remarks"></a>Note  
 È possibile specificare il membro utilizzando la classe o l'interfaccia di inclusione (`td`), il nome (`szName`) e, facoltativamente, la relativa firma (`pvSigBlob`).  
  
 La firma passata a `FindMemberRef` deve essere stata generata nell'ambito corrente, perché le firme sono associate a un ambito specifico. Una firma può incorporare un token che identifica la classe o il tipo di valore contenitore. Il token è un indice nella tabella TypeDef locale. Non è possibile compilare una firma in fase di esecuzione all'esterno del contesto dell'ambito corrente e utilizzare tale firma come input per `FindMemberRef`.  
  
 `FindMemberRef` trova solo i riferimenti ai membri definiti direttamente nella classe o nell'interfaccia; non trova riferimenti a membri ereditati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
