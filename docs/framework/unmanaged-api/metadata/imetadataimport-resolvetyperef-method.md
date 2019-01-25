---
title: Metodo IMetaDataImport::ResolveTypeRef
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3c69c67c5c9d996bd746d82ea86caf4a396c0b10
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625237"
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
 [in] Il token di metadati TypeRef per restituire informazioni sul tipo di riferimento per.  
  
 `riid`  
 [in] IID dell'interfaccia da restituire `ppIScope`. In genere, questa sarebbe IID_IMetaDataImport.  
  
 `ppIScope`  
 [out] Interfaccia per l'ambito del modulo in cui è definito il tipo di riferimento.  
  
 `ptd`  
 [out] Puntatore a un token TypeDef che rappresenta il tipo di riferimento.  
  
## <a name="remarks"></a>Note  
  
> [!IMPORTANT]
>  Non utilizzare questo metodo se sono caricati più domini dell'applicazione. Il metodo non rispetta i limiti del dominio applicazione. Se sono caricate più versioni di un assembly e che contengono lo stesso tipo con lo stesso spazio dei nomi, il metodo restituisce l'ambito del modulo del primo tipo trovato.  
  
 Il `ResolveTypeRef` metodo cerca la definizione del tipo in altri moduli. Se viene trovata la definizione del tipo, `ResolveTypeRef` restituisce un'interfaccia per tale ambito di modulo, nonché il token TypeDef per il tipo.  
  
 Se il riferimento al tipo da risolvere dispone di un ambito di risoluzione di AssemblyRef, il `ResolveTypeRef` metodo cerca una corrispondenza solo negli ambiti dei metadati che sono già stati aperti mediante chiamate al metodo il [IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)metodo o la [IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) (metodo). Infatti, `ResolveTypeRef` non è possibile stabilire dal solo nell'ambito di AssemblyRef in cui è archiviato l'assembly sul disco o nella global assembly cache.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
