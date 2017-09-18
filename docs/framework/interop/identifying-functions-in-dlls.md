---
title: Identificazione delle funzioni nelle DLL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- platform invoke, identifying functions
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- identifying DLL functions
- DLL functions
ms.assetid: 3e3f6780-6d90-4413-bad7-ba641220364d
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b96ef668a8a11794b87d3cbe7c2ba864f8a75e2f
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="identifying-functions-in-dlls"></a>Identificazione delle funzioni nelle DLL
L'identità di una funzione di una DLL è costituita dagli elementi seguenti:  
  
-   Nome della funzione o numero ordinale  
  
-   Nome del file DLL in cui si può trovare l'implementazione  
  
 Ad esempio, specificando la funzione **MessageBox** in User32.dll, vengono identificate la funzione (**MessageBox**) e la sua posizione (User32.dll, User32 o user32). L'API (Application Programming Interface) di Microsoft Windows (API Win32) può contenere due versioni di ogni funzione che gestisce i caratteri e le stringhe: una versione ANSI con caratteri a 1 byte e una versione Unicode con caratteri a 2 byte. Se non è specificato, il set di caratteri, rappresentato dal campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>, usa come impostazione predefinita la versione ANSI. Alcune funzioni possono includere più di due versioni.  
  
 **MessageBoxA** è il punto di ingresso ANSI per la funzione **MessageBox**, mentre **MessageBoxW** è la versione Unicode. Per elencare i nomi di funzione per una DLL specifica, ad esempio user32.dll, è possibile eseguire numerosi strumenti della riga di comando. Ad esempio, è possibile usare `dumpbin /exports user32.dll` o `link /dump /exports user32.dll` per ottenere i nomi di funzione.  
  
 È possibile rinominare una funzione non gestita con qualsiasi nome desiderato all'interno del codice, a condizione di eseguire il mapping del nuovo nome al punto di ingresso originale nella DLL. Per istruzioni su come rinominare una funzione DLL non gestita in codice sorgente gestito, vedere [Specifica di un punto di ingresso](../../../docs/framework/interop/specifying-an-entry-point.md).  
  
 Platform invoke permette di controllare una parte significativa del sistema operativo chiamando funzioni nell'API Win32 e altre DLL. Oltre all'API Win32, sono disponibili molte altre API e DLL tramite platform invoke.  
  
 La tabella seguente descrive diverse DLL di uso comune nell'API Win32.  
  
|DLL|Descrizione del contenuto|  
|---------|-----------------------------|  
|GDI32.dll|Funzioni Graphics Device Interface (GDI) per l'output del dispositivo, ad esempio per il disegno e la gestione dei tipi di carattere.|  
|Kernel32.dll|Funzioni del sistema operativo di basso livello per la gestione delle memoria e delle risorse.|  
|User32.dll|Funzioni di gestione di Windows per la gestione dei messaggi, i timer, i menu e le comunicazioni.|  
  
 Per la documentazione completa dell'API Win32, vedere l'SDK della piattaforma. Per alcuni esempi che mostrano come costruire dichiarazioni basate su .NET da usare con platform invoke, vedere , vedere [Marshalling dei dati con platform invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Utilizzo di funzioni di DLL non gestite](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)   
 [Specifica di un punto di ingresso](../../../docs/framework/interop/specifying-an-entry-point.md)   
 [Creating a Class to Hold DLL Functions](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md)  (Creazione di una classe contenente funzioni di DLL)  
 [Creazione di prototipi nel codice gestito](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [Chiamata a una funzione di DLL](../../../docs/framework/interop/calling-a-dll-function.md)

