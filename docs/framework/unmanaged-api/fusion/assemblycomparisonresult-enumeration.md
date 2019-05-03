---
title: Enumerazione AssemblyComparisonResult
ms.date: 03/30/2017
api_name:
- AssemblyComparisonResult
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- AssemblyComparisonResult
helpviewer_keywords:
- AssemblyComparisonResult enumeration [.NET Framework fusion]
ms.assetid: bd042f89-10b1-40ca-946e-46da082f5263
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03b8ecc996e14263510e2d0a658cec020696c263
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61914500"
---
# <a name="assemblycomparisonresult-enumeration"></a>Enumerazione AssemblyComparisonResult
Indica l'equivalenza dei due identità di assembly, come determinato dal [CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md) (funzione).  
  
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
|`ACR_EquivalentFullMatch`|Indica che i campi degli assembly in corrispondenza il confronto.|  
|`ACR_EquivalentFXUnified`|Indica che gli assembly sono considerati equivalenti base unificazione degli versione (CLR) il common language runtime dei numeri di versione di assembly in .NET Framework versione 2.0.|  
|`ACR_EquivalentPartialFXUnified`|Indica una corrispondenza parziale degli assembly di base dell'unificazione CLR dei numeri di versione di assembly in .NET Framework 2.0.|  
|`ACR_EquivalentPartialMatch`|Indica una corrispondenza parziale degli assembly.|  
|`ACR_EquivalentPartialUnified`|Indica una corrispondenza parziale degli assembly in base all'unificazione legacy di numeri di versione.|  
|`ACR_EquivalentPartialWeakNamed`|Indica una corrispondenza parziale di assembly con nome semplice.|  
|`ACR_EquivalentUnified`|Indica che gli assembly sono considerati equivalenti in base l'unificazione CLR di numeri di versione in versioni legacy di .NET Framework.|  
|`ACR_EquivalentWeakNamed`|Indica una corrispondenza tra i due assembly denominati semplicemente cui numeri di versione sono stati ignorati.|  
|`ACR_NonEquivalent`|Indica che si è verificata alcuna corrispondenza tra i due assembly.|  
|`ACR_NonEquivalentPartialVersion`|Indica che i due assembly corrisponde, ad eccezione dei numeri di versione che corrispondono solo parzialmente.|  
|`ACR_NonEquivalentVersion`|Indica che i due assembly corrisponde, ad eccezione dei numeri di versione che non corrispondono.|  
|`ACR_Unknown`|Indica che non è noto il motivo per determinarne la non equivalenza.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)
- [Enumerazioni Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
