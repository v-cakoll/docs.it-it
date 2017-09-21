---
title: MDA invalidApartmentStateChange
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
- MDAs (managed debugging assistants), invalid apartment state
- managed debugging assistants (MDAs), invalid apartment state
- InvalidApartmentStateChange MDA
- invalid apartment state changes
- threading [.NET Framework], apartment states
- apartment states
- threading [.NET Framework], managed debugging assistants
- COM apartment states
ms.assetid: e56fb9df-5286-4be7-b313-540c4d876cd7
caps.latest.revision: 12
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f42a2b840a0cf678cfc2a06be0e9ed252c355a2a
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="invalidapartmentstatechange-mda"></a>MDA invalidApartmentStateChange
L'assistente al debug gestito `invalidApartmentStateChange` viene attivato quando si verificano due problemi diversi:  
  
-   Viene effettuato un tentativo di modificare lo stato di apartment COM di un thread che è già stato inizializzato da COM in uno stato di apartment diverso.  
  
-   Lo stato di apartment COM di un thread cambia in modo imprevisto.  
  
## <a name="symptoms"></a>Sintomi  
  
-   Lo stato di apartment COM di un thread è diverso da quello richiesto. Questo problema può causare l'uso di proxy per componenti COM associati a un modello di threading diverso da quello corrente. A sua volta, questo comportamento può provocare la generazione di un'eccezione <xref:System.InvalidCastException> quando viene chiamato l'oggetto COM tramite interfacce che non sono configurate per il marshalling tra diversi apartment.  
  
-   Lo stato di apartment COM del thread è diverso da quello previsto. Questo problema può provocare un'eccezione <xref:System.Runtime.InteropServices.COMException> con valore HRESULT impostato su RPC_E_WRONG_THREAD, nonché un'eccezione <xref:System.InvalidCastException> quando si effettuano chiamate in un [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW). Questo problema può anche far sì che diversi thread accedano contemporaneamente ad alcuni componenti COM a thread singolo, danneggiando i dati o provocandone la perdita.  
  
## <a name="cause"></a>Causa  
  
-   Il thread è stato precedentemente inizializzato in uno stato di apartment COM diverso. Si noti che lo stato di apartment di un thread può essere impostato in modo sia esplicito sia implicito. Le operazioni esplicite includono la proprietà <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=fullName> e i metodi <xref:System.Threading.Thread.SetApartmentState%2A> e <xref:System.Threading.Thread.TrySetApartmentState%2A>. Un thread creato con il metodo <xref:System.Threading.Thread.Start%2A> viene impostato in modo implicito su <xref:System.Threading.ApartmentState.MTA>, a meno che <xref:System.Threading.Thread.SetApartmentState%2A> non venga chiamato prima dell'avvio del thread. Anche il thread principale dell'applicazione viene inizializzato in modo implicito in <xref:System.Threading.ApartmentState.MTA>, a meno che nel metodo principale non sia specificato l'attributo <xref:System.STAThreadAttribute>.  
  
-   Nel thread viene chiamato il metodo `CoUninitialize` (o il metodo `CoInitializeEx`) con un modello di concorrenza diverso.  
  
## <a name="resolution"></a>Risoluzione  
 Impostare lo stato di apartment del thread prima dell'avvio dell'esecuzione oppure applicare l'attributo <xref:System.STAThreadAttribute> o <xref:System.MTAThreadAttribute> al metodo principale dell'applicazione.  
  
 Per la seconda causa, idealmente, il codice che chiama il metodo `CoUninitialize` deve essere modificato in modo da ritardare la chiamata finché il thread non sta per terminare e non vi sono RCW, né i rispettivi componenti COM sottostanti, ancora in uso da parte del thread. Tuttavia, se non è possibile modificare il codice che chiama il metodo `CoUninitialize`, nessun RCW può essere usato dai thread non inizializzati in questo modo.  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 L'assistente al debug gestito non ha alcun effetto su CLR.  
  
## <a name="output"></a>Output  
 Stato di apartment COM del thread corrente e stato che il codice stava tentando di applicare.  
  
## <a name="configuration"></a>Configurazione  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidApartmentStateChange />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente mostra una situazione che può comportare l'attivazione di questo assistente al debug gestito.  
  
```  
using System.Threading;  
namespace ApartmentStateMDA  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Thread.CurrentThread.SetApartmentState(ApartmentState.STA);  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnostica degli errori tramite gli assistenti al debug gestito](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Marshalling di interoperabilità](../../../docs/framework/interop/interop-marshaling.md)

