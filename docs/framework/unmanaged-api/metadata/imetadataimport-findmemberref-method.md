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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 057dd7c25821aedddeee57a31200cf35c6df1273
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498515"
---
# <a name="imetadataimportfindmemberref-method"></a>Metodo IMetaDataImport::FindMemberRef
Ottiene un riferimento che è un puntatore al token MemberRef per il membro racchiusi specificato <xref:System.Type> e avente il nome e i metadati della firma specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMemberRef        *pmr  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `td`  
 [in] Il token TypeRef per la classe o interfaccia che racchiude il riferimento al membro da cercare. Se questo valore è `mdTokenNil`, la ricerca viene eseguita per una variabile globale o un riferimento alla funzione globale.  
  
 `szName`  
 [in] Il nome del riferimento al membro da cercare.  
  
 `pvSigBlob`  
 [in] Un puntatore per la firma binaria dei metadati del riferimento al membro.  
  
 `cbSigBlob`  
 [in] La dimensione in byte di `pvSigBlob`.  
  
 `pmr`  
 [out] Puntatore al token MemberRef corrispondente.  
  
## <a name="remarks"></a>Note  
 Si specifica il membro utilizzando la classe o interfaccia contenitore (`td`), il relativo nome (`szName`) e facoltativamente la firma (`pvSigBlob`).  
  
 La firma è passato a `FindMemberRef` deve essere stata generata nell'ambito corrente, in quanto le firme sono associate a un particolare ambito. Una firma possibile incorporare un token che identifica il tipo di classe o valore di inclusione. Il token è un indice nella tabella di TypeDef locale. Non è possibile generare una firma in fase di esecuzione all'esterno del contesto dell'ambito corrente e usare tale firma come input per `FindMemberRef`.  
  
 `FindMemberRef` Trova solo i riferimenti di membro che sono stati definiti direttamente nella classe o interfaccia. non trova riferimenti ai membri ereditati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
