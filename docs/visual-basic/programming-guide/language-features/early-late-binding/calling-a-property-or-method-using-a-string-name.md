---
title: Chiamata di una proprietà o di un metodo mediante un nome di stringa (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- passing operators [Visual Basic]
- strings [Visual Basic], passing new operators as
- objects [Visual Basic], setting properties
- setting properties, object properties at run time
- method calls [Visual Basic], strings
- methods [Visual Basic], calling with string names
- calling methods [Visual Basic], string names
- properties [Visual Basic], setting at run time
- CallByName function
ms.assetid: 79a7b8b4-b8c7-4ad8-aca8-12a9a2b32f03
ms.openlocfilehash: 865270cfc8089d0bf229d9de7a7775dd2a3361d4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54731522"
---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a>Chiamata di una proprietà o di un metodo mediante un nome di stringa (Visual Basic)
Nella maggior parte dei casi, è possibile individuare le proprietà e metodi di un oggetto in fase di progettazione e scrivere codice per gestirli. Tuttavia, in alcuni casi potrebbe non sapere sui metodi e proprietà di un oggetto in anticipo, oppure è possibile semplicemente la flessibilità di un utente finale di specificare le proprietà o eseguire i metodi in fase di esecuzione.  
  
## <a name="callbyname-function"></a>CallByName (funzione)  
 Si consideri, ad esempio, un'applicazione client che valuta le espressioni immesse dall'utente mediante il passaggio di un operatore per un componente COM. Si supponga che si aggiunge costantemente nuove funzioni per il componente che richiedono nuovi operatori. Quando si usano tecniche di accesso agli oggetti standard, è necessario ricompilare e ridistribuire l'applicazione client prima che potrebbe usare gli operatori di nuovo. Per evitare questo problema, è possibile usare il `CallByName` funzione per passare nuovi operatori come stringhe, senza apportare modifiche all'applicazione.  
  
 Il `CallByName` funzione consente di utilizzare una stringa per specificare una proprietà o metodo in fase di esecuzione. La firma per il `CallByName` funzione si presenta come segue:  
  
 *Result* = `CallByName`(*Object*, *ProcedureName*, *CallType*, *Arguments*())  
  
 Il primo argomento, *oggetto*, accetta il nome dell'oggetto a cui si vuole agire. Il *nomeroutine* argomento accetta una stringa che contiene il nome del metodo o proprietà della routine da richiamare. Il *CallType* argomento accetta una costante che rappresenta il tipo di routine da richiamare: un metodo (`Microsoft.VisualBasic.CallType.Method`), una proprietà di lettura (`Microsoft.VisualBasic.CallType.Get`), o una proprietà impostata (`Microsoft.VisualBasic.CallType.Set`). Il *argomenti* argomenti, che sono facoltativo, accetta una matrice di tipo `Object` che contiene gli argomenti per la procedura.  
  
 È possibile usare `CallByName` con le classi nella soluzione corrente, ma è in genere usato per accedere agli oggetti COM o gli oggetti da [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assembly.  
  
 Si supponga di aggiunta un riferimento a un assembly che contiene una classe denominata `MathClass`, che dispone di una nuova funzione denominata `SquareRoot`, come illustrato nel codice seguente:  
  
 [!code-vb[VbVbalrOOP#53](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_1.vb)]  
  
 L'applicazione può usare controlli casella di testo al controllo verrà chiamato il metodo e i relativi argomenti. Ad esempio, se `TextBox1` contiene l'espressione da valutare, e `TextBox2` viene usato per immettere il nome della funzione, è possibile usare il codice seguente per richiamare il `SquareRoot` funzione nell'espressione nel `TextBox1`:  
  
 [!code-vb[VbVbalrOOP#54](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_2.vb)]  
  
 Se si immette "64" nella `TextBox1`, "SquareRoot" nella `TextBox2`, quindi chiamare il `CallMath` procedure, la radice quadrata del numero in `TextBox1` viene valutata. Il codice di esempio richiama il `SquareRoot` funzione (che accetta una stringa che contiene l'espressione deve essere valutata come un argomento obbligatorio), restituisce "8" in `TextBox1` (la radice quadrata di 64). Naturalmente, se l'utente immette una stringa non valida in `TextBox2`, se la stringa contenente il nome di una proprietà anziché un metodo, o se il metodo richiede un ulteriore argomento, si verifica un errore di run-time. È necessario aggiungere codice di gestione degli errori affidabile quando si usa `CallByName` per prevenire questo o altri errori.  
  
> [!NOTE]
>  Mentre il `CallByName` funzione potrebbe essere utile in alcuni casi, è necessario valutare dell'utilità, anche le implicazioni sulle prestazioni, ovvero usando `CallByName` per richiamare una procedura è leggermente più lento rispetto a una chiamata ad associazione tardiva. Se si richiamano una funzione che viene poi chiamata più volte, ad esempio all'interno di un ciclo, `CallByName` può avere un grave effetto sulle prestazioni.  
  
## <a name="see-also"></a>Vedere anche
- <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>
- [Determinazione del tipo di un oggetto](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)
