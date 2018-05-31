---
title: Utilizzo di funzioni di DLL non gestite
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged functions, calling
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- platform invoke, about platform invoke
- DLL functions, consuming unmanaged
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- platform invoke
- DLL functions
ms.assetid: eca7606e-ebfb-4f47-b8d9-289903fdc045
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3166d6c95532706781188da0c56ebf9022038a50
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33388378"
---
# <a name="consuming-unmanaged-dll-functions"></a>Utilizzo di funzioni di DLL non gestite
Platform invoke è un servizio che consente al codice gestito di chiamare funzioni non gestite implementate in librerie a collegamento dinamico (DLL), come quelle nell'API Win32. Individua e richiama una funzione esportata ed esegue il marshalling degli argomenti (Integer, stringhe, matrici, strutture e così via) nel limite dell'interazione, in base alle necessità.  
  
 In questa sezione vengono presentate le attività associate all'utilizzo di funzioni DLL non gestite e sono disponibili altre informazioni su platform invoke. Oltre alle seguenti attività, vengono illustrate alcune considerazioni generali e viene fornito un collegamento a informazioni ed esempi aggiuntivi.  
  
#### <a name="to-consume-exported-dll-functions"></a>Per usare le funzioni DLL esportate  
  
1.  [Identificare le funzioni nelle DLL](../../../docs/framework/interop/identifying-functions-in-dlls.md).  
  
     È necessario specificare almeno il nome della funzione e il nome della DLL che la contiene.  
  
2.  [Creare una classe che contenga le funzioni DLL](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md).  
  
     È possibile usare una classe esistente, creare una classe per ogni funzione non gestita o creare una classe contenente un set di funzioni non gestite correlate.  
  
3.  [Creare prototipi nel codice gestito](../../../docs/framework/interop/creating-prototypes-in-managed-code.md).  
  
     [Visual Basic] Usare l'istruzione **Declare** con le parole chiave **Function** e **Lib**. In pochissimi casi, è possibile usare **DllImportAttribute** con le parole chiave **Shared Function**. Questi casi vengono illustrati più avanti in questa sezione.  
  
     [C#] Usare **DllImportAttribute** per identificare la DLL e la funzione. Contrassegnare il metodo con i modificatori **static** ed **extern**.  
  
     [C++] Usare **DllImportAttribute** per identificare la DLL e la funzione. Contrassegnare il metodo o la funzione wrapper con **extern "C"**.  
  
4.  [Chiamare una funzione DLL](../../../docs/framework/interop/calling-a-dll-function.md).  
  
     Chiamare il metodo sulla classe gestita come qualsiasi altro metodo gestito. Il [passaggio di strutture](../../../docs/framework/interop/passing-structures.md) e l'[implementazione di funzioni di callback](../../../docs/framework/interop/callback-functions.md) sono casi particolari.  
  
 Per alcuni esempi che mostrano come costruire dichiarazioni basate su .NET da usare con platform invoke, vedere , vedere [Marshalling dei dati con platform invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).  
  
## <a name="a-closer-look-at-platform-invoke"></a>Informazioni dettagliate su platform invoke  
 Platform invoke si basa sui metadati per individuare le funzioni esportate ed eseguire il marshalling degli argomenti in fase di esecuzione. Nella figura seguente viene illustrato questo processo.  
  
 ![Platform invoke](../../../docs/framework/interop/media/pinvoke.gif "pinvoke")  
Chiamata di platform invoke a una funzione DLL non gestita  
  
 Quando platform invoke chiama una funzione non gestita, esegue la sequenza di azioni seguente:  
  
1.  Individua la DLL contenente la funziona.  
  
2.  Carica la DLL in memoria.  
  
3.  Individua l'indirizzo della funzione in memoria ed effettua il push degli argomenti nello stack, eseguendo il marshalling dei dati in base alle necessità.  
  
    > [!NOTE]
    >  L'individuazione e il caricamento della DLL e l'individuazione dell'indirizzo della funzione in memoria si verificano solo alla prima chiamata alla funzione.  
  
4.  Trasferisce il controllo alla funzione non gestita.  
  
 Platform invoke dà luogo a eccezioni generate dalla funzione non gestita per il chiamante gestito.  
  
## <a name="see-also"></a>Vedere anche  
 [Interoperabilità con codice non gestito](../../../docs/framework/interop/index.md)  
 [Esempi di platform invoke](../../../docs/framework/interop/platform-invoke-examples.md)  
 [Marshalling di interoperabilità](../../../docs/framework/interop/interop-marshaling.md)  
