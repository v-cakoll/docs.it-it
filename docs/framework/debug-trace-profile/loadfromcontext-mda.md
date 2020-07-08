---
title: MDA loadFromContext
description: Comprendere l'assistente al debug gestito di loadFromContext in .NET, che viene attivato se un assembly viene caricato nel contesto LoadFrom.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), LoadFrom context
- managed debugging assistants (MDAs), LoadFrom context
- LoadFrom context
- LoadFromContext MDA
ms.assetid: a9b14db1-d3a9-4150-a767-dcf3aea0071a
ms.openlocfilehash: 8d55268f2b2106dde4e488a6f0271fd3b17349da
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051649"
---
# <a name="loadfromcontext-mda"></a>MDA loadFromContext
L'assistente al debug gestito `loadFromContext` viene attivato se viene caricato un assembly nel contesto `LoadFrom`. Questa situazione può verificarsi come risultato di una chiamata di <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> o di altri metodi simili.  
  
## <a name="symptoms"></a>Sintomi  
 L'uso di alcuni metodi di caricamento può determinare il caricamento di un assembly nel contesto `LoadFrom`. L'uso di questo contesto può provocare un comportamento imprevisto per la serializzazione, il cast e la risoluzione delle dipendenze. In generale, per evitare problemi è preferibile che gli assembly vengano caricati nel contesto `Load`. Senza questo assistente al debug gestito, è difficile determinare il contesto in cui è stato caricato un assembly.  
  
## <a name="cause"></a>Causa  
 In genere, un assembly viene caricato nel contesto `LoadFrom` se è stato caricato da un percorso esterno al contesto `Load`, ad esempio la Global Assembly Cache o la proprietà <xref:System.AppDomainSetup.ApplicationBase%2A?displayProperty=nameWithType>.  
  
## <a name="resolution"></a>Soluzione  
 Configurare le applicazioni in modo che non siano più necessarie chiamate di <xref:System.Reflection.Assembly.LoadFrom%2A>. A questo scopo, è possibile usare le tecniche seguenti:  
  
- Installare gli assembly nella Global Assembly Cache.  
  
- Inserire gli assembly nella directory <xref:System.AppDomainSetup.ApplicationBase%2A> per <xref:System.AppDomain>. Nel caso del dominio predefinito, la directory <xref:System.AppDomainSetup.ApplicationBase%2A> è quella che contiene il file eseguibile che ha avviato il processo. In questo caso, può essere necessaria anche la creazione di un nuovo oggetto <xref:System.AppDomain> se non si vuole spostare l'assembly.  
  
- Aggiungere un percorso di sondaggio al file di configurazione dell'applicazione (con estensione config) o ai domini dell'applicazione secondari se nelle directory figlio relative al file eseguibile sono presenti assembly dipendenti.  
  
 In ogni caso, il codice può essere modificato in modo da usare il metodo <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 L'assistente al debug gestito non ha alcun effetto su CLR e segnala il contesto usato come risultato di una richiesta di caricamento.  
  
## <a name="output"></a>Output  
 L'assistente al debug gestito segnala che l'assembly è stato caricato nel contesto `LoadFrom`, specifica il nome semplice dell'assembly e il percorso e suggerisce anche le misure di prevenzione per evitare di usare il contesto `LoadFrom`.  
  
## <a name="configuration"></a>Configurazione  
  
```xml  
<mdaConfig>  
  <assistants>  
    <loadFromContext />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente mostra una situazione che può comportare l'attivazione dell'assistente al debug gestito:  
  
```csharp
using System.Reflection;  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // The following call caused the LoadFrom context to be used  
            // because the assembly is loaded using LoadFrom and the path is
            // located outside of the Load context probing path.
            Assembly.LoadFrom(@"C:\Text\Test.dll");  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Vedere anche

- [Diagnostica degli errori tramite gli assistenti al debug gestito](diagnosing-errors-with-managed-debugging-assistants.md)
