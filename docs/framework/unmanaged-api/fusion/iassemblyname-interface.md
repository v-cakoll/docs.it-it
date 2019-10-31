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
ms.openlocfilehash: de49d66667033dfc6918b139f90cd5523661597f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134322"
---
# <a name="iassemblyname-interface"></a>Interfaccia IAssemblyName
Fornisce metodi per la descrizione e l'utilizzo dell'identità univoca di un assembly.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Clone](iassemblyname-clone-method.md)|Crea una copia superficiale di questo oggetto `IAssemblyName`.|  
|[Metodo Finalize](iassemblyname-finalize-method.md)|Consente a questo oggetto `IAssemblyName` di rilasciare risorse ed eseguire altre operazioni di pulizia prima che venga chiamato il relativo distruttore.|  
|[Metodo GetDisplayName](iassemblyname-getdisplayname-method.md)|Ottiene il nome leggibile dell'assembly a cui fa riferimento questo oggetto `IAssemblyName`.|  
|[Metodo GetName](iassemblyname-getname-method.md)|Ottiene il nome semplice e non crittografato dell'assembly a cui fa riferimento questo oggetto `IAssemblyName`.|  
|[Metodo GetProperty](iassemblyname-getproperty-method.md)|Ottiene un puntatore alla proprietà a cui fa riferimento il `PropertyId`specificato.|  
|[Metodo GetVersion](iassemblyname-getversion-method.md)|Ottiene le informazioni sulla versione per l'assembly a cui fa riferimento questo oggetto `IAssemblyName`.|  
|[Metodo IsEqual](iassemblyname-isequal-method.md)|Determina se un oggetto `IAssemblyName` specificato è uguale a questo `IAssemblyName`, in base ai flag di confronto specificati.|  
|[Metodo SetProperty](iassemblyname-setproperty-method.md)|Imposta il valore della proprietà a cui fa riferimento il `PropertyId`specificato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce Fusion](fusion-interfaces.md)
- [Interfaccia IAssemblyEnum](iassemblyenum-interface.md)
