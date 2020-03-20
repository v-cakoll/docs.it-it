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
ms.openlocfilehash: dab155b82d87609b3d3f390133e6490502a43518
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177277"
---
# <a name="imetadataimportfindmember-method"></a>Metodo IMetaDataImport::FindMember
Ottiene un puntatore al token MemberDef per il campo <xref:System.Type> o il metodo racchiuso dal nome specificato e con il nome e la firma dei metadati specificati.  
  
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
 [in] Token TypeDef per la classe o l'interfaccia che racchiude il membro da cercare. Se questo `mdTokenNil`valore è , la ricerca viene eseguita per una variabile globale o una funzione globale.  
  
 `szName`  
 [in] Nome del membro da cercare.  
  
 `pvSigBlob`  
 [in] Puntatore alla firma dei metadati binari del membro.  
  
 `cbSigBlob`  
 [in] Dimensione in byte `pvSigBlob`di .  
  
 `pmb`  
 [fuori] Puntatore al token MemberDef corrispondente.  
  
## <a name="remarks"></a>Osservazioni  
 Il membro viene specificato utilizzando la`td`relativa classe`szName`o interfaccia di inclusione ( ), il nome ( ) e, facoltativamente, la firma (`pvSigBlob`). Potrebbero essere presenti più membri con lo stesso nome in una classe o interfaccia. In tal caso, passare la firma del membro per trovare la corrispondenza univoca.  
  
 La firma `FindMember` passata deve essere stata generata nell'ambito corrente, perché le firme sono associate a un ambito specifico. Una firma può incorporare un token che identifica la classe o il tipo di valore che lo contiene. Il token è un indice nella tabella TypeDef locale. Non è possibile compilare un'firma in fase di esecuzione all'esterno `FindMember`del contesto dell'ambito corrente e utilizzare tale firma come input per l'input in .  
  
 `FindMember`trova solo i membri che sono stati definiti direttamente nella classe o nell'interfaccia; non trova i membri ereditati.  
  
> [!NOTE]
> `FindMember`è un metodo di supporto. Chiama [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); se tale chiamata non trova `FindMember` una corrispondenza, chiama [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Incluso come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
