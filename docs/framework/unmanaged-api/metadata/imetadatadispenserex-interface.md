---
title: Interfaccia IMetaDataDispenserEx
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx
helpviewer_keywords:
- IMetaDataDispenserEx interface [.NET Framework metadata]
ms.assetid: 78b3629e-77a2-4406-89c3-56b5cc2c4594
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7d930088d6e621885d14fc4bdab2475aa27594e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448700"
---
# <a name="imetadatadispenserex-interface"></a>Interfaccia IMetaDataDispenserEx
Estende il [interfaccia IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) interfaccia per fornire la funzionalità di controllo come API dei metadati sull'ambito dei metadati corrente.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo FindAssembly](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassembly-method.md)|Questo metodo non è implementato. Se chiamato, restituisce E_NOTIMPL.|  
|[Metodo FindAssemblyModule](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassemblymodule-method.md)|Questo metodo non è implementato. Se chiamato, restituisce E_NOTIMPL.|  
|[Metodo GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getcorsystemdirectory-method.md)|Ottiene la directory contenente corrente common language runtime (CLR). Questo metodo è supportato solo per uso dai debugger out-of-process. Se chiamato da un altro componente, verrà restituito E_NOTIMPL.|  
|[Metodo GetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getoption-method.md)|Ottiene il valore dell'opzione specificata per l'ambito dei metadati corrente. L'opzione controlla la modalità di gestione delle chiamate all'ambito dei metadati corrente.|  
|[Metodo OpenScopeOnITypeInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-openscopeonitypeinfo-method.md)|Questo metodo non è implementato. Se chiamato, restituisce E_NOTIMPL.|  
|[Metodo SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)|Imposta l'opzione specificata per un determinato valore per l'ambito dei metadati corrente. L'opzione controlla la modalità di gestione delle chiamate all'ambito dei metadati corrente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [Interfaccia IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
