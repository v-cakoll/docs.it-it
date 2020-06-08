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
ms.openlocfilehash: f55af87e21b48430807166cb03e1d41271e830a1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503440"
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
 in IID dell'interfaccia da restituire in `ppIScope` . In genere, questo IID_IMetaDataImport.  
  
 `ppIScope`  
 out Interfaccia per l'ambito del modulo in cui è definito il tipo a cui si fa riferimento.  
  
 `ptd`  
 out Puntatore a un token TypeDef che rappresenta il tipo a cui si fa riferimento.  
  
## <a name="remarks"></a>Osservazioni  
  
> [!IMPORTANT]
> Non usare questo metodo se vengono caricati più domini applicazione. Il metodo non rispetta i limiti del dominio applicazione. Se vengono caricate più versioni di un assembly e contengono lo stesso tipo con lo stesso spazio dei nomi, il metodo restituisce l'ambito del modulo del primo tipo trovato.  
  
 Il `ResolveTypeRef` metodo cerca la definizione del tipo in altri moduli. Se viene trovata la definizione del tipo, `ResolveTypeRef` restituisce un'interfaccia a tale ambito del modulo e il token typedef per il tipo.  
  
 Se il riferimento al tipo da risolvere ha un ambito di risoluzione di AssemblyRef, il `ResolveTypeRef` metodo cerca una corrispondenza solo negli ambiti dei metadati già aperti con le chiamate al metodo [IMetaDataDispenser:: OpenScope](imetadatadispenser-openscope-method.md) o [IMetaDataDispenser:: OpenScopeOnMemory](imetadatadispenser-openscopeonmemory-method.md) . Ciò è dovuto `ResolveTypeRef` al fatto che non è in grado di determinare solo dall'ambito AssemblyRef in cui è archiviato l'assembly su disco o nel Global assembly cache.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](imetadataimport2-interface.md)
