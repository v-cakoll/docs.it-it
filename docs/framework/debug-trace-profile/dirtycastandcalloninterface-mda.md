---
title: MDA dirtyCastAndCallOnInterface
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
- managed debugging assistants (MDAs), early bound calls AutoDispatch
- dispatch-only mode
- dirtyCastAndCallOnInterface
- early-bound managed classes
- early bound calls on AutoDispatch
- MDAs (managed debugging assistants), early bound calls AutoDispatch
- EarlyBoundCallOnAutorDispatchClassInteface MDA
ms.assetid: aa388ed3-7e3d-48ea-a0b5-c47ae19cec38
caps.latest.revision: 17
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 838348b3af485025ee196931237527333be73235
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="dirtycastandcalloninterface-mda"></a>MDA dirtyCastAndCallOnInterface
L'assistente al debug gestito `dirtyCastAndCallOnInterface` viene attivato quando viene tentata una chiamata ad associazione anticipata attraverso un vtable su un'interfaccia di classe contrassegnata solo per l'associazione tardiva.  
  
## <a name="symptoms"></a>Sintomi  
 Un'applicazione genera una violazione di accesso o ha un comportamento imprevisto quando si inserisce in CLR una chiamata ad associazione anticipata tramite COM.  
  
## <a name="cause"></a>Causa  
 Il codice sta tentando una chiamata ad associazione anticipata attraverso un vtable tramite un'interfaccia di classe solo ad associazione tardiva. Si noti che, per impostazione predefinita, le interfacce di classe vengono identificate solo come ad associazione tardiva. Possono essere identificate come ad associazione tardiva anche con l'attributo <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> con un valore <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch> (`[ClassInterface(ClassInterfaceType.AutoDispatch)]`).  
  
## <a name="resolution"></a>Risoluzione  
 La soluzione consigliata prevede di definire un'interfaccia esplicita da usare con COM e di fare in modo che i client COM chiamino tramite questa interfaccia invece che tramite l'interfaccia di classe generata automaticamente. In alternativa, è possibile trasformare la chiamata da COM in una chiamata ad associazione tardiva mediante `IDispatch`.  
  
 Infine, è possibile identificare la classe come <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> (`[ClassInterface(ClassInterfaceType.AutoDual)]`) per consentire alle chiamate ad associazione anticipata di essere inserite da COM. Tuttavia, l'uso di <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> è fortemente sconsigliato a causa delle limitazioni nel controllo delle versioni descritte in <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>.  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 L'assistente al debug gestito non ha alcun effetto su CLR. Segnala solo i dati sulle chiamate ad associazione anticipata sulle interfacce ad associazione tardiva.  
  
## <a name="output"></a>Output  
 Nome del metodo o nome del campo a cui si accede con associazione anticipata.  
  
## <a name="configuration"></a>Configurazione  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dirtyCastAndCallOnInterface />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>   
 [Diagnostica degli errori tramite gli assistenti al debug gestito](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)

