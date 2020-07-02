---
title: 'Procedura: Fare riferimento a tipi .NET da COM'
description: Fare riferimento a tipi .NET da COM. I client VB possono visualizzare un oggetto .NET nel Visualizzatore oggetti, ma i client C++ devono fare riferimento a un file TLB con la \# direttiva Import.
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- importing type library
- COM interop, referencing .NET types
- interoperation with unmanaged code, referencing .NET types
- referencing .NET types
- interoperation with unmanaged code, importing type library
- type libraries
- COM interop, importing type library
ms.assetid: 54917f6f-cb18-4103-b622-856b55da93f3
ms.openlocfilehash: f8d052c7b9bac9c4bab61ab1950e9e89a7c73912
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618961"
---
# <a name="how-to-reference-net-types-from-com"></a>Procedura: Fare riferimento a tipi .NET da COM
Dal punto di vista del codice client e server, le differenze tra COM e .NET Framework sono in gran parte invisibili. I client di Microsoft Visual Basic possono visualizzare un oggetto .NET nel Visualizzatore oggetti, che espone i metodi e la sintassi, le proprietà e i campi dell'oggetto esattamente come se si trattasse di un normale oggetto COM.  
  
 Il processo per l'importazione di una libreria dei tipi è leggermente più complesso per i client C++, anche se si usano gli stessi strumenti per esportare i metadati in una libreria dei tipi COM. Per fare riferimento a membri di oggetti .NET da un client C++ non gestito, fare riferimento al file TLB (prodotto con Tlbexp.exe) con la direttiva **#import**. Quando si fa riferimento a una libreria dei tipi da C++, è necessario specificare l'opzione **raw_interfaces_only** o importare le definizioni nella libreria di classi di base, Mscorlib.tlb.  
  
### <a name="to-import-a-library"></a>Per importare una libreria  
  
- Specificare l'opzione **raw_interfaces_only** nella direttiva **#import**. Ad esempio:  
  
    ```cpp  
    #import "..\LoanLib\LoanLib.tlb" raw_interfaces_only  
    ```  
  
     -oppure-  
  
- Includere una direttiva #import per Mscorlib.tlb. Ad esempio:  
  
    ```cpp  
    #import "mscorlib.tlb"  
    #import "..\LoanLib\LoanLib.tlb"  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Esposizione di componenti .NET Framework a COM](exposing-dotnet-components-to-com.md)
- [Registrazione di assembly presso COM](registering-assemblies-with-com.md)
- [Chiamata di un oggetto .NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))
- [Distribuzione di un'applicazione per l'accesso COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))
