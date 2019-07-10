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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: caec760cea52cb14d3fdb5d4cf0b59adcae5633b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782509"
---
# <a name="imetadataimportfindmember-method"></a>Metodo IMetaDataImport::FindMember
Ottiene un puntatore al MemberDef token per campo o un metodo che è racchiuso da specificato <xref:System.Type> e avente il nome e i metadati della firma specificata.  
  
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
 [in] Il token TypeDef per la classe o interfaccia che include il membro da cercare. Se questo valore è `mdTokenNil`, la ricerca viene eseguita per una variabile globale o una funzione globale.  
  
 `szName`  
 [in] Il nome del membro da cercare.  
  
 `pvSigBlob`  
 [in] Un puntatore per la firma binaria dei metadati del membro.  
  
 `cbSigBlob`  
 [in] La dimensione in byte di `pvSigBlob`.  
  
 `pmb`  
 [out] Puntatore al token MemberDef corrispondente.  
  
## <a name="remarks"></a>Note  
 Si specifica il membro utilizzando la classe o interfaccia contenitore (`td`), il relativo nome (`szName`) e facoltativamente la firma (`pvSigBlob`). Potrebbero essere presenti più membri con lo stesso nome in una classe o interfaccia. In tal caso, passare la firma del membro per trovare una corrispondenza univoca.  
  
 La firma è passato a `FindMember` deve essere stata generata nell'ambito corrente, in quanto le firme sono associate a un particolare ambito. Una firma possibile incorporare un token che identifica il tipo di classe o valore di inclusione. Il token è un indice nella tabella di TypeDef locale. Non è possibile generare una firma in fase di esecuzione all'esterno del contesto dell'ambito corrente e usare come input a quella firma `FindMember`.  
  
 `FindMember` Trova solo i membri che sono stati definiti direttamente nella classe o interfaccia. i membri ereditati non viene trovato.  
  
> [!NOTE]
>  `FindMember` è un metodo helper. Viene chiamato [FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); se tale chiamata non trova una corrispondenza `FindMember` quindi chiama [FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
