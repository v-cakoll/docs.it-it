---
title: MDA failedQI
ms.date: 03/30/2017
helpviewer_keywords:
- failed QueryInterface
- FailedQI MDA
- QueryInterface call failures
- MDAs (managed debugging assistants), failed QueryInterface
- managed debugging assistants (MDAs), failed QueryInterface
ms.assetid: 902dc863-34b3-477c-b433-b8a6bb6133c6
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 60fd5c29f716aa55f35c520794fbc9a0f673b9f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="failedqi-mda"></a>MDA failedQI
L'assistente al debug gestito `failedQI` viene attivato quando il runtime chiama `QueryInterface` su un puntatore a interfaccia COM per conto di un Runtime Callable Wrapper (RWC) e la chiamata `QueryInterface` non riesce.  
  
## <a name="symptoms"></a>Sintomi  
 Mancata riuscita di un cast su un RCW oppure errore imprevisto di una chiamata a COM da parte di un RCW.  
  
## <a name="cause"></a>Causa  
  
-   La chiamata viene effettuata da un contesto errato.  
  
-   Il proxy registrato non riesce a chiamare `QueryInterface` perché il tentativo di chiamata è stato effettuato nel contesto errato.  
  
-   Un proxy di proprietà di OLE ha restituito un HRESULT di errore.  
  
## <a name="resolution"></a>Risoluzione  
 Vedere la documentazione MSDN relativa alle regole COM.  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 Se una chiamata a `QueryInterface` non riesce, viene cambiato il contesto e viene tentata di nuovo la chiamata a `QueryInterface` per verificare se l'errore è stato causato da un contesto errato.  
  
## <a name="output"></a>Output  
 Il nome gestito e il GUID dell'interfaccia e l'oggetto HRESULT dell'errore.  
  
## <a name="configuration"></a>Configurazione  
  
```xml  
<mdaConfig>  
  <assistants>  
    <failedQI/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Diagnostica degli errori tramite gli assistenti al debug gestito](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [Marshalling di interoperabilità](../../../docs/framework/interop/interop-marshaling.md)
