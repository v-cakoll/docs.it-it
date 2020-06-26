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
# <a name="how-to-add-trace-statements-to-application-code"></a><span data-ttu-id="7fd1d-104">Procedura: aggiungere istruzioni di traccia al codice dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="7fd1d-104">How to: Add Trace Statements to Application Code</span></span>
<span data-ttu-id="7fd1d-105">I metodi usati più spesso per la traccia sono i metodi per la scrittura dell'output nei listener: **Write**, **WriteIf**, **WriteLine**, **WriteLineIf**, **Assert** e **Fail**.</span><span class="sxs-lookup"><span data-stu-id="7fd1d-105">The methods used most often for tracing are the methods for writing output to listeners: **Write**, **WriteIf**, **WriteLine**, **WriteLineIf**, **Assert**, and **Fail**.</span></span> <span data-ttu-id="7fd1d-106">Questi metodi possono essere divisi in due categorie: **Write**, **WriteLine** e **Fail** generano tutti output in modo non condizionale, mentre **WriteIf**, **WriteLineIf** e **Assert** verificano una condizione booleana e scrivono o non scrivono il valore della condizione.</span><span class="sxs-lookup"><span data-stu-id="7fd1d-106">These methods can be divided into two categories: **Write**, **WriteLine**, and **Fail** all emit output unconditionally, whereas **WriteIf**, **WriteLineIf**, and **Assert** test a Boolean condition, and write or do not write based on the value of the condition.</span></span> <span data-ttu-id="7fd1d-107">**WriteIf** e **WriteLineIf** generano output se la condizione è `true` e **Assert** genera output se la condizione è `false`.</span><span class="sxs-lookup"><span data-stu-id="7fd1d-107">**WriteIf** and **WriteLineIf** emit output if the condition is `true`, and **Assert** emits output if the condition is `false`.</span></span>  
  
 <span data-ttu-id="7fd1d-108">Quando si progetta la traccia e si esegue il debug strategia, è necessario considerare come si desidera visualizzare l'output.</span><span class="sxs-lookup"><span data-stu-id="7fd1d-108">When designing your tracing and debugging strategy, you should think about how you want the output to look.</span></span> <span data-ttu-id="7fd1d-109">Più istruzioni **Write** costituite da informazioni non correlate creeranno un log che è difficile da leggere.</span><span class="sxs-lookup"><span data-stu-id="7fd1d-109">Multiple **Write** statements filled with unrelated information will create a log that is difficult to read.</span></span> <span data-ttu-id="7fd1d-110">D'altra parte, usando **WriteLine** per inserire istruzioni correlate in righe separate, potrebbe essere difficile distinguere quali informazioni sono correlate.</span><span class="sxs-lookup"><span data-stu-id="7fd1d-110">On the other hand, using **WriteLine** to put related statements on separate lines may make it difficult to distinguish what information belongs together.</span></span> <span data-ttu-id="7fd1d-111">In generale, usare più istruzioni **Write** quando si vogliono combinare informazioni provenienti da più origini per creare un singolo messaggio informativo e usare l’istruzione **WriteLine** quando si intende creare un unico messaggio completo.</span><span class="sxs-lookup"><span data-stu-id="7fd1d-111">In general, use multiple **Write** statements when you want to combine information from multiple sources to create a single informative message, and use the **WriteLine** statement when you want to create a single, complete message.</span></span>  
  
### <a name="to-write-a-complete-line"></a><span data-ttu-id="7fd1d-112">Per scrivere una riga completa</span><span class="sxs-lookup"><span data-stu-id="7fd1d-112">To write a complete line</span></span>  
  
1. <span data-ttu-id="7fd1d-113">Chiamare il metodo <xref:System.Diagnostics.Trace.WriteLine%2A> o <xref:System.Diagnostics.Trace.WriteLineIf%2A>.</span><span class="sxs-lookup"><span data-stu-id="7fd1d-113">Call the <xref:System.Diagnostics.Trace.WriteLine%2A> or <xref:System.Diagnostics.Trace.WriteLineIf%2A> method.</span></span>  
  
     <span data-ttu-id="7fd1d-114">Un ritorno a capo viene aggiunto alla fine del messaggio restituito da questo metodo, quindi il messaggio successivo restituito da **Write**, **WriteIf**, **WriteLine** o **WriteLineIf** inizierà nella riga seguente:</span><span class="sxs-lookup"><span data-stu-id="7fd1d-114">A carriage return is appended to the end of the message this method returns, so that the next message returned by **Write**, **WriteIf**, **WriteLine**, or **WriteLineIf** will begin on the following line:</span></span>  
  
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
  
### <a name="to-write-a-partial-line"></a><span data-ttu-id="7fd1d-115">Per scrivere una riga parzialmente eseguita</span><span class="sxs-lookup"><span data-stu-id="7fd1d-115">To write a partial line</span></span>  
  
1. <span data-ttu-id="7fd1d-116">Chiamare il metodo <xref:System.Diagnostics.Trace.Write%2A> o <xref:System.Diagnostics.Trace.WriteIf%2A>.</span><span class="sxs-lookup"><span data-stu-id="7fd1d-116">Call the <xref:System.Diagnostics.Trace.Write%2A> or <xref:System.Diagnostics.Trace.WriteIf%2A> method.</span></span>  
  
     <span data-ttu-id="7fd1d-117">Il messaggio successivo di **Write**, **WriteIf**, **WriteLine** o **WriteLineIf** inizierà sulla stessa riga del messaggio dell’istruzione **Write** o **WriteIf**:</span><span class="sxs-lookup"><span data-stu-id="7fd1d-117">The next message put out by a **Write**, **WriteIf**, **WriteLine**, or **WriteLineIf** will begin on the same line as the message put out by the **Write** or **WriteIf** statement:</span></span>  
  
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
  
### <a name="to-verify-that-certain-conditions-exist-either-before-or-after-you-execute-a-method"></a><span data-ttu-id="7fd1d-118">Per verificare che determinate condizioni esistano prima o dopo l'esecuzione di un metodo</span><span class="sxs-lookup"><span data-stu-id="7fd1d-118">To verify that certain conditions exist either before or after you execute a method</span></span>  
  
1. <span data-ttu-id="7fd1d-119">Chiamare il metodo <xref:System.Diagnostics.Trace.Assert%2A> .</span><span class="sxs-lookup"><span data-stu-id="7fd1d-119">Call the <xref:System.Diagnostics.Trace.Assert%2A> method.</span></span>  
  
    ```vb  
    Dim i As Integer = 4  
    Trace.Assert(i = 5, "i is not equal to 5.")  
    ```  
  
    ```csharp  
    int i = 4;  
    System.Diagnostics.Trace.Assert(i == 5, "i is not equal to 5.");  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="7fd1d-120">È possibile usare **Assert** con operazioni di traccia e debug.</span><span class="sxs-lookup"><span data-stu-id="7fd1d-120">You can use **Assert** with both tracing and debugging.</span></span> <span data-ttu-id="7fd1d-121">In questo esempio viene restituito lo stack di chiamate nella raccolta **Listeners**.</span><span class="sxs-lookup"><span data-stu-id="7fd1d-121">This example outputs the call stack to any listener in the **Listeners** collection.</span></span> <span data-ttu-id="7fd1d-122">Per altre informazioni, vedere [Asserzioni nel codice gestito](/visualstudio/debugger/assertions-in-managed-code) e <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7fd1d-122">For more information, see [Assertions in Managed Code](/visualstudio/debugger/assertions-in-managed-code) and <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fd1d-123">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="7fd1d-123">See also</span></span>

- <xref:System.Diagnostics.Debug.WriteIf%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.Debug.WriteLineIf%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.Trace.WriteIf%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.Trace.WriteLineIf%2A?displayProperty=nameWithType>
- [<span data-ttu-id="7fd1d-124">Traccia e strumentazione di applicazioni</span><span class="sxs-lookup"><span data-stu-id="7fd1d-124">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)
- [<span data-ttu-id="7fd1d-125">Procedura: Creare, inizializzare e configurare opzioni di traccia</span><span class="sxs-lookup"><span data-stu-id="7fd1d-125">How to: Create, Initialize and Configure Trace Switches</span></span>](how-to-create-initialize-and-configure-trace-switches.md)
- [<span data-ttu-id="7fd1d-126">Opzioni di traccia</span><span class="sxs-lookup"><span data-stu-id="7fd1d-126">Trace Switches</span></span>](trace-switches.md)
- [<span data-ttu-id="7fd1d-127">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="7fd1d-127">Trace Listeners</span></span>](trace-listeners.md)
