---
title: Metodo IMetaDataImport::FindMember
ms.date: 03/30/2017
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
ms.openlocfilehash: 7a46fa5319a1badc0cf28dcdbf535a6ed017c9c9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437923"
---
# <a name="imetadataimportfindmember-method"></a>Metodo IMetaDataImport::FindMember
Ottiene un puntatore al token MemberDef per il campo o il metodo racchiuso dall'<xref:System.Type> specificato e con il nome e la firma dei metadati specificati.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,   
   [in]  PCCOR_SIGNATURE   pvSigBlob,   
   [in]  ULONG             cbSigBlob,   
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `td`  
 in Token TypeDef per la classe o l'interfaccia che racchiude il membro da cercare. Se questo valore è `mdTokenNil`, la ricerca viene eseguita per una variabile globale o una funzione globale.  
  
 `szName`  
 in Nome del membro da cercare.  
  
 `pvSigBlob`  
 in Puntatore alla firma dei metadati binari del membro.  
  
 `cbSigBlob`  
 in Dimensioni in byte del `pvSigBlob`.  
  
 `pmb`  
 out Puntatore al token MemberDef corrispondente.  
  
## <a name="remarks"></a>Note  
 È possibile specificare il membro utilizzando la classe o l'interfaccia di inclusione (`td`), il nome (`szName`) e, facoltativamente, la relativa firma (`pvSigBlob`). Potrebbero essere presenti più membri con lo stesso nome in una classe o in un'interfaccia. In tal caso, passare la firma del membro per trovare la corrispondenza univoca.  
  
 La firma passata a `FindMember` deve essere stata generata nell'ambito corrente, perché le firme sono associate a un ambito specifico. Una firma può incorporare un token che identifica la classe o il tipo di valore contenitore. Il token è un indice nella tabella TypeDef locale. Non è possibile compilare una firma in fase di esecuzione all'esterno del contesto dell'ambito corrente e utilizzare tale firma come input per l'input per `FindMember`.  
  
 `FindMember` trova solo i membri definiti direttamente nella classe o nell'interfaccia; non vengono trovati membri ereditati.  
  
> [!NOTE]
> `FindMember` è un metodo helper. Chiama [IMetaDataImport:: FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); Se la chiamata non trova una corrispondenza, `FindMember` chiama [IMetaDataImport:: FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
