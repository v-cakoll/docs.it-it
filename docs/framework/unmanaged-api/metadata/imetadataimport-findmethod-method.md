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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 857ea06ad8aba2a6de87bdf670ad0462a2f7dde1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487285"
---
# <a name="imetadataimportfindmethod-method"></a>Metodo IMetaDataImport::FindMethod
Ottiene un puntatore al MethodDef token per il metodo che è racchiuso da specificato <xref:System.Type> e avente il nome e i metadati della firma specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
 [in] Il `mdTypeDef` token per il tipo (una classe o interfaccia) che include il membro da cercare. Se questo valore è `mdTokenNil`, quindi la ricerca viene eseguita per una funzione globale.  
  
 `szName`  
 [in] Il nome del metodo da cercare.  
  
 `pvSigBlob`  
 [in] Un puntatore per la firma binaria dei metadati del metodo.  
  
 `cbSigBlob`  
 [in] La dimensione in byte di `pvSigBlob`.  
  
 `pmb`  
 [out] Puntatore al token MethodDef corrispondente.  
  
## <a name="remarks"></a>Note  
 Specificare il metodo utilizzando la classe o interfaccia che lo contiene (`td`), il relativo nome (`szName`) e facoltativamente la firma (`pvSigBlob`). Potrebbero esserci più metodi con lo stesso nome in una classe o interfaccia. In tal caso, passare la firma del metodo per trovare una corrispondenza univoca.  
  
 La firma è passato a `FindMethod` deve essere stata generata nell'ambito corrente, in quanto le firme sono associate a un particolare ambito. Una firma possibile incorporare un token che identifica il tipo di classe o valore di inclusione. Il token è un indice nella tabella di TypeDef locale. Non è possibile generare una firma in fase di esecuzione all'esterno del contesto dell'ambito corrente e usare come input a quella firma `FindMethod`.  
  
 `FindMethod` Trova solo i metodi che sono stati definiti direttamente nella classe o interfaccia. metodi ereditati non viene trovato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Reflection.MethodInfo>
- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
