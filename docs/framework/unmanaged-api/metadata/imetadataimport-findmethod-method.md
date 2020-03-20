---
title: Metodo IMetaDataImport::FindMethod
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMethod
helpviewer_keywords:
- FindMethod method [.NET Framework metadata]
- IMetaDataImport::FindMethod method [.NET Framework metadata]
ms.assetid: 0f9bde1d-e306-438d-941b-d0925b322304
topic_type:
- apiref
ms.openlocfilehash: 53b3d94e8b1e273fcbc041d25a5bf586a12735c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177257"
---
# <a name="imetadataimportfindmethod-method"></a>Metodo IMetaDataImport::FindMethod
Ottiene un puntatore al token MethodDef per il <xref:System.Type> metodo racchiuso tra il nome e la firma dei metadati specificati.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `td`  
 [in] Token `mdTypeDef` per il tipo (una classe o un'interfaccia) che racchiude il membro da cercare. Se questo `mdTokenNil`valore è , la ricerca viene eseguita per una funzione globale.  
  
 `szName`  
 [in] Nome del metodo da cercare.  
  
 `pvSigBlob`  
 [in] Puntatore alla firma dei metadati binari del metodo.  
  
 `cbSigBlob`  
 [in] Dimensione in byte `pvSigBlob`di .  
  
 `pmb`  
 [fuori] Puntatore al token MethodDef corrispondente.  
  
## <a name="remarks"></a>Osservazioni  
 Il metodo viene specificato utilizzando la`td`relativa classe`szName`o interfaccia di inclusione ( ), il nome ( ) e, facoltativamente, la firma (`pvSigBlob`). Potrebbero essere presenti più metodi con lo stesso nome in una classe o interfaccia. In tal caso, passare la firma del metodo per trovare la corrispondenza univoca.  
  
 La firma `FindMethod` passata deve essere stata generata nell'ambito corrente, perché le firme sono associate a un ambito specifico. Una firma può incorporare un token che identifica la classe o il tipo di valore che lo contiene. Il token è un indice nella tabella TypeDef locale. Non è possibile compilare un'firma in fase di esecuzione all'esterno `FindMethod`del contesto dell'ambito corrente e utilizzare tale firma come input per l'input in .  
  
 `FindMethod`trova solo i metodi che sono stati definiti direttamente nella classe o nell'interfaccia; non trova i metodi ereditati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Incluso come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Reflection.MethodInfo>
- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
