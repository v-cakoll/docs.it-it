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
ms.openlocfilehash: d8b8bfd0e70e75c702f32555c10f433a1ff4ae10
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175421"
---
# <a name="imetadataimportfindmemberref-method"></a>Metodo IMetaDataImport::FindMemberRef
Ottiene un puntatore al token MemberRef per il riferimento <xref:System.Type> al membro racchiuso dal nome specificato e con il nome e la firma dei metadati specificati.  
  
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
 [in] Token TypeRef per la classe o l'interfaccia che racchiude il riferimento al membro da cercare. Se questo `mdTokenNil`valore è , la ricerca viene eseguita per una variabile globale o un riferimento a una funzione globale.  
  
 `szName`  
 [in] Nome del riferimento del membro da cercare.  
  
 `pvSigBlob`  
 [in] Puntatore alla firma dei metadati binari del riferimento al membro.  
  
 `cbSigBlob`  
 [in] Dimensione in byte `pvSigBlob`di .  
  
 `pmr`  
 [fuori] Puntatore al token MemberRef corrispondente.  
  
## <a name="remarks"></a>Osservazioni  
 Il membro viene specificato utilizzando la`td`relativa classe`szName`o interfaccia di inclusione ( ), il nome ( ) e, facoltativamente, la firma (`pvSigBlob`).  
  
 La firma `FindMemberRef` passata deve essere stata generata nell'ambito corrente, perché le firme sono associate a un ambito specifico. Una firma può incorporare un token che identifica la classe o il tipo di valore che lo contiene. Il token è un indice nella tabella TypeDef locale. Non è possibile compilare un'firma in fase di esecuzione all'esterno del contesto dell'ambito corrente e utilizzare tale firma come input per `FindMemberRef`.  
  
 `FindMemberRef`trova solo i riferimenti ai membri definiti direttamente nella classe o nell'interfaccia; non trova riferimenti ai membri ereditati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Incluso come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
