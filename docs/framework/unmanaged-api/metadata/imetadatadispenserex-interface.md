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
ms.openlocfilehash: 96f0c0c254ce255581ac2937c805096918ab29e8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008053"
---
# <a name="imetadatadispenserex-interface"></a>Interfaccia IMetaDataDispenserEx
Estende l'interfaccia dell' [interfaccia IMetaDataDispenser](imetadatadispenser-interface.md) per fornire la possibilità di controllare il funzionamento delle API dei metadati sull'ambito dei metadati corrente.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo FindAssembly](imetadatadispenserex-findassembly-method.md)|Questo metodo non è implementato. Se chiamato, restituisce E_NOTIMPL.|  
|[Metodo FindAssemblyModule](imetadatadispenserex-findassemblymodule-method.md)|Questo metodo non è implementato. Se chiamato, restituisce E_NOTIMPL.|  
|[Metodo GetCORSystemDirectory](imetadatadispenserex-getcorsystemdirectory-method.md)|Ottiene la directory che include la Common Language Runtime corrente (CLR). Questo metodo è supportato solo per l'utilizzo da debugger out-of-process. Se viene chiamato da un altro componente, restituirà E_NOTIMPL.|  
|[Metodo GetOption](imetadatadispenserex-getoption-method.md)|Ottiene il valore dell'opzione specificata per l'ambito dei metadati corrente. L'opzione consente di controllare il modo in cui vengono gestite le chiamate all'ambito dei metadati corrente.|  
|[Metodo OpenScopeOnITypeInfo](imetadatadispenserex-openscopeonitypeinfo-method.md)|Questo metodo non è implementato. Se chiamato, restituisce E_NOTIMPL.|  
|[Metodo SetOption](imetadatadispenserex-setoption-method.md)|Imposta l'opzione specificata su un valore specificato per l'ambito dei metadati corrente. L'opzione consente di controllare il modo in cui vengono gestite le chiamate all'ambito dei metadati corrente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di metadati](metadata-interfaces.md)
- [Interfaccia IMetaDataDispenser](imetadatadispenser-interface.md)
- [Interfaccia IMetaDataEmit](imetadataemit-interface.md)
- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
