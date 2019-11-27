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
ms.openlocfilehash: 800b15bb75e74898cee9d838900ea14b60620940
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431467"
---
# <a name="imetadataimportresolvetyperef-method"></a>Metodo IMetaDataImport::ResolveTypeRef
Risolve un riferimento <xref:System.Type> rappresentato dal token TypeRef specificato.  
  
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
 in IID dell'interfaccia da restituire in `ppIScope`. In genere, questo IID_IMetaDataImport.  
  
 `ppIScope`  
 out Interfaccia per l'ambito del modulo in cui è definito il tipo a cui si fa riferimento.  
  
 `ptd`  
 out Puntatore a un token TypeDef che rappresenta il tipo a cui si fa riferimento.  
  
## <a name="remarks"></a>Osservazioni  
  
> [!IMPORTANT]
> Non usare questo metodo se vengono caricati più domini applicazione. Il metodo non rispetta i limiti del dominio applicazione. Se vengono caricate più versioni di un assembly e contengono lo stesso tipo con lo stesso spazio dei nomi, il metodo restituisce l'ambito del modulo del primo tipo trovato.  
  
 Il metodo `ResolveTypeRef` cerca la definizione del tipo in altri moduli. Se viene trovata la definizione del tipo, `ResolveTypeRef` restituisce un'interfaccia a tale ambito del modulo e il token TypeDef per il tipo.  
  
 Se il riferimento al tipo da risolvere ha un ambito di risoluzione di AssemblyRef, il metodo `ResolveTypeRef` cerca una corrispondenza solo negli ambiti dei metadati già aperti con le chiamate al metodo [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) o [IMetaDataDispenser:: OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) . Ciò è dovuto al fatto che `ResolveTypeRef` non è in grado di determinare solo dall'ambito AssemblyRef in cui è archiviato su disco o nel Global Assembly Cache assembly.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
