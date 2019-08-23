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
ms.openlocfilehash: f323e91e60c9735a51e955eaab6673ca167f294d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951875"
---
# <a name="imetadataimportresolvetyperef-method"></a>Metodo IMetaDataImport::ResolveTypeRef
Risolve un <xref:System.Type> riferimento rappresentato dal token TypeRef specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `tr`  
 in Token di metadati TypeRef per cui restituire le informazioni sul tipo a cui si fa riferimento.  
  
 `riid`  
 in IID dell'interfaccia da restituire in `ppIScope`. Si tratta in genere di IID_IMetaDataImport.  
  
 `ppIScope`  
 out Interfaccia per l'ambito del modulo in cui è definito il tipo a cui si fa riferimento.  
  
 `ptd`  
 out Puntatore a un token TypeDef che rappresenta il tipo a cui si fa riferimento.  
  
## <a name="remarks"></a>Note  
  
> [!IMPORTANT]
> Non usare questo metodo se vengono caricati più domini applicazione. Il metodo non rispetta i limiti del dominio applicazione. Se vengono caricate più versioni di un assembly e contengono lo stesso tipo con lo stesso spazio dei nomi, il metodo restituisce l'ambito del modulo del primo tipo trovato.  
  
 Il `ResolveTypeRef` metodo cerca la definizione del tipo in altri moduli. Se viene trovata la definizione del tipo `ResolveTypeRef` , restituisce un'interfaccia a tale ambito del modulo e il token typedef per il tipo.  
  
 Se il riferimento al tipo da risolvere ha un ambito di risoluzione di AssemblyRef, `ResolveTypeRef` il metodo cerca una corrispondenza solo negli ambiti dei metadati già aperti con le chiamate al metodo [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) o [ Metodo IMetaDataDispenser:: OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) . Ciò è dovuto `ResolveTypeRef` al fatto che non è in grado di determinare solo dall'ambito AssemblyRef in cui è archiviato l'assembly su disco o nel Global assembly cache.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
