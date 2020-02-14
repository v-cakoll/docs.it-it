---
title: MDA invalidMemberDeclaration
ms.date: 03/30/2017
helpviewer_keywords:
- invalid member declaration
- InvalidMemberDeclaration MDA
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
ms.openlocfilehash: 6033cd4178b2bc493794b5dcc527bc543ba24284
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216302"
---
# <a name="invalidmemberdeclaration-mda"></a>MDA invalidMemberDeclaration
L'assistente al debug gestito `invalidMemberDeclaration` viene attivato per segnalare un errore che si è verificato durante l'identificazione della modalità di marshalling dei parametri di un membro che deve essere chiamato da COM.  
  
## <a name="symptoms"></a>Sintomi  
 A COM viene restituito un HRESULT di errore senza che sia stato chiamato il metodo gestito.  
  
## <a name="cause"></a>Causa  
 La causa più probabile è la presenza di un attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> incompatibile in uno dei parametri.  
  
## <a name="resolution"></a>Risoluzione  
 Specificare attributi <xref:System.Runtime.InteropServices.MarshalAsAttribute> validi nei parametri.  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 L'assistente al debug gestito non ha alcun effetto su CLR.  
  
## <a name="output"></a>Output  
 Un messaggio informativo che contiene il nome del membro, il nome del tipo e il messaggio di errore.  
  
## <a name="configuration"></a>Configurazione  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnostica degli errori tramite gli assistenti al debug gestito](diagnosing-errors-with-managed-debugging-assistants.md)
- [Marshalling di interoperabilità](../interop/interop-marshaling.md)
