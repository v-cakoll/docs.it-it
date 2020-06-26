---
title: "Procedura: aggiungere istruzioni di traccia al codice dell'applicazione"
description: Informazioni su come aggiungere istruzioni di traccia al codice dell'applicazione in .NET. I metodi usati più spesso per la traccia sono i metodi per la scrittura dell'output nei listener.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tracing [.NET Framework], conditional writes based on switches
- trace statements
- WriteLineIf method
- tracing [.NET Framework], adding trace statements
- Assert method, tracing code
- trace switches, conditional writes based on switches
- WriteIf method
ms.assetid: f3a93fa7-1717-467d-aaff-393e5c9828b4
ms.openlocfilehash: 0c75a8775649aabe73b02187c4604d2eb3a8435b
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415888"
---
# <a name="how-to-add-trace-statements-to-application-code"></a>Procedura: aggiungere istruzioni di traccia al codice dell'applicazione
I metodi usati più spesso per la traccia sono i metodi per la scrittura dell'output nei listener: **Write**, **WriteIf**, **WriteLine**, **WriteLineIf**, **Assert** e **Fail**. Questi metodi possono essere divisi in due categorie: **Write**, **WriteLine** e **Fail** generano tutti output in modo non condizionale, mentre **WriteIf**, **WriteLineIf** e **Assert** verificano una condizione booleana e scrivono o non scrivono il valore della condizione. **WriteIf** e **WriteLineIf** generano output se la condizione è `true` e **Assert** genera output se la condizione è `false`.  
  
 Quando si progetta la traccia e si esegue il debug strategia, è necessario considerare come si desidera visualizzare l'output. Più istruzioni **Write** costituite da informazioni non correlate creeranno un log che è difficile da leggere. D'altra parte, usando **WriteLine** per inserire istruzioni correlate in righe separate, potrebbe essere difficile distinguere quali informazioni sono correlate. In generale, usare più istruzioni **Write** quando si vogliono combinare informazioni provenienti da più origini per creare un singolo messaggio informativo e usare l’istruzione **WriteLine** quando si intende creare un unico messaggio completo.  
  
### <a name="to-write-a-complete-line"></a>Per scrivere una riga completa  
  
1. Chiamare il metodo <xref:System.Diagnostics.Trace.WriteLine%2A> o <xref:System.Diagnostics.Trace.WriteLineIf%2A>.  
  
     Un ritorno a capo viene aggiunto alla fine del messaggio restituito da questo metodo, quindi il messaggio successivo restituito da **Write**, **WriteIf**, **WriteLine** o **WriteLineIf** inizierà nella riga seguente:  
  
    ```vb  
    Dim errorFlag As Boolean = False  
    Trace.WriteLine("Error in AppendData procedure.")  
    Trace.WriteLineIf(errorFlag, "Error in AppendData procedure.")  
    ```  
  
    ```csharp  
    bool errorFlag = false;  
    System.Diagnostics.Trace.WriteLine ("Error in AppendData procedure.");  
    System.Diagnostics.Trace.WriteLineIf(errorFlag,
       "Error in AppendData procedure.");  
    ```  
  
### <a name="to-write-a-partial-line"></a>Per scrivere una riga parzialmente eseguita  
  
1. Chiamare il metodo <xref:System.Diagnostics.Trace.Write%2A> o <xref:System.Diagnostics.Trace.WriteIf%2A>.  
  
     Il messaggio successivo di **Write**, **WriteIf**, **WriteLine** o **WriteLineIf** inizierà sulla stessa riga del messaggio dell’istruzione **Write** o **WriteIf**:  
  
    ```vb  
    Dim errorFlag As Boolean = False  
    Trace.WriteIf(errorFlag, "Error in AppendData procedure.")  
    Debug.WriteIf(errorFlag, "Transaction abandoned.")  
    Trace.Write("Invalid value for data request")  
    ```  
  
    ```csharp  
    bool errorFlag = false;  
    System.Diagnostics.Trace.WriteIf(errorFlag,
       "Error in AppendData procedure.");  
    System.Diagnostics.Debug.WriteIf(errorFlag, "Transaction abandoned.");  
    Trace.Write("Invalid value for data request");  
    ```  
  
### <a name="to-verify-that-certain-conditions-exist-either-before-or-after-you-execute-a-method"></a>Per verificare che determinate condizioni esistano prima o dopo l'esecuzione di un metodo  
  
1. Chiamare il metodo <xref:System.Diagnostics.Trace.Assert%2A> .  
  
    ```vb  
    Dim i As Integer = 4  
    Trace.Assert(i = 5, "i is not equal to 5.")  
    ```  
  
    ```csharp  
    int i = 4;  
    System.Diagnostics.Trace.Assert(i == 5, "i is not equal to 5.");  
    ```  
  
    > [!NOTE]
    > È possibile usare **Assert** con operazioni di traccia e debug. In questo esempio viene restituito lo stack di chiamate nella raccolta **Listeners**. Per altre informazioni, vedere [Asserzioni nel codice gestito](/visualstudio/debugger/assertions-in-managed-code) e <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Diagnostics.Debug.WriteIf%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.Debug.WriteLineIf%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.Trace.WriteIf%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.Trace.WriteLineIf%2A?displayProperty=nameWithType>
- [Traccia e strumentazione di applicazioni](tracing-and-instrumenting-applications.md)
- [Procedura: Creare, inizializzare e configurare opzioni di traccia](how-to-create-initialize-and-configure-trace-switches.md)
- [Opzioni di traccia](trace-switches.md)
- [Listener di traccia](trace-listeners.md)
