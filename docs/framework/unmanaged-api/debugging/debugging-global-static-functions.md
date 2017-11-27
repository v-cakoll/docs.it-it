---
title: Funzioni statiche globali di debug
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- global static functions [.NET Framework debugging]
- debugging global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], debugging
ms.assetid: efc64414-77c3-48d0-881a-8594ed416aad
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ad5d3ef689a251ea4b154afc5d1bfb387388ddb3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="debugging-global-static-functions"></a>Funzioni statiche globali di debug
Questa sezione descrive le funzioni statiche globali non gestite usate dall'API di debug.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Funzione EFN_GetManagedExcepStack](../../../../docs/framework/unmanaged-api/debugging/efn-getmanagedexcepstack-function.md)  
 Restituisce una versione stringa della traccia dello stack contenuta internamente, dato l'indirizzo di un oggetto eccezione gestita.  
  
 [Funzione EFN_GetManagedObjectFieldInfo](../../../../docs/framework/unmanaged-api/debugging/efn-getmanagedobjectfieldinfo-function.md)  
 Ottiene l'offset per un campo dall'inizio di un oggetto e il valore del campo, usando il puntatore all'oggetto e il nome di campo forniti.  
  
 [Funzione EFN_GetManagedObjectName](../../../../docs/framework/unmanaged-api/debugging/efn-getmanagedobjectname-function.md)  
 Ottiene il nome di un tipo usando il puntatore all'oggetto gestito fornito.  
  
 [Funzione EFN_StackTrace](../../../../docs/framework/unmanaged-api/debugging/efn-stacktrace-function.md)  
 Fornisce una rappresentazione testuale di una traccia dello stack gestito e una matrice di record `CONTEXT`, uno per ogni transizione tra codice non gestito e gestito.  
  
 [CLRDataCreateInstance (funzione)](../../../../docs/framework/unmanaged-api/debugging/clrdatacreateinstance-function.md)  
 Chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR) per creare l'oggetto all'interfaccia specificata per il processo di destinazione specificato.  
  
 [Alla funzione Pfn_clrdatacreateinstance](../../../../docs/framework/unmanaged-api/debugging/pfn-clrdatacreateinstance-function-pointer.md)  
 Punta a una funzione chiamata dai servizi di accesso ai dati di CLR per creare l'oggetto all'interfaccia specificata per il processo di destinazione specificato.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Coclassi di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
