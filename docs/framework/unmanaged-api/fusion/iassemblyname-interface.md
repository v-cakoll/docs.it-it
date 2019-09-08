---
title: Interfaccia IAssemblyName
ms.date: 03/30/2017
api_name:
- IAssemblyName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName
helpviewer_keywords:
- IAssemblyName interface [.NET Framework fusion]
ms.assetid: f7f8e605-6b67-4151-936f-f04ecd671d90
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aee9b986c1e26c1b2e34dac7151a00172451bbad
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796556"
---
# <a name="iassemblyname-interface"></a>Interfaccia IAssemblyName
Fornisce metodi per la descrizione e l'utilizzo dell'identità univoca di un assembly.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Clone](iassemblyname-clone-method.md)|Crea una copia superficiale dell' `IAssemblyName` oggetto.|  
|[Metodo Finalize](iassemblyname-finalize-method.md)|Consente a `IAssemblyName` questo oggetto di rilasciare risorse ed eseguire altre operazioni di pulizia prima che venga chiamato il relativo distruttore.|  
|[Metodo GetDisplayName](iassemblyname-getdisplayname-method.md)|Ottiene il nome leggibile dell'assembly a cui fa riferimento questo `IAssemblyName` oggetto.|  
|[Metodo GetName](iassemblyname-getname-method.md)|Ottiene il nome semplice e non crittografato dell'assembly a cui fa riferimento `IAssemblyName` questo oggetto.|  
|[Metodo GetProperty](iassemblyname-getproperty-method.md)|Ottiene un puntatore alla proprietà a cui fa riferimento l'oggetto `PropertyId`specificato.|  
|[Metodo GetVersion](iassemblyname-getversion-method.md)|Ottiene le informazioni sulla versione per l'assembly a cui fa `IAssemblyName` riferimento questo oggetto.|  
|[Metodo IsEqual](iassemblyname-isequal-method.md)|Determina se un oggetto `IAssemblyName` specificato è uguale `IAssemblyName`all'oggetto, in base ai flag di confronto specificati.|  
|[Metodo SetProperty](iassemblyname-setproperty-method.md)|Imposta il valore della proprietà a cui fa riferimento l'oggetto `PropertyId`specificato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce Fusion](fusion-interfaces.md)
- [Interfaccia IAssemblyEnum](iassemblyenum-interface.md)
