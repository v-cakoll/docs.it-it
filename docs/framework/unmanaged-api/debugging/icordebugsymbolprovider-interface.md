---
title: Interfaccia ICorDebugSymbolProvider
ms.date: 03/30/2017
ms.assetid: 85b24196-b6c6-4bda-9de3-47180bd6ff96
ms.openlocfilehash: 6f7a8a2b12c047b956a3b6e85fe8365e0360b3f2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791536"
---
# <a name="icordebugsymbolprovider-interface"></a>Interfaccia ICorDebugSymbolProvider
Fornisce metodi che possono essere usati per recuperare informazioni relative al simbolo di debug.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetAssemblyImageBytes](icordebugsymbolprovider-getassemblyimagebytes-method.md)|Legge i dati da un assembly sottoposto a merge tramite un indirizzo RVA (Relative Virtual Address) specificato nell'assembly sottoposto a merge.|  
|[Metodo GetAssemblyImageMetadata](icordebugsymbolprovider-getassemblyimagemetadata-method.md)|Restituisce i metadati da un assembly sottoposto a merge.|  
|[Metodo GetCodeRange](icordebugsymbolprovider-getcoderange-method.md)|Ottiene l'indirizzo iniziale del metodo e la dimensione sulla base di un indirizzo RVA (Relative Virtual Address) in un metodo.|  
|[Metodo GetInstanceFieldSymbols](icordebugsymbolprovider-getinstancefieldsymbols-method.md)|Ottiene i simboli dei campi di istanza che corrispondono a una firma typespec.|  
|[Metodo GetMergedAssemblyRecords](icordebugsymbolprovider-getmergedassemblyrecords-method.md)|Ottiene i record dei simboli per tutti gli assembly sottoposti a merge.|  
|[Metodo GetMethodLocalSymbols](icordebugsymbolprovider-getmethodlocalsymbols-method.md)|Ottiene i simboli locali del metodo da un indirizzo RVA (Relative Virtual Address) di tale metodo.|  
|[Metodo GetMethodParameterSymbols](icordebugsymbolprovider-getmethodparametersymbols-method.md)|Ottiene i parametri del metodo da un indirizzo RVA (Relative Virtual Address) di tale metodo.|  
|[Metodo GetMethodProps](icordebugsymbolprovider-getmethodprops-method.md)|Restituisce informazioni sulle proprietà del metodo, ad esempio il token di metadati del metodo e informazioni sui relativi parametri generici, da un indirizzo RVA (Relative Virtual Address) fornito in tale metodo.|  
|[Metodo GetObjectSize](icordebugsymbolprovider-getobjectsize-method.md)|Restituisce le dimensioni dell'oggetto per un oggetto in base alla relativa firma typespec.|  
|[Metodo GetStaticFieldSymbols](icordebugsymbolprovider-getstaticfieldsymbols-method.md)|Ottiene i simboli dei campi statici che corrispondono a una firma typespec.|  
|[Metodo GetTypeProps](icordebugsymbolprovider-gettypeprops-method.md)|Restituisce informazioni sulle proprietà di un tipo, ad esempio il numero di firma dei parametri generici, dato un indirizzo RVA (Relative Virtual Address) in un oggetto vtable.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
> Questa interfaccia è disponibile solo con .NET Native. Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
