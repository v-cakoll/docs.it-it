---
title: Metodo IMetaDataImport::FindMember
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
- IMetaDataImport.FindMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMember
helpviewer_keywords:
- IMetaDataImport::FindMember method [.NET Framework metadata]
- FindMember method [.NET Framework metadata]
ms.assetid: ad32fb84-c2b6-41cd-888d-787ff3a90449
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a20930688aed210309a719de2c7187f1f5fd1f24
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportfindmember-method"></a>Metodo IMetaDataImport::FindMember
Ottiene un puntatore al MemberDef token di campo o metodo incluso dall'oggetto <xref:System.Type> e con la firma di nome e i metadati specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,   
   [in]  PCCOR_SIGNATURE   pvSigBlob,   
   [in]  ULONG             cbSigBlob,   
   [out] mdToken           *pmb  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `td`  
 [in] Il token TypeDef per la classe o interfaccia che include il membro da cercare. Se questo valore è `mdTokenNil`, la ricerca viene eseguita per una variabile globale o una funzione globale.  
  
 `szName`  
 [in] Il nome del membro da cercare.  
  
 `pvSigBlob`  
 [in] Un puntatore per la firma binaria dei metadati del membro.  
  
 `cbSigBlob`  
 [in] Le dimensioni in byte di `pvSigBlob`.  
  
 `pmb`  
 [out] Puntatore al token MemberDef corrispondente.  
  
## <a name="remarks"></a>Note  
 Specificare il membro utilizzando la classe o interfaccia di inclusione (`td`), il nome (`szName`) e facoltativamente la firma (`pvSigBlob`). Potrebbero essere presenti più membri con lo stesso nome in una classe o interfaccia. In tal caso, passare la firma del membro per trovare una corrispondenza univoca.  
  
 La firma passata a `FindMember` deve essere stata generata nell'ambito corrente, in quanto le firme sono associate a un particolare ambito. Una firma è possibile incorporare un token che identifica il tipo di classe o un valore che lo contiene. Il token è un indice nella tabella TypeDef locale. Non è possibile generare una firma in fase di esecuzione all'esterno del contesto dell'ambito corrente e utilizzare tale firma come input a `FindMember`.  
  
 `FindMember`Trova solo i membri che sono stati definiti direttamente nella classe o interfaccia. i membri ereditati non viene trovato.  
  
> [!NOTE]
>  `FindMember`è un metodo di supporto. Chiama [IMetaDataImport:: FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); se la chiamata non trova una corrispondenza, `FindMember` chiama quindi [FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
