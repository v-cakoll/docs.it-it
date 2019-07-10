---
title: Enumerazione AssemblyOptions
ms.date: 03/30/2017
api_name:
- AssemblyOptions
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 324e30f6cbcaa1d1d81c7c03967dbb629d2cd6e9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742273"
---
# <a name="assemblyoptions-enumeration"></a>Enumerazione AssemblyOptions
Enumera le opzioni di assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum _AssemblyOptions {  
    optAssemTitle = 0,  
    optAssemDescription,  
    optAssemConfig,  
    optAssemOS,  
    optAssemProcessor,  
    optAssemLocale,  
    optAssemVersion,  
    optAssemCompany,  
    optAssemProduct,  
    optAssemProductVersion,  
    optAssemCopyright,  
    optAssemTrademark,  
    optAssemKeyFile,  
    optAssemKeyName,  
    optAssemAlgID,  
    optAssemFlags,  
    optAssemHalfSign,  
    optAssemFileVersion,  
    optAssemSatelliteVer,  
    optLastAssemOption  
}   AssemblyOptions;  
```  
  
## <a name="fields"></a>Campi  
  
|Campo|Descrizione|  
|-----------|-----------------|  
|optAssemTitle|Stringa - rappresenta il titolo dell'assembly.|  
|optAssemDescription|Stringa - contiene la descrizione dell'assembly.|  
|optAssemConfig|Stringa - contiene la configurazione dell'assembly.|  
|optAssemOS|Stringa, codificata come: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".|  
|optAssemProcessor|ULONG|  
|optAssemLocale|Stringa - contiene le impostazioni locali di assembly.|  
|optAssemVersion|Stringa, codificata come: "Revisione".|  
|optAssemCompany|Stringa - contiene l'azienda.|  
|optAssemProduct|Stringa - contiene il nome del prodotto.|  
|optAssemProductVersion|Stringa (anche nota come InformationalVersion).|  
|optAssemCopyright|Stringa - contiene le informazioni sul copyright.|  
|optAssemTrademark|Stringa - contiene le informazioni sul marchio.|  
|optAssemKeyFile|String (nome file).|  
|optAssemKeyName|Stringa (il nome della chiave).|  
|optAssemAlgID|ULONG|  
|optAssemFlags|ULONG|  
|optAssemHalfSign|Bool (noto anche come DelaySign).|  
|optAssemFileVersion|Stringa - codificato come "Revisione", identico ProductVersion.|  
|optAssemSatelliteVer|Stringa - codificato come "Revisione".|  
|optLastAssemOption|Un contatore del numero di elementi.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** alink.h  
  
 **Libreria**: ALink. dll  
  
## <a name="see-also"></a>Vedere anche

- [Al.exe (Assembly Linker)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
