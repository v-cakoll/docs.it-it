---
title: MDA memberInfoCacheCreation
ms.date: 03/30/2017
helpviewer_keywords:
- member info cache creation
- MemberInfoCacheCreation MDA
- reflection, run-time errors
- MDAs (managed debugging assistants), cache
- cache [.NET Framework], reflection
- managed debugging assistants (MDAs), cache
- MemberInfo cache
ms.assetid: 5abdad23-1335-4744-8acb-934002c0b6fe
ms.openlocfilehash: e5dbc769bd634afae06582ee614addafd611fad9
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217309"
---
# <a name="memberinfocachecreation-mda"></a>MDA memberInfoCacheCreation
L'assistente al debug gestito `memberInfoCacheCreation` viene attivato al momento della creazione di una cache <xref:System.Reflection.MemberInfo>. Si tratta di un'indicazione chiara di un programma che usa funzionalità di reflection onerose a livello di risorse.  
  
## <a name="symptoms"></a>Sintomi  
 Il working set di un programma aumenta perché il programma usa la reflection con uso intensivo delle risorse.  
  
## <a name="cause"></a>Causa  
 Le operazioni di reflection che richiamano oggetti <xref:System.Reflection.MemberInfo> sono considerate onerose a livello di risorse perché devono leggere i metadati archiviati in pagine ad accesso sporadico e in genere indicano che il programma usa un qualche tipo di scenario di associazione tardiva.  
  
## <a name="resolution"></a>Risoluzione  
 Per determinare se il programma usa la reflection, è possibile abilitare questo assistente al debug gestito e quindi eseguire il codice in un debugger o collegare un debugger quando viene attivato l'assistente al debug gestito. In un debugger si otterrà un'analisi dello stack che mostra la posizione in cui è stata creata la cache <xref:System.Reflection.MemberInfo> e da tale informazione è possibile determinare dove il programma usa la reflection.  
  
 La risoluzione dipende dagli obiettivi del codice. Questo assistente al debug gestito segnala che il programma ha uno scenario di associazione tardiva. È possibile valutare la sostituzione con uno scenario di associazione anticipata oppure esaminare le prestazioni dello scenario di associazione tardiva.  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 Questo assistente al debug gestito viene attivato ogni volta che viene creata una cache <xref:System.Reflection.MemberInfo>. L'impatto sulle prestazioni è trascurabile.  
  
## <a name="output"></a>Output  
 L'assistente al debug gestito genera un messaggio che indica che la cache <xref:System.Reflection.MemberInfo> è stata creata. Usare un debugger per ottenere un'analisi dello stack che mostra le posizioni in cui il programma usa la reflection.  
  
## <a name="configuration"></a>Configurazione  
  
```xml  
<mdaConfig>  
  <assistants>  
    <memberInfoCacheCreation/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Esempio  
 Questo codice di esempio attiverà l'assistente al debug gestito `memberInfoCacheCreation`.  
  
```csharp
using System;  
  
public class Exe  
{  
    public static void Main()  
    {  
        typeof(object).GetMethods();  
    }  
}  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Reflection.MemberInfo>
- [Diagnostica degli errori tramite gli assistenti al debug gestito](diagnosing-errors-with-managed-debugging-assistants.md)
