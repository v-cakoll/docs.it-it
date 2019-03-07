---
title: Funzione CompareAssemblyIdentity
ms.date: 03/30/2017
api_name:
- CompareAssemblyIdentity
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CompareAssemblyIdentity
helpviewer_keywords:
- CompareAssemblyIdentity function [.NET Framework fusion]
ms.assetid: 8b364ae1-8efa-4744-a7da-81fd093d84d6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0088ed696b2018054dc34a0b363def97c5753fe0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494090"
---
# <a name="compareassemblyidentity-function"></a>Funzione CompareAssemblyIdentity
Confronta due identità di assembly per determinare se sono equivalenti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
STDAPI CompareAssemblyIdentity (  
    [in]  LPCWSTR                  pwzAssemblyIdentity1,  
    [in]  BOOL                     fUnified1,  
    [in]  LPCWSTR                  pwzAssemblyIdentity2,  
    [in]  BOOL                     fUnified2,  
    [out] BOOL                     *pfEquivalent,  
    [out] AssemblyComparisonResult *pResult  
 );  
```  
  
## <a name="parameters"></a>Parametri  
 `pwzAssemblyIdentity1`  
 [in] L'identità testuale dell'assembly prima del confronto.  
  
 `fUnified1`  
 [in] Flag booleano che indica l'unificazione specificato dall'utente per `pwzAssemblyIdentity1`.  
  
 `pwzAssemblyIdentity2`  
 [in] L'identità testuale del secondo assembly nel confronto.  
  
 `fUnified2`  
 [in] Flag booleano che indica l'unificazione specificato dall'utente per `pwzAssemblyIdentity2`.  
  
 `pfEquivalent`  
 [out] Flag booleano che indica se i due assembly sono equivalenti.  
  
 `pResult`  
 [out] Un' [AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md) enumerazione che contiene informazioni dettagliate sul confronto.  
  
## <a name="return-value"></a>Valore restituito  
 `pfEquivalent` Restituisce un valore booleano che indica se i due assembly sono equivalenti. `pResult` Restituisce uno dei `AssemblyComparisonResult` valori, per fornire più dettagliate sul motivo per il valore di `pfEquivalent`.  
  
## <a name="remarks"></a>Note  
 `CompareAssemblyIdentity` Controlla se `pwzAssemblyIdentity1` e `pwzAssemblyIdentity2` sono equivalenti. `pfEquivalent` è impostato su `true` in uno o più delle condizioni seguenti:  
  
-   Le identità di due assembly sono equivalenti. Per assembly con nome sicuro, equivalency richiede il nome dell'assembly, versione, token di chiave pubblica e le impostazioni cultura in modo identico. Per gli assembly di nome semplice, equivalency richiede una corrispondenza per il nome dell'assembly e le impostazioni cultura.  
  
-   Entrambe le identità di assembly fare riferimento ad assembly in esecuzione su .NET Framework. Questa condizione restituisce `true` anche se i numeri di versione di assembly non corrispondono.  
  
-   I due assembly non sono gestiti, ma `fUnified1` oppure `fUnified2` è stata impostata su `true`.  
  
 Il `fUnified` flag indica che tutti i numeri di versione fino al numero di versione dell'assembly con nome sicuro vengono considerati equivalenti all'assembly con nome sicuro. Ad esempio, se il valore di `pwzAssemblyIndentity1` è "MyAssembly, versione = 3.0.0.0, culture = neutral, publicKeyToken =..." e il valore di `fUnified1` è `true`, ciò indica che tutte le versioni di MyAssembly dalla versione è 0.0.0.0 a 3.0.0.0 devono essere considerati equivalenti. In tal caso, se `pwzAssemblyIndentity2` fa riferimento allo stesso assembly come `pwzAssemblyIndentity1`, ad eccezione del fatto che abbia un numero di versione inferiore `pfEquivalent` è impostata su `true`. Se `pwzAssemblyIdentity2` fa riferimento a un numero di versione superiore `pfEquivalent` è impostata su `true` solo se il valore di `fUnified2` è `true`.  
  
 Il `pResult` parametro contiene informazioni specifiche sui motivi per cui i due assembly sono considerati equivalenti o non è equivalente. Per altre informazioni, vedere [enumerazione AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Funzioni statiche globali Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
- [Enumerazione AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md)
