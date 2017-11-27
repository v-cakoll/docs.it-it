---
title: Enumerazione AssemblyOptions
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyOptions
api_location: alink.dll
api_type: COM
f1_keywords: AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ccbbcabd3fbb372322ca6334f6ab6db4fdafc2f1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="assemblyoptions-enumeration"></a>Enumerazione AssemblyOptions
Enumera le opzioni di assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
|optAssemOS|Stringa - codificata come: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".|  
|optAssemProcessor|ULONG|  
|optAssemLocale|Stringa - contiene le impostazioni locali di assembly.|  
|optAssemVersion|Stringa - codificata come: "Principale".|  
|optAssemCompany|Stringa - contiene la società.|  
|optAssemProduct|Stringa - contiene il nome del prodotto.|  
|optAssemProductVersion|Stringa (noto anche come InformationalVersion).|  
|optAssemCopyright|Stringa - contiene le informazioni sul copyright.|  
|optAssemTrademark|Stringa - contiene le informazioni sul marchio.|  
|optAssemKeyFile|String (nome file).|  
|optAssemKeyName|Stringa (il nome della chiave).|  
|optAssemAlgID|ULONG|  
|optAssemFlags|ULONG|  
|optAssemHalfSign|Bool (anche noto come DelaySign).|  
|optAssemFileVersion|Stringa - codificata come "Revisione", corrisponde a ProductVersion.|  
|optAssemSatelliteVer|Stringa - codificata come "Revisione".|  
|optLastAssemOption|Un contatore del numero di elementi.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** alink.h  
  
 **Libreria**: alink.dll  
  
## <a name="see-also"></a>Vedere anche  
 [Al.exe (Assembly Linker)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
