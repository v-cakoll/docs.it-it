---
title: Interfaccia IMetaDataDispenser
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser
helpviewer_keywords:
- IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 989840b3-9822-4ce5-a6c5-b375d3340a7a
topic_type:
- apiref
ms.openlocfilehash: 2bdfe65dbf923ec61d91a259b5257d892fef53da
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007338"
---
# <a name="imetadatadispenser-interface"></a>Interfaccia IMetaDataDispenser
Fornisce metodi per creare un nuovo ambito di metadati o per aprirne uno esistente.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo DefineScope](imetadatadispenser-definescope-method.md)|Crea una nuova area in memoria in cui è possibile creare nuovi metadati.|  
|[Metodo OpenScope](imetadatadispenser-openscope-method.md)|Apre un file su disco esistente ed esegue il mapping dei relativi metadati in memoria.|  
|[Metodo OpenScopeOnMemory](imetadatadispenser-openscopeonmemory-method.md)|Apre un'area di memoria contenente i metadati esistenti. Questo metodo apre un'area di memoria specificata in cui i dati esistenti vengono considerati come metadati.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataDispenserEx](imetadatadispenserex-interface.md)
- [Interfacce di metadati](metadata-interfaces.md)
