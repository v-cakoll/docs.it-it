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
ms.openlocfilehash: e3cdb648397ca4f4aa2326e4f2349a5a14c3edcc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178296"
---
# <a name="assemblycomparisonresult-enumeration"></a>Enumerazione AssemblyComparisonResult
Indica l'equivalenza di due identità assembly, come determinato dalla funzione [CompareAssemblyIdentity.](compareassemblyidentity-function.md)  
  
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
  
|Nome del membro|Descrizione|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|Indica che tutti i campi di assembly nel confronto corrispondono.|  
|`ACR_EquivalentFXUnified`|Indica che gli assembly sono considerati equivalenti in base all'unificazione dei numeri di versione degli assembly in .NET Framework versione 2.0.|  
|`ACR_EquivalentPartialFXUnified`|Indica una corrispondenza parziale degli assembly in base all'unificazione CLR dei numeri di versione dell'assembly in .NET Framework 2.0.|  
|`ACR_EquivalentPartialMatch`|Indica una corrispondenza parziale degli assembly.|  
|`ACR_EquivalentPartialUnified`|Indica una corrispondenza parziale degli assembly in base all'unificazione legacy dei numeri di versione.|  
|`ACR_EquivalentPartialWeakNamed`|Indica una corrispondenza parziale di assembly denominati semplicemente.|  
|`ACR_EquivalentUnified`|Indica che gli assembly sono considerati equivalenti in base all'unificazione CLR dei numeri di versione nelle versioni precedenti di .NET Framework.|  
|`ACR_EquivalentWeakNamed`|Indica una corrispondenza tra due assembly con nome semplicemente i cui numeri di versione sono stati ignorati.|  
|`ACR_NonEquivalent`|Indica che non si è verificata alcuna corrispondenza tra i due assembly.|  
|`ACR_NonEquivalentPartialVersion`|Indica che i due assembly corrispondono, ad eccezione dei relativi numeri di versione, che corrispondono solo parzialmente.|  
|`ACR_NonEquivalentVersion`|Indica che i due assembly corrispondono, ad eccezione dei relativi numeri di versione, che non corrispondono.|  
|`ACR_Unknown`|Indica che il motivo della non equivalenza non è noto.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Fusione.h  
  
 **Biblioteca:** Incluso come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione CompareAssemblyIdentity](compareassemblyidentity-function.md)
- [Enumerazioni Fusion](fusion-enumerations.md)
