---
title: Funzioni statiche globali di debug
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework debugging]
- debugging global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], debugging
ms.assetid: efc64414-77c3-48d0-881a-8594ed416aad
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e2403d736d031aab52525fc12b5071e764a8bde1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="debugging-global-static-functions"></a>Funzioni statiche globali di debug
Questa sezione descrive le funzioni statiche globali non gestite usate dall'API di debug.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Funzione _EFN_GetManagedExcepStack](../../../../docs/framework/unmanaged-api/debugging/efn-getmanagedexcepstack-function.md)  
 Restituisce una versione stringa della traccia dello stack contenuta internamente, dato l'indirizzo di un oggetto eccezione gestita.  
  
 [Funzione _EFN_GetManagedObjectFieldInfo](../../../../docs/framework/unmanaged-api/debugging/efn-getmanagedobjectfieldinfo-function.md)  
 Ottiene l'offset per un campo dall'inizio di un oggetto e il valore del campo, usando il puntatore all'oggetto e il nome di campo forniti.  
  
 [Funzione _EFN_GetManagedObjectName](../../../../docs/framework/unmanaged-api/debugging/efn-getmanagedobjectname-function.md)  
 Ottiene il nome di un tipo usando il puntatore all'oggetto gestito fornito.  
  
 [Funzione _EFN_StackTrace](../../../../docs/framework/unmanaged-api/debugging/efn-stacktrace-function.md)  
 Fornisce una rappresentazione testuale di una traccia dello stack gestito e una matrice di record `CONTEXT`, uno per ogni transizione tra codice non gestito e gestito.  
  
 [Funzione CLRDataCreateInstance](../../../../docs/framework/unmanaged-api/debugging/clrdatacreateinstance-function.md)  
 Chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR) per creare l'oggetto all'interfaccia specificata per il processo di destinazione specificato.  
  
 [Puntatore alla funzione PFN_CLRDataCreateInstance](../../../../docs/framework/unmanaged-api/debugging/pfn-clrdatacreateinstance-function-pointer.md)  
 Punta a una funzione chiamata dai servizi di accesso ai dati di CLR per creare l'oggetto all'interfaccia specificata per il processo di destinazione specificato.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Coclassi di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
