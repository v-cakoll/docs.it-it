---
title: Metodo IMetaDataImport::ResolveTypeRef
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
- IMetaDataImport.ResolveTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResolveTypeRef
helpviewer_keywords:
- ResolveTypeRef method [.NET Framework metadata]
- IMetaDataImport::ResolveTypeRef method [.NET Framework metadata]
ms.assetid: 556bccfb-61bc-4761-b1d5-de4b1c18a38f
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 64a783297b27c9d1400670eecb7dfe4cb69c2b96
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportresolvetyperef-method"></a>Metodo IMetaDataImport::ResolveTypeRef
Risolve un <xref:System.Type> riferimento rappresentato dal token TypeRef specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `tr`  
 [in] Il token di metadati TypeRef per restituire le informazioni di riferimento di tipo per.  
  
 `riid`  
 [in] IID dell'interfaccia da restituire `ppIScope`. In genere, questo potrebbe essere IID_IMetaDataImport.  
  
 `ppIScope`  
 [out] Interfaccia per l'ambito del modulo in cui è definito il tipo di riferimento.  
  
 `ptd`  
 [out] Puntatore a un token TypeDef che rappresenta il tipo di riferimento.  
  
## <a name="remarks"></a>Note  
  
> [!IMPORTANT]
>  Non utilizzare questo metodo se vengono caricati più domini applicazione. Il metodo non rispetta i limiti del dominio applicazione. Se più versioni di un assembly vengono caricate e che contengono lo stesso tipo con lo stesso spazio dei nomi, il metodo restituisce l'ambito del modulo del primo tipo trovato.  
  
 Il `ResolveTypeRef` il metodo di ricerca per la definizione del tipo in altri moduli. Se viene trovata la definizione del tipo, `ResolveTypeRef` restituisce un'interfaccia per tale ambito del modulo, nonché il token TypeDef per il tipo.  
  
 Se il riferimento al tipo di risoluzione ha un ambito di risoluzione di AssemblyRef, il `ResolveTypeRef` metodo cerca una corrispondenza solo nell'ambito dei metadati che sono già stati aperti mediante chiamate al metodo di [IMetaDataDispenser::](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)metodo o [IMetaDataDispenser::](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) metodo. In questo modo `ResolveTypeRef` non può determinare solo dall'AssemblyRef ambito in cui è archiviato l'assembly sul disco o nella global assembly cache.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
