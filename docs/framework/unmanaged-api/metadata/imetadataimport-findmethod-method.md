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
ms.openlocfilehash: c2ec907759a25048444ebcc81bf5bb0fd23ced58
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503653"
---
# <a name="imetadataimportfindmethod-method"></a>Metodo IMetaDataImport::FindMethod
Ottiene un puntatore al token MethodDef per il metodo racchiuso dall'oggetto specificato <xref:System.Type> e con il nome e la firma dei metadati specificati.  
  
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
 in `mdTypeDef`Token per il tipo, ovvero una classe o un'interfaccia, che racchiude il membro da cercare. Se questo valore è `mdTokenNil` , la ricerca viene eseguita per una funzione globale.  
  
 `szName`  
 in Nome del metodo da cercare.  
  
 `pvSigBlob`  
 in Puntatore alla firma dei metadati binari del metodo.  
  
 `cbSigBlob`  
 in Dimensioni in byte di `pvSigBlob` .  
  
 `pmb`  
 out Puntatore al token MethodDef corrispondente.  
  
## <a name="remarks"></a>Osservazioni  
 Il metodo viene specificato utilizzando la classe o l'interfaccia di inclusione ( `td` ), il nome ( `szName` ) e, facoltativamente, la relativa firma () `pvSigBlob` . Potrebbero essere presenti più metodi con lo stesso nome in una classe o in un'interfaccia. In tal caso, passare la firma del metodo per trovare la corrispondenza univoca.  
  
 La firma passata a `FindMethod` deve essere stata generata nell'ambito corrente, perché le firme sono associate a un ambito specifico. Una firma può incorporare un token che identifica la classe o il tipo di valore contenitore. Il token è un indice nella tabella TypeDef locale. Non è possibile compilare una firma in fase di esecuzione all'esterno del contesto dell'ambito corrente e utilizzare tale firma come input per l'input `FindMethod` .  
  
 `FindMethod`trova solo i metodi definiti direttamente nella classe o nell'interfaccia. non trova metodi ereditati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Reflection.MethodInfo>
- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](imetadataimport2-interface.md)
