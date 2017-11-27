---
title: Interfaccia IMetaDataDispenserEx
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenserEx
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenserEx
helpviewer_keywords: IMetaDataDispenserEx interface [.NET Framework metadata]
ms.assetid: 78b3629e-77a2-4406-89c3-56b5cc2c4594
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5ecb4e94c0deed3ed62b2d2eb8b0309ca092abf8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenserex-interface"></a>Interfaccia IMetaDataDispenserEx
Estende il [interfaccia IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) interfaccia per fornire la funzionalità di controllo come API dei metadati sull'ambito dei metadati corrente.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[FindAssembly (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassembly-method.md)|Questo metodo non è implementato. Se chiamato, restituisce E_NOTIMPL.|  
|[FindAssemblyModule (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassemblymodule-method.md)|Questo metodo non è implementato. Se chiamato, restituisce E_NOTIMPL.|  
|[GetCORSystemDirectory (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getcorsystemdirectory-method.md)|Ottiene la directory contenente corrente common language runtime (CLR). Questo metodo è supportato solo per uso dai debugger out-of-process. Se chiamato da un altro componente, verrà restituito E_NOTIMPL.|  
|[GetOption (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getoption-method.md)|Ottiene il valore dell'opzione specificata per l'ambito dei metadati corrente. L'opzione controlla la modalità di gestione delle chiamate all'ambito dei metadati corrente.|  
|[OpenScopeOnITypeInfo (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-openscopeonitypeinfo-method.md)|Questo metodo non è implementato. Se chiamato, restituisce E_NOTIMPL.|  
|[SetOption (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)|Imposta l'opzione specificata per un determinato valore per l'ambito dei metadati corrente. L'opzione controlla la modalità di gestione delle chiamate all'ambito dei metadati corrente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [IMetaDataDispenser (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 [IMetaDataEmit (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataImport (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
