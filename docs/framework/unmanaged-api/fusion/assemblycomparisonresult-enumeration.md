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
ms.openlocfilehash: 0086906b23cc65825bbd54a54e544fa9ec7b211e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796261"
---
# <a name="assemblycomparisonresult-enumeration"></a>Enumerazione AssemblyComparisonResult
Indica l'equivalenza di due identità di assembly, come determinato dalla funzione [CompareAssemblyIdentity](compareassemblyidentity-function.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
## <a name="members"></a>Members  
  
|Nome del membro|DESCRIZIONE|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|Indica che tutti i campi di assembly nel confronto corrispondono.|  
|`ACR_EquivalentFXUnified`|Indica che gli assembly sono considerati equivalenti in base all'unificazione del Common Language Runtime versione (CLR) dei numeri di versione dell'assembly nella .NET Framework versione 2,0.|  
|`ACR_EquivalentPartialFXUnified`|Indica una corrispondenza parziale degli assembly in base all'unificazione CLR dei numeri di versione dell'assembly nel .NET Framework 2,0.|  
|`ACR_EquivalentPartialMatch`|Indica una corrispondenza parziale degli assembly.|  
|`ACR_EquivalentPartialUnified`|Indica una corrispondenza parziale degli assembly in base all'unificazione legacy dei numeri di versione.|  
|`ACR_EquivalentPartialWeakNamed`|Indica una corrispondenza parziale di assembly semplicemente denominati.|  
|`ACR_EquivalentUnified`|Indica che gli assembly sono considerati equivalenti in base all'unificazione CLR dei numeri di versione nelle versioni legacy del .NET Framework.|  
|`ACR_EquivalentWeakNamed`|Indica una corrispondenza tra due assembly con nome semplice i cui numeri di versione sono stati ignorati.|  
|`ACR_NonEquivalent`|Indica che non è stata eseguita alcuna corrispondenza tra i due assembly.|  
|`ACR_NonEquivalentPartialVersion`|Indica che i due assembly corrispondono a eccezione dei rispettivi numeri di versione, che corrispondono solo parzialmente.|  
|`ACR_NonEquivalentVersion`|Indica che i due assembly corrispondono ad eccezione dei numeri di versione, che non corrispondono.|  
|`ACR_Unknown`|Indica che il motivo della mancata equivalenza non è noto.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Libreria** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione CompareAssemblyIdentity](compareassemblyidentity-function.md)
- [Enumerazioni Fusion](fusion-enumerations.md)
