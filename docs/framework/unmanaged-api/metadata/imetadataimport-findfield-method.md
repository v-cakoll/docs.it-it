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
ms.openlocfilehash: ac69bab45ccd39b6a055fe4d2f74950ab47da779
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataimportfindfield-method"></a>Metodo IMetaDataImport::FindField
Ottiene un puntatore al FieldDef token per il campo che è racchiuso da specificato <xref:System.Type> e con la firma di nome e i metadati specificata.  
  
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
  
#### <a name="parameters"></a>Parametri  
 `td`  
 [in] Il token TypeDef per la classe o interfaccia che racchiude il campo per la ricerca. Se questo valore è `mdTokenNil`, la ricerca verrà eseguita per una variabile globale.  
  
 `szName`  
 [in] Il nome del campo per la ricerca.  
  
 `pvSigBlob`  
 [in] Un puntatore per la firma binaria dei metadati del campo.  
  
 `cbSigBlob`  
 [in] Le dimensioni in byte di `pvSigBlob`.  
  
 `pmb`  
 [out] Puntatore al token FieldDef corrispondente.  
  
## <a name="remarks"></a>Note  
 Specificare il campo utilizzando la classe o interfaccia di inclusione (`td`), il nome (`szName`) e facoltativamente la firma (`pvSigBlob`).  
  
 La firma passata a `FindField` deve essere stata generata nell'ambito corrente, in quanto le firme sono associate a un particolare ambito. Una firma è possibile incorporare un token che identifica il tipo di classe o un valore che lo contiene. Il token è un indice nella tabella TypeDef locale. Non è possibile generare una firma in fase di esecuzione all'esterno del contesto dell'ambito corrente e utilizzare tale firma come input per `FindField`.  
  
 `FindField` Consente di individuare solo i campi che sono stati definiti direttamente nella classe o interfaccia. non trova i campi ereditati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
