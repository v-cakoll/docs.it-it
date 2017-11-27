---
title: Enumerazione AssemblyComparisonResult
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyComparisonResult
api_location: fusion.dll
api_type: COM
f1_keywords: AssemblyComparisonResult
helpviewer_keywords: AssemblyComparisonResult enumeration [.NET Framework fusion]
ms.assetid: bd042f89-10b1-40ca-946e-46da082f5263
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 75c53e750ad031ccec944625be130547404767bd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="assemblycomparisonresult-enumeration"></a>Enumerazione AssemblyComparisonResult
Indica l'equivalenza di due identità di assembly, come determinato dal [CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md) (funzione).  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum _tagAssemblyComparisonResult {  
    ACR_Unknown,   
    ACR_EquivalentFullMatch,  
    ACR_EquivalentWeakNamed,  
    ACR_EquivalentFXUnified,  
    ACR_EquivalentUnified,    
    ACR_NonEquivalentVersion,  
    ACR_NonEquivalent,      
    ACR_EquivalentPartialMatch,  
    ACR_EquivalentPartialWeakNamed,    
    ACR_EquivalentPartialUnified,  
    ACR_EquivalentPartialFXUnified,  
    ACR_NonEquivalentPartialVersion    
} AssemblyComparisonResult;  
```  
  
## <a name="members"></a>Membri  
  
|Nome del membro|Descrizione|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|Indica che i campi degli assembly in corrispondenza di confronto.|  
|`ACR_EquivalentFXUnified`|Indica che gli assembly sono considerati equivalenti in base del common language runtime (CLR) versione unificazione dei numeri di versione di assembly in .NET Framework versione 2.0.|  
|`ACR_EquivalentPartialFXUnified`|Indica una corrispondenza parziale degli assembly in base l'unificazione CLR dei numeri di versione di assembly in .NET Framework 2.0.|  
|`ACR_EquivalentPartialMatch`|Indica una corrispondenza parziale degli assembly.|  
|`ACR_EquivalentPartialUnified`|Indica una corrispondenza parziale degli assembly basata sull'unificazione legacy di numeri di versione.|  
|`ACR_EquivalentPartialWeakNamed`|Indica una corrispondenza parziale degli assembly con nome semplice.|  
|`ACR_EquivalentUnified`|Indica che gli assembly sono considerati equivalenti in base l'unificazione CLR numeri di versione nelle versioni precedenti di .NET Framework.|  
|`ACR_EquivalentWeakNamed`|Indica una corrispondenza tra due assembly denominati semplicemente con numeri di versione sono stati ignorati.|  
|`ACR_NonEquivalent`|Indica che si è verificata alcuna corrispondenza tra i due assembly.|  
|`ACR_NonEquivalentPartialVersion`|Indica che i due assembly corrispondono ad eccezione dei numeri di versione, che corrispondono solo parzialmente.|  
|`ACR_NonEquivalentVersion`|Indica che i due assembly corrispondono ad eccezione dei numeri di versione non corrispondono.|  
|`ACR_Unknown`|Indica che non è noto il motivo per determinarne la non equivalenza.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [CompareAssemblyIdentity (funzione)](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)  
 [Enumerazioni Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
