---
title: Metodo IMetaDataImport::FindField
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindField
helpviewer_keywords:
- IMetaDataImport::FindField method [.NET Framework metadata]
- FindField method [.NET Framework metadata]
ms.assetid: 38cd4e16-fbb2-471c-aa73-ac51a1931ad2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 88cd08b4290739808079bc8ecb713a5c5ea96584
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777897"
---
# <a name="imetadataimportfindfield-method"></a>Metodo IMetaDataImport::FindField
Ottiene un puntatore a FieldDef token per il campo che è racchiuso da specificato <xref:System.Type> e avente il nome e i metadati della firma specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `td`  
 [in] Il token TypeDef per la classe o interfaccia che racchiude il campo da cercare. Se questo valore è `mdTokenNil`, la ricerca viene eseguita per una variabile globale.  
  
 `szName`  
 [in] Il nome del campo da cercare.  
  
 `pvSigBlob`  
 [in] Un puntatore per la firma binaria dei metadati del campo.  
  
 `cbSigBlob`  
 [in] La dimensione in byte di `pvSigBlob`.  
  
 `pmb`  
 [out] Puntatore al token FieldDef corrispondente.  
  
## <a name="remarks"></a>Note  
 Si specifica il campo utilizzando la classe o interfaccia contenitore (`td`), il relativo nome (`szName`) e facoltativamente la firma (`pvSigBlob`).  
  
 La firma è passato a `FindField` deve essere stata generata nell'ambito corrente, in quanto le firme sono associate a un particolare ambito. Una firma possibile incorporare un token che identifica il tipo di classe o valore di inclusione. (Il token è un indice nella tabella di TypeDef locale). Non è possibile generare una firma in fase di esecuzione all'esterno del contesto dell'ambito corrente e usare tale firma come input per `FindField`.  
  
 `FindField` Trova solo i campi che sono stati definiti direttamente nella classe o interfaccia. i campi ereditati non viene trovato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
