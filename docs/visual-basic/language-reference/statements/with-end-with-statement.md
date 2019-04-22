---
title: Istruzione With...End With (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.With
helpviewer_keywords:
- With keyword [Visual Basic]
- loop structures [Visual Basic], and With...End With statements
- execution [Visual Basic], on object
- instructions, repeating
- With...End With statements [Visual Basic]
- With statement [Visual Basic]
- With statement [Visual Basic], nesting
- objects [Visual Basic], accessing
- With block
- End keyword [Visual Basic], With...End With statements
ms.assetid: 340d5fbb-4f43-48ec-a024-80843c137817
ms.openlocfilehash: de2edc6b16689673c3be6703ff1a201febe73526
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58825358"
---
# <a name="withend-with-statement-visual-basic"></a>Istruzione With...End With (Visual Basic)
Esegue una serie di istruzioni che fanno riferimento più volte a un singolo oggetto o struttura in modo da poter utilizzare una sintassi semplificata per le istruzioni quando si accede ai membri dell'oggetto o della struttura.  Quando si utilizza una struttura, è possibile leggere solo i valori dei membri o i metodi invoke e ottenere un errore se si tenta di assegnare valori ai membri di una struttura utilizzata in un'istruzione `With...End With`.  
  
## <a name="syntax"></a>Sintassi  
  
```  
With objectExpression  
    [ statements ]  
End With  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`objectExpression`|Obbligatorio. Espressione che restituisce un oggetto. L'espressione può essere arbitrariamente complessa ed essere valutata solo una volta. Può restituire qualsiasi tipo di dati, compresi i tipi di base.|  
|`statements`|Facoltativo. Una o più istruzioni tra `With` e `End With` che possono fare riferimento ai membri di un oggetto che verrà prodotto dalla valutazione di `objectExpression`.|  
|`End With`|Obbligatorio. Termina la definizione del blocco `With`.|  
  
## <a name="remarks"></a>Note  
 Utilizzando `With...End With`, è possibile eseguire una serie di istruzioni in un oggetto specificato senza specificare il nome dell'oggetto più volte. All'interno di un blocco di istruzioni `With`, è possibile specificare un membro dell'oggetto che inizia con un punto, come se l'oggetto dell'istruzione `With` lo precedesse.  
  
 Per modificare più proprietà in un singolo oggetto, ad esempio, è possibile inserire le istruzioni di assegnazione delle proprietà all'interno del blocco `With...End With`, facendo riferimento all'oggetto una sola volta anziché una volta per assegnazione di proprietà.  
  
 Se il codice accede allo stesso oggetto in più istruzioni, utilizzando l'istruzione di `With` si ottengono i vantaggi seguenti:  
  
-   Non è necessario valutare più volte un'espressione complessa o assegnare il risultato a una variabile temporanea per fare riferimento ai membri più volte.  
  
-   È possibile rendere il codice più leggibile eliminando le espressioni di qualificazione ripetitive.  
  
 Il tipo di dati `objectExpression` può essere qualsiasi tipo di classe o struttura o anche un tipo elementare di Visual Basic come `Integer`.  Se `objectExpression` restituisce qualcosa di diverso da un oggetto, è possibile leggere solo i valori dei membri o i metodi invoke e ottenere un errore se si tenta di assegnare valori ai membri di una struttura utilizzata in un'istruzione `With...End With`.  Si tratta dello stesso errore che si otterrebbe se viene richiamato un metodo che restituisce una struttura e immediatamente si accede e si assegna un valore a un membro del risultato della funzione, come `GetAPoint().x = 1`.  Il problema in entrambi i casi è che la struttura esiste solo nello stack di chiamate e in nessun caso un membro di una struttura modificata in tali situazioni può scrivere in una posizione in modo che altro codice del programma può osservare la modifica.  
  
 `objectExpression` viene valutato una volta, all'ingresso nel blocco. Non è possibile riassegnare `objectExpression` dall'interno del blocco `With`.  
  
 Dal blocco `With`, è possibile accedere ai metodi e alle proprietà del solo oggetto specificato senza qualifica. Metodi e proprietà di altri oggetti possono essere utilizzati ma è necessario qualificarli con i relativi nomi di oggetto.  
  
 È possibile inserire un'istruzione `With...End With` in un'altra. Le istruzioni `With...End With` annidate possono creare confusione se gli oggetti a cui si fa riferimento non sono chiari dal contesto. È necessario fornire un riferimento completo a un oggetto che si trova in un blocco `With` esterno quando si fa riferimento all'oggetto dal un blocco `With` interno.  
  
 Non è consentita la creazione di rami in un'istruzione `With` dall'esterno del blocco.  
  
 A meno che il blocco non contenga un ciclo, le istruzioni vengono eseguite una sola volta. È possibile annidare tipi diversi di strutture di controllo. Per altre informazioni, vedere [strutture di controllo annidate](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
> [!NOTE]
>  È possibile utilizzare la parola chiave `With` anche negli inizializzatori di oggetto. Per altre informazioni ed esempi, vedere [gli inizializzatori di oggetto: Tipi denominati e anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) e [tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
>   
>  Se si utilizza un blocco `With` solo per inizializzare le proprietà o i campi di un oggetto di cui è stata appena creata un'istanza, è possibile utilizzare un inizializzatore di oggetto.  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito, ogni blocco `With` esegue una serie di istruzioni su un singolo oggetto.  
  
 [!code-vb[VbVbalrWithStatement#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrwithstatement/vb/mainwindow.xaml.vb#2)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono annidate le istruzioni `With…End With`. Nell'istruzione `With` annidata, la sintassi fa riferimento all'oggetto interno.  
  
 [!code-vb[VbVbalrWithStatement#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrwithstatement/vb/mainwindow.xaml.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Generic.List%601>
- [Strutture di controllo annidate](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Inizializzatori di oggetto: Tipi denominati e anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
