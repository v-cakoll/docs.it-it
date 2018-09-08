---
title: Attività di espressioni regolari
ms.date: 03/30/2017
ms.assetid: b8f24694-49db-4339-92ec-014e3d4ae63b
ms.openlocfilehash: 50daa5b6d7baab37f372de4c30c2e0d12b4fa943
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44201010"
---
# <a name="regular-expression-activities"></a>Attività di espressioni regolari
In questo esempio viene illustrato come creare un set di attività che espongono la funzionalità delle espressioni regolari dello spazio dei nomi <xref:System.Text.RegularExpressions>. Queste attività personalizzate possono essere usate all'interno di un'applicazione flusso di lavoro. Per altre informazioni sulle espressioni regolari, vedere [N:System.Text.RegularExpressions](https://go.microsoft.com/fwlink/?LinkId=150434) Namespace.  
  
 Nella tabella seguente sono indicate in dettaglio le attività personalizzate in questo esempio.  
  
|Attività|Descrizione|  
|--------------|-----------------|  
|IsMatch|Specifica se l'espressione regolare ha trovato una corrispondenza nella stringa di input.|  
|Corrispondenze|Cerca una stringa di input di tutte le occorrenze di un'espressione regolare e restituisce tutte le corrispondenze esatte.|  
|Sostituisci|All'interno di una stringa di input specificata, sostituisce le stringhe che corrispondono ai criteri di ricerca dell'espressione regolare con una stringa di sostituzione specificata.|  
  
## <a name="ismatch"></a>IsMatch  
 L'attività personalizzata `IsMatch` restituisce `true` se la proprietà della stringa di `Input` trova una corrispondenza nell'espressione regolare specificata nella proprietà `Pattern`. L'attività deriva da <xref:System.Activities.CodeActivity%601> e all'interno del metodo <xref:System.Activities.CodeActivity%601.Execute%2A> chiama il metodo <xref:System.Text.RegularExpressions.Regex.IsMatch%2A>.  
  
 Nella tabella seguente vengono descritte le proprietà e il valore restituito per l'attività personalizzata `IsMatch`.  
  
|Proprietà o valore restituito|Descrizione|  
|------------------------------|-----------------|  
|Pattern (obbligatorio)|Espressione regolare con cui eseguire la ricerca.|  
|Input (obbligatorio)|Stringa di input da cercare.|  
|RegexOptions|Combinazione bit per bit dei [RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446) valori di enumerazione.|  
|Valore restituito|`true` se l'input trova una corrispondenza nel criterio di ricerca specificato; in caso contrario, `false`.|  
  
 Nell'esempio di codice riportato di seguito viene illustrato come usare l'attività personalizzata `IsMatch`.  
  
```  
new IsMatch  
{  
    Pattern = new InArgument<string>( @"^-?\d+(\.\d{2})?$"),  
    Input = "20.00",  
};  
```  
  
## <a name="matches"></a>Corrispondenze  
 L'attività personalizzata `Matches` cerca una stringa di input di tutte le occorrenze di un'espressione regolare e restituisce tutte le corrispondenze esatte. L'attività deriva da <xref:System.Activities.CodeActivity%601> e all'interno del metodo <xref:System.Activities.CodeActivity%601.Execute%2A> chiama il metodo <xref:System.Text.RegularExpressions.Regex.Matches%2A>.  
  
 Nella tabella seguente vengono descritte le proprietà e il valore restituito per l'attività personalizzata `IsMatch`.  
  
|Proprietà o valore restituito|Descrizione|  
|------------------------------|-----------------|  
|Pattern (obbligatorio)|Espressione regolare con cui eseguire la ricerca.|  
|Input (obbligatorio)|Stringa di input da cercare.|  
|RegexOptions|Combinazione bit per bit dei [RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446) valori di enumerazione.|  
|Valore restituito|Oggetto <xref:System.Text.RegularExpressions.MatchCollection> che contiene la raccolta di corrispondenze esatte.|  
  
 Nell'esempio di codice riportato di seguito viene illustrato come usare l'attività personalizzata `Matches`.  
  
```  
new Matches  
{  
    Pattern = @"\b(?<word>\w+)\s+(\k<word>)\b",  
    Input = "The quick brown fox  fox jumped over over the lazy dog dog.",  
};  
```  
  
## <a name="replace"></a>Sostituisci  
 L'attività personalizzata `Replace` cerca una stringa di input e sostituisce tutte le stringhe che corrispondono a un'espressione regolare specificata con una stringa. L'attività deriva da <xref:System.Activities.CodeActivity%601> e all'interno del metodo <xref:System.Activities.CodeActivity%601.Execute%2A> chiama il metodo <xref:System.Text.RegularExpressions.Regex.Replace%2A>.  
  
 Nella tabella seguente vengono descritte le proprietà e il valore restituito per l'attività personalizzata `Replace`.  
  
|Proprietà o valore restituito|Descrizione|  
|------------------------------|-----------------|  
|Pattern (obbligatorio)|Espressione regolare con cui eseguire la ricerca.|  
|Input (obbligatorio)|Stringa di input da cercare.|  
|Replacement|Stringa di sostituzione.<br /><br /> Se viene specificato `Replacement`, la proprietà `MatchEvaluator` viene ignorata. Deve essere impostata la proprietà `Replacement` o `MatchEvaluator`.|  
|MatchEvaluator|Metodo personalizzato che esamina ogni corrispondenza e restituisce la stringa corrispondente originale o una stringa di sostituzione.<br /><br /> Se viene specificato `Replacement`, la proprietà `MatchEvaluator` viene ignorata. Deve essere impostata la proprietà `Replacement` o `MatchEvaluator`.|  
|RegexOptions|Combinazione bit per bit dei [RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446) valori di enumerazione.|  
|Valore restituito|Oggetto <xref:System.Text.RegularExpressions.MatchCollection> che contiene la raccolta di corrispondenze esatte.|  
  
 Nell'esempio di codice riportato di seguito viene illustrato come usare l'attività personalizzata `Replace`.  
  
```  
// Using the replacement string.  
new Replace  
{  
    Pattern = @"\bWorld\b",  
    Input = "Hello World! This is a wonderful World",  
    Replacement = "Universe"  
};  
  
// Using a match evaluator.  
new Replace  
{  
    Pattern = new InArgument<string>(pattern),  
    Input = new InArgument<string>(input),  
    MatchEvaluator = new MatchEvaluator(CapText)                  
};  
```  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione RegexActivities.sln.  
  
2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3.  Per eseguire la soluzione, premere CTRL+F5.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Regex`