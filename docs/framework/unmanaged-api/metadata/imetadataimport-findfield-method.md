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
ms.openlocfilehash: 11ea6e468909ea42e38bdc7b76c60c460c98025e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503666"
---
# <a name="imetadataimportfindfield-method"></a>Metodo IMetaDataImport::FindField
Ottiene un puntatore al token FieldDef per il campo racchiuso dall'oggetto specificato <xref:System.Type> e con il nome e la firma dei metadati specificati.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
 in Token TypeDef per la classe o l'interfaccia che racchiude il campo da ricercare. Se questo valore è `mdTokenNil` , la ricerca viene eseguita per una variabile globale.  
  
 `szName`  
 in Nome del campo da ricercare.  
  
 `pvSigBlob`  
 in Puntatore alla firma dei metadati binari del campo.  
  
 `cbSigBlob`  
 in Dimensioni in byte di `pvSigBlob` .  
  
 `pmb`  
 out Puntatore al token FieldDef corrispondente.  
  
## <a name="remarks"></a>Osservazioni  
 Il campo viene specificato utilizzando la classe o l'interfaccia di inclusione ( `td` ), il nome ( `szName` ) e, facoltativamente, la relativa firma () `pvSigBlob` .  
  
 La firma passata a `FindField` deve essere stata generata nell'ambito corrente, perché le firme sono associate a un ambito specifico. Una firma può incorporare un token che identifica la classe o il tipo di valore contenitore. (Il token è un indice nella tabella TypeDef locale). Non è possibile compilare una firma in fase di esecuzione all'esterno del contesto dell'ambito corrente e utilizzare tale firma come input per `FindField` .  
  
 `FindField`trova solo i campi definiti direttamente nella classe o nell'interfaccia; non trova i campi ereditati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](imetadataimport2-interface.md)
