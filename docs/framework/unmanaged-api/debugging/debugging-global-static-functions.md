---
title: Funzioni statiche globali di debug
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework debugging]
- debugging global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], debugging
ms.assetid: efc64414-77c3-48d0-881a-8594ed416aad
ms.openlocfilehash: c20d8719b63cb40074dc740506ae4a3c0fc3a251
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793775"
---
# <a name="debugging-global-static-functions"></a>Funzioni statiche globali di debug
Questa sezione descrive le funzioni statiche globali non gestite usate dall'API di debug.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Funzione _EFN_GetManagedExcepStack](efn-getmanagedexcepstack-function.md)  
 Restituisce una versione stringa della traccia dello stack contenuta internamente, dato l'indirizzo di un oggetto eccezione gestita.  
  
 [Funzione _EFN_GetManagedObjectFieldInfo](efn-getmanagedobjectfieldinfo-function.md)  
 Ottiene l'offset per un campo dall'inizio di un oggetto e il valore del campo, usando il puntatore all'oggetto e il nome di campo forniti.  
  
 [Funzione _EFN_GetManagedObjectName](efn-getmanagedobjectname-function.md)  
 Ottiene il nome di un tipo usando il puntatore all'oggetto gestito fornito.  
  
 [Funzione _EFN_StackTrace](efn-stacktrace-function.md)  
 Fornisce una rappresentazione testuale di una traccia dello stack gestito e una matrice di record `CONTEXT`, uno per ogni transizione tra codice non gestito e gestito.  
  
 [Funzione CLRDataCreateInstance](clrdatacreateinstance-function.md)  
 Chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR) per creare l'oggetto all'interfaccia specificata per il processo di destinazione specificato.  
  
 [Puntatore alla funzione PFN_CLRDataCreateInstance](pfn-clrdatacreateinstance-function-pointer.md)  
 Punta a una funzione chiamata dai servizi di accesso ai dati di CLR per creare l'oggetto all'interfaccia specificata per il processo di destinazione specificato.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Coclassi di debug](debugging-coclasses.md)  
  
 [Interfacce di debug](debugging-interfaces.md)  
  
 [Enumerazioni di debug](debugging-enumerations.md)  
  
 [Strutture di debug](debugging-structures.md)
